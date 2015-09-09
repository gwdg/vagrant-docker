require 'yaml'

vagrant_base = File.expand_path(File.dirname(__FILE__))
docker_nodes = Dir["#{vagrant_base}/docker/*"].select {|f| File.directory? f}.map { |v| File.basename(v)}

Vagrant.configure("2") do |config|

  config.vm.provider "docker" do |d|
    d.vagrant_vagrantfile = "./docker-host/Vagrantfile"
  end

  docker_nodes.each do |docker_node|
    config.vm.define docker_node do |subconfig|  
      subconfig.vm.provider "docker" do |d|

        docker_path = File.expand_path("#{vagrant_base}/docker/#{docker_node}")
        docker_env  = YAML.load_file(File.expand_path("#{docker_path}/Dockerenv"))

        d.build_dir = docker_path
        d.name      = docker_node

        docker_env.each { |k,v| d.send("#{k}=", v)} if docker_env

      end
    end
  end
end
