**PM2 Clustering**: A popular production-ready process manager with built-in clustering support.

Simplified clustering (pm2 start app.js -i max).

Integrates well with CI/CD and ecosystem modules

Use Case: When you want a robust, feature-rich solution with minimal setup for production environments.

**When Using a Process Manager Like PM2**: Tools like PM2 abstract clustering and offer additional features such as monitoring and process management, reducing the need for manual clustering.

**What is the purpose of pm2 save?**

The purpose of pm2 save is to save the current process list managed by PM2 so it can be restored automatically after a system reboot or crash

Example context

pm2 start app.js --name "my-app"
pm2 save
pm2 startup

```javascript
// PM2 usage in a Node.js project
const pm2 = require('pm2');

pm2.connect((err) => {
  if (err) {
    console.error(err);
    process.exit(2);
  }

  pm2.start({
    script: 'app.js',  // Application to run
    name: 'my-app',    // Application name
  }, (err) => {
    if (err) return console.error(err);

    // Save the process list for future restoration
    pm2.save((err) => {
      if (err) console.error('Error saving process list:', err);
      else console.log('Process list saved!');
      pm2.disconnect();
    });
  });
});
```

PM2 is a popular process manager for Node.js that makes it easy to run applications as background services

**using pm2**
npm install -g pm2

pm2 start app.js --name "my-app"

pm2 save
pm2 startup

pm2 list

pm2 stop my-app
pm2 restart my-app

**using nohup**

lets you run a process in the background, even if the terminal is closed.
nohup node app.js > app.log 2>&1 &
ps aux | grep node
kill <process_id>


**Using systemd on Linux**

**sudo nano /etc/systemd/system/my-app.service**

[Unit]
Description=My Node.js App
After=network.target

[Service]
ExecStart=/usr/bin/node /path/to/app.js
Restart=always
User=your-user
Group=your-group
Environment=PATH=/usr/bin:/usr/local/bin
Environment=NODE_ENV=production
WorkingDirectory=/path/to

[Install]
WantedBy=multi-user.target


**Enable ans start service**

sudo systemctl enable my-app
sudo systemctl start my-app

**Check status**

sudo systemctl status my-app

**reastart and stop**
sudo systemctl restart my-app
sudo systemctl stop my-app


