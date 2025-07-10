  #Download-Snapshot-For-Faster-Sync
📈 Download Snapshot For Faster Sync 🚀-by-Mrr_Bear (Avinash Kumar)

⚕️ This Snapshot will help u to sync Faster & it will start from Block -- 3562700

🛠️ Installation Instructions

1.🔴 Stop The Node & Delete flow db

    sudo systemctl stop zgs 
2.🧹 Delete existing flow_db

    rm -rf $HOME/0g-storage-node/run/db/flow_db

3. ⬇️ Download the Snapshot

       wget -O flow_db.tar.gz https://github.com/Avinashtok/0g-fast-sync/releases/download/backup-3507655/flow_db-3507655.tar.gz

4. 📦 Extract the Snapshot

       tar -xzvf $HOME/0g-storage-node/run/db/flow_db.tar.gz -C $HOME/0g-storage-node/run/db/
   

5. 🔄 Restart the Node

       sudo systemctl restart zgs


🔍 Managing Logs
   
☑️Check Node Status
        
    sudo systemctl status zgs

![Snapshot Step](./Screenshot%202025-07-08%20072158.png)

👁️🔍View Logs

    tail -f ~/0g-storage-node/run/log/zgs.log.$(TZ=UTC date +%Y-%m-%d)


    
🧪 Monitor Sync Progress

    while true; do \
    response=$(curl -s -X POST http://localhost:5678 -H "Content-Type: application/json" \
    -d '{"jsonrpc":"2.0","method":"zgs_getStatus","params":[],"id":1}'); \
    logSyncHeight=$(echo $response | jq '.result.logSyncHeight'); \
    connectedPeers=$(echo $response | jq '.result.connectedPeers'); \
      echo -e "logSyncHeight: \033[32m$logSyncHeight\033[0m, connectedPeers: \033[34m$connectedPeers\033[0m"; \
      sleep 5; \
    done

![Download Snapshot](Screenshot%202025-07-08%20072343.png)






---

### ✅ 📬 Need any Help?
Telegram id : @Mrr_Bear
Name - Avinash kumar 

Age - Tujhe Usse kya Mje kr 😈 



    


