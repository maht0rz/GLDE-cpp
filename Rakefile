require 'rake'


# file paths to be included in the executable
sources = Rake::FileList['src/**/*.cpp'].join("\n")


# special flags for compiler
flags = [
  '--std=c++11'  
]

# paths to be available for header includes
includes = ['./src']
.map {|e|"-I#{e}"}

# libs to be included from external sources
libraries = []
.map {|e| "-l#{e}"}

# final executable
output = 'GLDE'



def generateOptions(*args)
  (args.each do |option|
    option.join(' ')
  end).join(' ')
end

def generateCommand(sources ,options)
  "g++ #{sources} #{options}"
end

task :default do
  puts "Building app from the following #sources: \n" + sources
  puts "Running the following command: \n"
  options = generateOptions(flags, includes, libraries)
  command = generateCommand(sources, options) + " -o #{output}"
  sh command
end
