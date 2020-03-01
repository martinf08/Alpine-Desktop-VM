Vagrant.configure(2) do |config|
  config.ssh.shell = "/bin/ash"
  config.vbguest.auto_update = false

  config.vm.define 'alpine' do |alpine|

    alpine.ssh.username = 'vagrant'
    alpine.ssh.password = 'vagrant'
    alpine.disksize.size = '10GB'

    alpine.vm.box = './alpine.box'

    config.vm.synced_folder '.', '/vagrant', disabled: true
    config.vm.synced_folder "./ansible", "/vagrant", type: "nfs"

    config.vm.network "private_network", ip: "192.168.50.2"

    alpine.vm.provider 'virtualbox' do |vb|
      vb.name = 'alpine-mate'
      vb.cpus = 1
      vb.memory = 1024
      vb.gui = true
      vb.customize [
        'modifyvm', :id,
        '--natdnshostresolver1', 'on',
        '--natdnsproxy1', 'on',
        '--vram', '256'
      ]
    end
  end
  config.vm.provision "shell", inline: "apk add ansible"

  config.vm.provision "ansible_local" do |ansible|
    ansible.compatibility_mode = "2.0"
    ansible.playbook = "playbook.yaml"
    ansible.extra_vars = { ansible_python_interpreter:"/usr/bin/python3" }
    # ansible.verbose = "-vvv"
  end
end
