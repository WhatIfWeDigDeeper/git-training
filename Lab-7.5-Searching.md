

    git grep Object.assign
    
    # --count or summary count by file
    git grep -c Object.assign

    git grep -c lodash

    git grep -p --break --heading Object.assign
    
    # search in a specific branch or tag
    git grep -p --break --heading -p Object.assign 0.0.110
   
    git log -S Object.assign --oneline

    # :function name:file
    git log -L :sumQuantity:cartUtil.js --oneline

![git log -L](https://github.com/VolusionDev/volusion-git-training-repo/blob/master/diagrams/git-log-L.png)