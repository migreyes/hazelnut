task :default do
  system "rm -rf _site"
  pids = [
    spawn("jekyll -w build"),
    spawn("sass --watch _includes/sass:assets/stylesheets"),
    spawn("coffee --bare --watch --join assets/javascript/scripts.js --compile _includes/coffeescript/*.coffee")
  ]

  trap "INT" do
    Process.kill "INT", *pids
    exit 1
  end

  loop do
    sleep 1
  end
end

task :clean do
  system "rm -rf _site"
  puts "Cleaned old site files."
end

task :compile do
  system "jekyll build"
  system "coffee --bare --join assets/javascript/scripts.js --compile _includes/coffeescript/*.coffee"
end

task :compress do
  puts "Compressing assets!"
  system "sass --style compressed _includes/sass/style.scss:assets/stylesheets/style.css"
  system "uglifyjs assets/javascript/scripts.js --compress --output assets/javascript/scripts.js"
end

task :build => [:clean, :compile, :compress] do
  puts "Done! See it locally at http://mig.dev/"
end

deploy_user = "user@site.com"
deploy_path = "site.com/location"

task :deploy => [:build] do
  puts "Deploying at site.com!"
  system("rsync -avze 'ssh -p 22' --delete _site/ #{deploy_user}:#{deploy_path}")
end