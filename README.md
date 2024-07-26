<h2>Overview</h2>
<strong>This project fuses Ollama and OpenWeb UI to create a dynamic and intuitive platform for managing web applications. Ollama delivers a high-performance backend framework built for scalability and efficiency, while OpenWeb UI offers a sleek, modern interface that makes interacting with these services smooth and enjoyable. Together, they provide a seamless and engaging experience</strong>

<h3>Key Features</h3>
<ul>
    <li><strong>Ollama:</strong> Command-line interface for running and managing a wide range of language models.</li>
    <li><strong>OpenWebUI:</strong> Web-based interface for interacting with language models, visualizing results, and managing model settings.</li>
    <li><strong>Model Support:</strong> Compatible with various models including llama, codegemma, llava </li>
    <li><strong>Customizable:</strong> Easily configure and extend both Ollama and OpenWebUI to suit your specific needs.</li>
</ul>

<h3>How It Works</h3>
<p>Ollama operates as a backend service that runs language models, providing a CLI to execute and manage these models. OpenWebUI connects to Ollama to offer a graphical user interface where you can interact with the models, view outputs, and adjust settings. The integration of Ollama with OpenWebUI ensures a seamless experience for users, allowing both command-line and graphical interactions with language models.</p>

<h3>Benefits</h3>
<ul>
    <li><strong>Enhanced Accessibility:</strong> Use a web interface to manage models, making it accessible even to users with minimal command-line experience.</li>
    <li><strong>Flexible Management:</strong> Run and test various language models with ease, adapting to different use cases and requirements.</li>
    <li><strong>Improved Productivity:</strong> Streamline workflows by combining the power of a CLI with a user-friendly web interface.</li>
    <li><strong>Scalability:</strong> Easily scale your language model deployments and manage them effectively through OpenWebUI.</li>
</ul>

<h2>Ollama Installation</h2>

<h3>1. Update System Packages</h3>
<strong>Ensure your system packages are up-to-date:</strong>
<pre><code>sudo apt update && sudo apt upgrade -y</code></pre>

<h3>2. Install Ollama</h3>
<strong>Run the following command to install Ollama:</strong>
<pre><code>curl -fsSL https://ollama.com/install.sh | sh</code></pre>

<h3>3. Verify Ollama Installation</h3>
<strong>To verify that Ollama is running correctly, visit <code>localhost:11434</code> in your browser. If Ollama is running, you should see the interface for managing your models.</strong>
<strong>You can explore available models at the <a href="https://ollama.com/library">Ollama Library</a>.</strong>

<h3>4. Run Language Models</h3>
<p> Run the model</p>
<pre><code>ollama run llama3.1:8b</code></pre>
<strong>You can also use other models such as <code>llama</code>, <code>llava</code> and others by replacing the model <a href="https://ollama.com/library">Ollama Library</a> name and there version in the command.</strong>


<h2><strong>Configure OpenWebUI</strong></h2>

<h3>Install Dependencies</h3>
<pre><code>sudo apt-get update
sudo apt-get install ca-certificates curl -y
sudo install -m 0755 -d /etc/apt/keyrings
sudo curl -fsSL https://download.docker.com/linux/ubuntu/gpg -o /etc/apt/keyrings/docker.asc
sudo chmod a+r /etc/apt/keyrings/docker.asc
echo \
"deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.asc] https://download.docker.com/linux/ubuntu \
$(. /etc/os-release && echo "$VERSION_CODENAME") stable" | \
sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
sudo apt-get update
sudo apt-get install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin -y
</code></pre>

<p><strong>Start OpenWebUI</strong></p>
<p><pre><code>sudo docker run -d --network=host -v open-webui:/app/backend/data -e OLLAMA_BASE_URL=http://127.0.0.1:11434 --name open-webui --restart always ghcr.io/open-webui/open-webui:main
</code></pre></p>

<p><strong>Verify</strong></p>
<pre><code>sudo docker ps</code></pre>

<p><strong>Open your webBrowser and go to port: 8080 </strong> http://localhost:8080 </p>
