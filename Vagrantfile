Vagrant.configure("2") do |config|
  config.vm.box = "google/gce"
  config.vm.provider :google do |google, override|
    google.google_project_id = "fleet-flame-301407"
    google.google_json_key_location = "/home/ansible/Desktop/vagrant/fleet-flame-301407-c2898041b54e.json"

    google.image_family = 'centos-7'
    google.name = "spinup-centos"
    google.tags = ['http-server']
    google.machine_type = 'n1-standard-1'
    google.disk_size = '20'

    override.ssh.username = "ansible"
    override.ssh.private_key_path = "~/.ssh/google_compute_engine"
  end
  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "playbook.yml"
  end
end
