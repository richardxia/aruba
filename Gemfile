source 'https://rubygems.org'

# Use dependencies from gemspec
gemspec

# Load local Gemfile
load File.expand_path('../Gemfile.local', __FILE__) if File.file? File.expand_path('../Gemfile.local', __FILE__)

# Debug aruba
group :debug do
  if RUBY_VERSION >= '2' && !RUBY_PLATFORM.include?('java')
    gem 'byebug', '~> 9.0'
    gem 'pry-byebug', '~> 3.4'
  end

  if RUBY_VERSION < '2' && !RUBY_PLATFORM.include?('java')
    gem 'debugger', '~> 1.6.8'
    gem 'pry-debugger', '~> 0.2.3'
  end

  gem 'pry-doc', '~> 0.11.1'
end

group :development do
  # Needed for lint:yard:junk task
  if RUBY_VERSION >= '2.3.0'
    gem 'yard-junk', '~> 0'
  end
end

group :development, :test do
  # we use this to demonstrate interactive debugging within our feature tests
  if RUBY_VERSION >= '2'
    gem 'pry', '~> 0.11.2'
  else
    gem 'pry', '~> 0.9.12'
  end

  # Run development and test tasks
  gem 'rake', '~> 12.2.1'

  if RUBY_VERSION >= '2.0.0'
    # Lint travis yaml
    gem 'travis-yaml'

    # Reporting
    gem 'kramdown', '~> 1.14'
  end

  # Code Coverage
  gem 'simplecov', '~> 0.10'

  # API docs generation
  gem 'yard', '~>0.9.9'

  # Test api
  gem 'rspec', '~> 3.4'
  gem 'fuubar', '~> 2.2.0'

  # using platform for this makes bundler complain about the same gem given
  # twice
  gem 'cucumber', '~> 2.0'

  # Make aruba compliant to ruby community guide
  gem 'rubocop', '~> 0.32', '< 0.41.1'

  # gem 'cucumber-pro', '~> 0.0'

  # License compliance
  if RUBY_VERSION < '2.3'
    gem 'license_finder', '~> 2.0'
  else
    gem 'license_finder', '~> 3.0.2'
  end

  # Upload documentation
  # gem 'relish', '~> 0.7.1'

  gem 'minitest', '~> 5.10.3'

  gem 'json', '~>2.1'
end
