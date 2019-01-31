nodes = [
  { hostname: 'esxi-670', box: 'vmware/esxi'}
]

Vagrant.configure("2") do |config|
  nodes.each do |node|
    config.vm.define node[:hostname] do |node_config|
      node_config.vm.hostname = node[:hostname]
      node_config.vm.box = node[:box]
    end
  end
  config.vm.provider :vmware_desktop do |domain|
          domain.gui = true
          domain.vmx["ethernet0.pcislotnumber"] = "160"
          domain.vmx["memsize"] = "4096"
          domain.vmx["numvcpus"] = "2"
   end
end
