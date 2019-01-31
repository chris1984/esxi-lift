nodes = [
  { hostname: 'esxi-670', box: 'vmware/esxi', version: '6.7.0-8169922'},
  { hostname: 'esxi-650', box: 'vmware/esxi', version: '6.5.0-8294253'},
  { hostname: 'photon-2', box: 'vmware/photon', version: '2.0.0'}
]

Vagrant.configure("2") do |config|
  nodes.each do |node|
    config.vm.define node[:hostname] do |node_config|
      node_config.vm.hostname = node[:hostname]
      node_config.vm.box = node[:box]
      node_config.vm.box_version = node[:version]
    end
  end
  config.vm.provider :vmware_desktop do |domain|
          domain.gui = true
          domain.vmx["ethernet0.pcislotnumber"] = "160"
          domain.vmx["memsize"] = "4096"
          domain.vmx["numvcpus"] = "2"
   end
end
