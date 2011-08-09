desc "Installs the Plugins"
task :setup do
	user = ENV['USER']
	if system("ps -eo comm | grep ^gedit$") then
	  puts "Please close gedit before running rake setup again."
  elsif user == "root" then
    puts "You need to sudo this action"
  else 
		system("cp rails.xml /usr/share/mime/packages")
		system("update-mime-database /usr/share/mime")
		system("cp erb.lang /usr/share/gtksourceview-2.0/language-specs/")
		system("cp yaml.lang /usr/share/gtksourceview-2.0/language-specs/")
		system("mkdir -p ~/.gnome2/gedit") unless File.directory? ENV['HOME'] + "/.gnome2/gedit"
		system("cp -R snippets ~/.gnome2/gedit/")
		system("mkdir -p ~/.gnome2/gedit/plugins") unless File.directory? ENV['HOME'] + "/.gnome2/gedit/plugins"
		system("cp -R plugins/* ~/.gnome2/gedit/plugins/")
		system("mkdir -p ~/.gnome2/gedit/styles") unless File.directory? ENV['HOME'] + "/.gnome2/gedit/styles"
		system("cp -R styles/* ~/.gnome2/gedit/styles/")
	end
end
