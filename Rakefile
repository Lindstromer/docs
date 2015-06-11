require 'middleman-gh-pages'
require 'fileutils'

task :default => [:build]

task :apigen do
  if Dir.exists?('papi')
    FileUtils.remove_dir('papi')
  end

  if Dir.exists?('source/apigen')
    FileUtils.remove_dir('source/apigen')
  end

  sh 'git clone git@github.com:wp-papi/papi.git papi'
  sh 'apigen generate -s papi/src -d source/apigen'

  FileUtils.remove_dir('papi')
end

task :publish => :apigen
