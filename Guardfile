# A sample Guardfile
# More info at https://github.com/guard/guard#readme

group :specs, halt_on_fail: true do
  guard :rspec, cmd: 'bundle exec rspec' do
    watch(%r{^spec/.+_spec\.rb$})
    watch(%r{^lib/(.+)\.rb$}) { |m| "spec/#{m[1]}_spec.rb" }
    watch('spec/spec_helper.rb') { "spec/" }
  end

  guard :rubocop do
    watch(%r{^lib/(.+)\.rb$})
    watch(%r{(?:.+/)?\.rubocop\.yml$}) { |m| File.dirname(m[0]) }
  end
end

guard 'bundler' do
  watch('Gemfile')
  watch(/^.+\.gemspec/)
end
