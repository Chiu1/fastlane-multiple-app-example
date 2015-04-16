# fastlane-multiple-app-example
A barebones example of the how I'm trying to use fastlane with multiple applications within a single workspace.

Run ``` build_App1.sh ``` & ``` build_App2.sh ```

Here is a snippet from the where it's erroring out currently:

``` 
INFO [2015-04-16 17:44:12.65]: ---------------------
INFO [2015-04-16 17:44:12.65]: --- Step: deliver ---
INFO [2015-04-16 17:44:12.65]: ---------------------
INFO [2015-04-16 17:44:13.86]: Skipping submission of app update
INFO [2015-04-16 17:44:14.05]: Got all information needed to deploy a new update ('1.0.7') for app 'com.mavenclinic.ForumQA'
INFO [2015-04-16 17:44:15.63]: Logging into iTunesConnect
INFO [2015-04-16 17:44:25.77]: Successfully logged into iTunesConnect
INFO [2015-04-16 17:44:26.57]: Variable Dump:
INFO [2015-04-16 17:44:26.57]: {:ENVIRONMENT=>nil, :LANE_NAME=>:deploy, :IPA_OUTPUT_PATH=>"/Users/jason/fastlane-multiple-app-example/fastlane/_build_app1/App1.ipa", :DSYM_OUTPUT_PATH=>"/Users/jason/fastlane-multiple-app-example/fastlane/_build_app1/App1.app.dSYM.zip"}
FATAL [2015-04-16 17:44:26.57]: App is missing information (apple_id not given)
FATAL [2015-04-16 17:44:27.29]: fastlane finished with errors
/usr/local/lib/ruby/gems/2.1.0/gems/fastlane_core-0.5.2/lib/fastlane_core/itunes_connect/itunes_connect_helper.rb:33:in `verify_app': App is missing information (apple_id not given) (FastlaneCore::ItunesConnect::ItunesConnectGeneralError)
	from /usr/local/lib/ruby/gems/2.1.0/gems/deliver-0.9.1/lib/deliver/itunes_connect/itunes_connect_reader.rb:45:in `get_live_version'
	from /usr/local/lib/ruby/gems/2.1.0/gems/deliver-0.9.1/lib/deliver/itunes_connect/itunes_connect_new_version.rb:11:in `create_new_version!'
	from /usr/local/lib/ruby/gems/2.1.0/gems/deliver-0.9.1/lib/deliver/app.rb:152:in `create_new_version!'
	from /usr/local/lib/ruby/gems/2.1.0/gems/deliver-0.9.1/lib/deliver/deliver_process.rb:141:in `verify_app_on_itunesconnect'
	from /usr/local/lib/ruby/gems/2.1.0/gems/deliver-0.9.1/lib/deliver/deliver_process.rb:37:in `run'
	from /usr/local/lib/ruby/gems/2.1.0/gems/deliver-0.9.1/lib/deliver/deliverer.rb:133:in `finished_executing_deliver_file'
	from /usr/local/lib/ruby/gems/2.1.0/gems/deliver-0.9.1/lib/deliver/deliverfile/deliverfile.rb:31:in `initialize'
	from /usr/local/lib/ruby/gems/2.1.0/gems/deliver-0.9.1/lib/deliver/deliverer.rb:85:in `new'
	from /usr/local/lib/ruby/gems/2.1.0/gems/deliver-0.9.1/lib/deliver/deliverer.rb:85:in `initialize'
	from /usr/local/lib/ruby/gems/2.1.0/gems/fastlane-0.9.0/lib/fastlane/actions/deliver.rb:21:in `new'
	from /usr/local/lib/ruby/gems/2.1.0/gems/fastlane-0.9.0/lib/fastlane/actions/deliver.rb:21:in `block in run'
	from /usr/local/lib/ruby/gems/2.1.0/gems/fastlane-0.9.0/lib/fastlane/actions/deliver.rb:19:in `chdir'
	from /usr/local/lib/ruby/gems/2.1.0/gems/fastlane-0.9.0/lib/fastlane/actions/deliver.rb:19:in `run'
	from /usr/local/lib/ruby/gems/2.1.0/gems/fastlane-0.9.0/lib/fastlane/fast_file.rb:104:in `block (2 levels) in method_missing'
	from /usr/local/lib/ruby/gems/2.1.0/gems/fastlane-0.9.0/lib/fastlane/actions/actions_helper.rb:29:in `execute_action'
	from /usr/local/lib/ruby/gems/2.1.0/gems/fastlane-0.9.0/lib/fastlane/fast_file.rb:103:in `block in method_missing'
	from /usr/local/lib/ruby/gems/2.1.0/gems/fastlane-0.9.0/lib/fastlane/fast_file.rb:102:in `chdir'
	from /usr/local/lib/ruby/gems/2.1.0/gems/fastlane-0.9.0/lib/fastlane/fast_file.rb:102:in `method_missing'
	from (eval):18:in `block (2 levels) in parse'
	from /usr/local/lib/ruby/gems/2.1.0/gems/fastlane-0.9.0/lib/fastlane/runner.rb:19:in `call'
	from /usr/local/lib/ruby/gems/2.1.0/gems/fastlane-0.9.0/lib/fastlane/runner.rb:19:in `block in execute'
	from /usr/local/lib/ruby/gems/2.1.0/gems/fastlane-0.9.0/lib/fastlane/runner.rb:13:in `chdir'
	from /usr/local/lib/ruby/gems/2.1.0/gems/fastlane-0.9.0/lib/fastlane/runner.rb:13:in `execute'
	from /usr/local/lib/ruby/gems/2.1.0/gems/fastlane-0.9.0/lib/fastlane/lane_manager.rb:45:in `block in cruise_lanes'
	from /usr/local/lib/ruby/gems/2.1.0/gems/fastlane-0.9.0/lib/fastlane/lane_manager.rb:44:in `each'
	from /usr/local/lib/ruby/gems/2.1.0/gems/fastlane-0.9.0/lib/fastlane/lane_manager.rb:44:in `cruise_lanes'
	from /usr/local/lib/ruby/gems/2.1.0/gems/fastlane-0.9.0/bin/fastlane:32:in `block (2 levels) in run'
	from /usr/local/lib/ruby/gems/2.1.0/gems/commander-4.3.2/lib/commander/command.rb:178:in `call'
	from /usr/local/lib/ruby/gems/2.1.0/gems/commander-4.3.2/lib/commander/command.rb:178:in `call'
	from /usr/local/lib/ruby/gems/2.1.0/gems/commander-4.3.2/lib/commander/command.rb:153:in `run'
	from /usr/local/lib/ruby/gems/2.1.0/gems/commander-4.3.2/lib/commander/runner.rb:428:in `run_active_command'
	from /usr/local/lib/ruby/gems/2.1.0/gems/commander-4.3.2/lib/commander/runner.rb:68:in `run!'
	from /usr/local/lib/ruby/gems/2.1.0/gems/commander-4.3.2/lib/commander/delegates.rb:15:in `run!'
	from /usr/local/lib/ruby/gems/2.1.0/gems/fastlane-0.9.0/bin/fastlane:111:in `run'
	from /usr/local/lib/ruby/gems/2.1.0/gems/fastlane-0.9.0/bin/fastlane:117:in `<top (required)>'
	from /usr/local/bin/fastlane:23:in `load'
	from /usr/local/bin/fastlane:23:in `<main>' 
 
```
