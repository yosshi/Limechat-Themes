namespace :themes do
  
  desc 'Create symlinks for all of the themes in the current directory'
  task :linkup do
    %x[git submodule init && git submodule update]
    puts "updates done. linkup starting"
    Dir.glob("#{File.dirname(__FILE__)}/**/*.css") { |css|
        newcss = File.basename(css)
        FileUtils.ln_s css, newcss, :force => true
        }
    Dir.glob("#{File.dirname(__FILE__)}/**/*.yaml") { |yaml|
        newyaml = File.basename(yaml)
        FileUtils.ln_s yaml, newyaml, :force => true
        }
    Dir.glob("#{File.dirname(__FILE__)}/**/*.js") { |js|
        newjs = File.basename(js)
        FileUtils.ln_s js, newjs, :force => true
        }
  end

  desc 'Install into the logged in user\'s limechat directory'
  task :install do
    puts "Starting updates"
    %x[git submodule init && git submodule update]
    puts "Moving Files"
    source = Dir.getwd + "/."
    Dir.chdir
    target = Dir.getwd + '/Library/Application Support/LimeChat/Themes/'
    FileUtils.cp_r(source, target, :remove_destination => true)
      puts "Setting up Symlinks"
      Dir.chdir("#{Dir.getwd}/Library/Application Support/LimeChat/Themes/")  
      Dir.glob("#{File.dirname(__FILE__)}/**/*.css") { |css|
          newcss = File.basename(css)
          FileUtils.ln_s css, newcss, :force => true
          }
      Dir.glob("#{File.dirname(__FILE__)}/**/*.yaml") { |yaml|
          newyaml = File.basename(yaml)
          FileUtils.ln_s yaml, newyaml, :force => true
          }
      Dir.glob("#{File.dirname(__FILE__)}/**/*.js") { |js|
          newjs = File.basename(js)
          FileUtils.ln_s js, newjs, :force => true
          }
  end
  
  desc 'Install into the logged in user\'s appstore limechat directory'
  task :appstore_install do
    puts "Starting updates"
    %x[git submodule init && git submodule update]
    puts "Moving Files"
    source = Dir.getwd + "/."
    Dir.chdir
    target = Dir.getwd + '/Library/Application\\ Support/net.limechat.LimeChat-AppStore/Themes/'
    FileUtils.cp_r(source, target, :remove_destination => true)
      puts "Setting up Symlinks"
      Dir.chdir("#{Dir.getwd}/Library/Application\\ Support/net.limechat.LimeChat-AppStore/Themes/")  
      Dir.glob("#{File.dirname(__FILE__)}/**/*.css") { |css|
          newcss = File.basename(css)
          FileUtils.ln_s css, newcss, :force => true
          }
      Dir.glob("#{File.dirname(__FILE__)}/**/*.yaml") { |yaml|
          newyaml = File.basename(yaml)
          FileUtils.ln_s yaml, newyaml, :force => true
          }
      Dir.glob("#{File.dirname(__FILE__)}/**/*.js") { |js|
          newjs = File.basename(js)
          FileUtils.ln_s js, newjs, :force => true
          }
  end
  
end