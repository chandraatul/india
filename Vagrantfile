Vagrant.configure(2) do |config|

machines = [
{
:name => "test1",
:ipaddress => "10.1.2.3",
:memory => "512",
:box => "bento/centos-7.2"
}]

machines.each do |machine|
config.vm.define machine[:name] do |instance|
instance.vm.box = machine[:box]
instance.vm.hostname = machine[:name]
instance.ssh.insert_key = false
#instance.ssh.private_key_path = "~/.vagrant.d/insecure_private_key"
instance.vm.network "private_network", ip: machine[:ipaddress]
# machine[:ports].each do |port|
# instance.vm.network "forwarded_port", host: port[:host], guest: port[:guest]
# end

instance.vm.provider "virtualbox" do |vb|
vb.name = machine[:name]
vb.memory = machine[:memory]
end

end # config
end #machine
end #vagrant
