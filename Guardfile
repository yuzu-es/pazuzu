def on_rb_or_yml_update
  # run_pazuzu = "aws --region us-west-1 ec2 describe-volumes | ruby pazuzu.rb | jsonlint"
  run_pazuzu = "aws --region us-west-1 ec2 describe-volumes | ruby pazuzu.rb"



  command_to_run = "#{run_pazuzu}"
  return command_to_run
end





guard :shell do
  watch(/(.*)\.rb$/) {|m| `#{on_rb_or_yml_update}` }
end


guard :shell do
  watch(/(.*)\.json$/) {|m| `jsonlint #{m[0]}` }
end