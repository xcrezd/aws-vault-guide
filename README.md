# to start aws-vault login in a new temporary chrome profile:

` function __awslogin {  

         nohup bash -c "aws-vault --debug login $1 --stdout | xargs -t /opt/google/chrome/chrome  --args --no-first-run --new-window -disk-cache-dir=$(mktemp -d /tmp/chromecanary.XXXXXXX) --user-data-dir=$(mktemp -d /tmp/chromecanary.XXXXXXX) >& /dev/null" &    
         
} `

` alias awslogin='__awslogin' `

` awslogin profile_name_in_vault `
