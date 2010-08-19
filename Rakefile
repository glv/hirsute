require 'rubygems'
require 'rake'

begin
  require 'jeweler'
  Jeweler::Tasks.new do |gem|
    gem.name = "hirsute"
    gem.summary = %Q{TODO: one-line summary of your gem}
    gem.description = %Q{A Naked Objects framework for Ruby}
    gem.email = "glv@vanderburg.org"
    gem.homepage = "http://github.com/glv/hirsute"
    gem.authors = ["Glenn Vanderburg"]
    gem.add_development_dependency "spicycode-micronaut", ">= 0"
    # gem is a Gem::Specification... see http://www.rubygems.org/read/chapter/20 for additional settings
  end
  Jeweler::GemcutterTasks.new
rescue LoadError
  puts "Jeweler (or a dependency) not available. Install it with: gem install jeweler"
end

require 'micronaut/rake_task'
Micronaut::RakeTask.new(examples) do |examples|
  examples.pattern = 'examples/**/*_example.rb'
  examples.ruby_opts << '-Ilib -Iexamples'
end

Micronaut::RakeTask.new(:rcov) do |examples|
  examples.pattern = 'examples/**/*_example.rb'
  examples.rcov_opts = '-Ilib -Iexamples'
  examples.rcov = true
end

task :examples => :check_dependencies

task :default => :examples

require 'rake/rdoctask'
Rake::RDocTask.new do |rdoc|
  version = File.exist?('VERSION') ? File.read('VERSION') : ""

  rdoc.rdoc_dir = 'rdoc'
  rdoc.title = "hirsute #{version}"
  rdoc.rdoc_files.include('README*')
  rdoc.rdoc_files.include('lib/**/*.rb')
end
