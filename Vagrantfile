Vagrant.configure('2') do |config|
  config.vm.box_check_update = false
  config.vm.box = "archlinux/archlinux"

  config.vm.synced_folder './', '/vagrant', type: 'rsync'
  # config.vm.synced_folder './', '/vagrant', type: 'nfs'

  config.vm.define "myvm" do |myvm|
    myvm.vm.provider :libvirt do |v|
      v.memory = 256
      v.cpus = 1
      v.nested = true
    end
    myvm.vm.provision "shell" do |s|
      s.path = "run.sh"
      s.privileged = false
    end
  end
end

