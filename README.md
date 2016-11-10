# pipeline-pre-post-repo

This is a temporary repo containing sources for pre- and post actions of deployment pipeline components like XLR, XLD.

# XLD
docker build -t xldeploy:5.5.5 .

docker run -e PLUGINS_FILE_URL="https://raw.githubusercontent.com/ltutar/pipeline-pre-post-repo/master/xldeploy/plugins/list-of-plugins.txt" -p 4516:4516 xldeploy:5.5.5

# XLR
docker build -t xlrelease:5.0.1 .

docker run -e PLUGINS_FILE_URL="https://raw.githubusercontent.com/ltutar/pipeline-pre-post-repo/master/xlrelease/plugins/list-of-plugins.txt" -p 5516:5516 xlrelease:5.0.1

# Jenkins
docker build -t rbcdjenkins:1.0 .
docker run -e PLUGINS_FILE_URL="https://raw.githubusercontent.com/ltutar/pipeline-pre-post-repo/master/jenkins/plugins/list-of-plugins.txt" -p 8080:8080 rbcdjenkins:1.0
