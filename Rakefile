task :default do
  system "rm -rf _site"
  pids = [
    spawn("jekyll"),
    spawn("sass --watch _includes/sass:assets/stylesheets")
  ]

  trap "INT" do
    Process.kill "INT", *pids
    exit 1
  end

  loop do
    sleep 1
  end
end

task :compress do
  puts "Compressing stylesheets!"
  system "sass --style compressed _includes/sass/style.scss:assets/stylesheets/style.css"
end

deploy_user = "user@site.com"
deploy_path = "site.com/location"

task :deploy do
  puts "Compressing stylesheets!"
  system "sass --style compressed _includes/sass/style.scss:assets/stylesheets/style.css"
  puts "Deploying at site.com!"
  system("rsync -avze 'ssh -p 22' --delete _site/ #{deploy_user}:#{deploy_path}")
end