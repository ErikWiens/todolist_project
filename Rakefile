require "rake/testtask"
require 'find'
require "bundler/gem_tasks"

desc 'Say hello'
task :hello do
  puts "Hello there. This is the 'hello' task."
end

desc 'Run tests'
task :default => :test

Rake::TestTask.new(:test) do |t|
  t.libs << "test"
  t.libs << "lib"
  t.test_files = FileList['test/**/*_test.rb']
end

# Add a task to your Rakefile that lists every file in your project except
# those whose names begin with . and those that reside in a directory whose
# name begins with ..

# You can use Find::find from the Ruby standard library. You will also need
# File#file? to test whether a name in Find#find's block is a file or a
# directory.

# desc 'Find all files'
# task :files do
#   Find.find(Rake.application.original_dir) do |path|
#     if FileTest.directory?(path)
#       if File.basename(path).start_with?('.')
#         Find.prune       # Don't look any further into this directory.
#       else
#         next
#       end
#     else
#       puts File.basename(path)
#     end
#   end
# end

desc 'Display inventory of all files'
task :inventory do
  Find.find('.') do |name|
    next if name.include?('/.') # Excludes files and directories with . names
    puts name if File.file?(name)
  end
end