# pipeline-pre-post-repo

This is a temporary repo containing sources for pre- and post actions of deployment pipeline components like XLR, XLD.

# XLD
docker run -e PLUGINS_FILE_URL="https://raw.githubusercontent.com/ltutar/pipeline-pre-post-repo/master/xldeploy/plugins/list-of-plugins.txt" -p 4516:4516 xldeploy:5.5.5

# XLR
docker run -e PLUGINS_FILE_URL="https://raw.githubusercontent.com/ltutar/pipeline-pre-post-repo/master/xlrelease/plugins/list-of-plugins.txt" -p 5516:5516 xlrelease:5.0.1
