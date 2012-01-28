



desc "clean up"
task :clean do
  sh "rm -rf site/"
end

desc "compile the jade and stylus into a site"
task :build do
  Rake::Task['clean'].invoke
  sh "jade *.jade"
  sh "stylus *.styl"
  sh "mkdir site"
  sh "mv *.html site/"
  sh "mv *.css site/"
end
