```ruby
Vagrant.configure("2") do |config|
  config.vm.box = "generic/alpine318"		# Menentukan sistem operasi apa yang digunakan
  config.vm.hostname = "charles"			# Menentukan Hostname
  config.vm.network  "public_network"
	
	config.vm.provider "virtualbox" do |vb|
   	vb.memory = "512"						# Besaran RAM yang digunakan
   	vb.cpus = "1"							# Jumlah CPU Yang dipakai
   	vb.name = "latihan-asj2"				# Nama Mesin Virtual
   	end

config.vm.provision "shell", inline: <<-SHELL
      apk update
      apk add apache2
      service apache2 start
      SHELL
end
```
