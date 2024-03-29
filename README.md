# MLops Fastapi Deployment

Run into server without setup ci/cd

### Steps
<ul>
    <li>Create <strong>Digital Ocean</strong> Account</li>
    <li><i>The first User will get $200 free for 2 months, but just pay for the cheapest plan of $5 at the start</i></li>
    <li>Create Droplets</li>
    <li>Choose server location. Ex: Singapore</li>
    <li>Run <code>ssh-keygen -t rsa -b 4096 -C "your_email@example.com"</code> in root device</li>
    <li>Check the ssh in root device <code>ls .ssh</code></li>
    <li>Copy public ssh <code>cat .ssh/id_rsa.pub | pbcopy</code> (Mac)</li>
    <li>Paste in SSH key in Droplets account that creating (can also use a password but I just use SSH)</li>
    <li>Open terminal in droplets (Choose droplet -> Access -> Launch Droplet Console)</li>
    <li>Check SSH must be same in local <strong>cd ~/.ssh</strong> then write <code>cat authorized_keys</code></li>
    <li>If same continue to next step, but if not same copy SSH local and paste to <strong>authorized_keys</strong> in server</li>
    <li>Back to root directory <code>cd ..</code></li>
    <li>Install Docker <a href="https://www.digitalocean.com/community/tutorials/how-to-install-and-use-docker-on-ubuntu-20-04">Here</a> just follow step 1 (step 2 optional)</li>
    <li>Close droplet terminal and open terminal in local device</li>
    <li>Run <code>ssh root@ip_address_v4_droplets</code></li>
    <li>If success it will show mesage <i>Welcome to Ubuntu @version etc...</i></li>
    <li>Create dockerfile in root file code at Vscode or something that used</li>
    <li>Create docker-compose.yml then connect your dockerfile inside (as my file code)</li>
    <li>Setting the port anything we want. (my port is 8080)</li>
    <li>Push your repository</li>
    <li>Back to terminal device and install docker compose <code>apt install docker-compose</code></li>
    <li>Clone the repository that want to build <code>git clone https://url_repository.git</code></li>
    <li>Ensure docker is active <code>sudo systemctl status docker</code></li>
    <li>Move to directory to <code>cd path/repository</code></li>
    <li>Run <code>docker-compose up -d --build</code></li>
    <li>If success the message show "done"</li>
    <li>Visit url the project <i>http://ip_address_droplet:port/docs</i></li>
    <li>Deployment succesful</li>
    <li><code>exit</code> to exit from server</li>
</ul>

### Caution
If you restart droplet, docker will automatically stop please do this :<br/>
<ul>
    <li>Ensure docker is active <code>sudo systemctl status docker</code></li>
    <li>Check port running <code>docker ps</code></li>
    <li>To run all port project <code>docker start</code></li>
    <li>To run spesific project <code>docker start id_container</code></li>
</ul>
