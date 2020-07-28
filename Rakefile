require 'html-proofer'

task default: %w[lint]

task :lint do
  exec 'find . -name "*.md" | grep -v "^.\/vendor\/" | grep -v "^.\/public\/" | grep -v "^.\/_site\/" | xargs mdl -r ~MD002,~MD033,~MD041'
end

task :htmlproofer do
  options = { :only_4xx => true, :allow_hash_href => true }
  HTMLProofer.check_directory("./_site", options).run
end
