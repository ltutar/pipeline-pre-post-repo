# pipeline-pre-post-repo

This is a temporary repo containing sources for pre- and post actions of deployment pipeline components like XLR, XLD.

# XLD
docker build -t xldeploy:6.0.0 .

docker run -e PLUGINS_FILE_URL="https://raw.githubusercontent.com/ltutar/pipeline-pre-post-repo/master/xldeploy/plugins/list-of-plugins.txt" -p 4516:4516 xldeploy:6.0.0

# XLR
docker build -t xlrelease:6.0.0 .

docker run -e PLUGINS_FILE_URL="https://raw.githubusercontent.com/ltutar/pipeline-pre-post-repo/master/xlrelease/plugins/list-of-plugins.txt" -p 5516:5516 xlrelease:6.0.0

# Jenkins
docker build -t rbcdjenkins:1.0 .
docker run -e JENKINS_UC_DOWNLOAD="https://updates.jenkins.io/download" -e PLUGINS_FILE_URL="https://raw.githubusercontent.com/ltutar/pipeline-pre-post-repo/master/jenkins/plugins/list-of-plugins.txt" -e JENKINS_INIT_CONFIG_SCRIPT_URL="https://raw.githubusercontent.com/ltutar/petclinic/master/jenkins/init_jenkins.groovy" -p 8080:8080 jenkins:2.19.2
