require 'rubygems'
require 'rake'

begin
  require 'jeweler'
  Jeweler::Tasks.new do |gem|
    gem.name = "alegscogs-asset_library"
    gem.summary = %Q{Manage and bundle CSS and JavaScript files}
    gem.email = "alegscogs@gmail.com"
    gem.homepage = "http://github.com/alegscogs/asset_library"
    gem.add_dependency 'adamh-glob_fu', '>= 0.0.4'
    gem.authors = ["adamh", "alegscogs"]
    gem.files = FileList['lib/**/*.rb', 'rails/**/*.rb'].to_a
  end

rescue LoadError
  puts "Jeweler (or a dependency) not available. Install it with: sudo gem install jeweler"
end

require 'spec/rake/spectask'
Spec::Rake::SpecTask.new(:spec) do |spec|
  spec.libs << 'lib' << 'spec'
  spec.spec_files = FileList['spec/**/*_spec.rb']
end

Spec::Rake::SpecTask.new(:rcov) do |spec|
  spec.libs << 'lib' << 'spec'
  spec.pattern = 'spec/**/*_spec.rb'
  spec.rcov = true
end

task :spec => :check_dependencies

task :default => :spec

require 'rake/rdoctask'
Rake::RDocTask.new do |rdoc|
  if File.exist?('VERSION.yml')
    config = YAML.load(File.read('VERSION.yml'))
    version = "#{config[:major]}.#{config[:minor]}.#{config[:patch]}"
  else
    version = ""
  end

  rdoc.rdoc_dir = 'rdoc'
  rdoc.title = "alegscogs-asset_library #{version}"
  rdoc.rdoc_files.include('README*')
  rdoc.rdoc_files.include('lib/**/*.rb')
end

