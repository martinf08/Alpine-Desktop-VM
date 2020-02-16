Vagrant.configure(2) do |config|
  config.ssh.shell = "/bin/ash"
  config.vbguest.auto_update = false

  config.vm.define 'mategui' do |mategui|

    mategui.ssh.username = 'vagrant'
    mategui.ssh.password = 'vagrant'
    mategui.disksize.size = '10GB'

    mategui.vm.box = './mategui.box'

    config.vm.network "private_network", ip: "192.168.10.10"
    config.vm.synced_folder ".", "/vagrant", disabled: true
    config.vm.synced_folder "data", "/data", type: "nfs"

    mategui.vm.provider 'virtualbox' do |vb|
      vb.gui = true
      vb.name = 'mategui'
      vb.cpus = 2
      vb.memory = 2048
      vb.customize [
        'modifyvm', :id,
        '--natdnshostresolver1', 'on',
        '--natdnsproxy1', 'on'
      ]
    end
  end
end
