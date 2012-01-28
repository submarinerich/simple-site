



desc "clean up"
task :clean do
  sh "rm -rf site/"
end

desc "compile the jade and stylus into a site"
task :build => :clean do
  sh "jade *.jade"
  sh "stylus *.styl"
  Dir.entries('./') do | entry |
    if entry.include? '.mkd'
      sh "multimarkdown "+entry+" > "+entry.split('.mkd')[0]+".html"
    end
  end
  sh "mkdir site"
  sh "mv *.html site/"
  sh "mv *.css site/"
end


desc "clean, compile, open in a browser"
task :run => :build do
  sh "open site/index.html"
end

