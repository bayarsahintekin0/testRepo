---
title: Set up the Project
description: 5
---

<p>You can download the codelab project from: <a href="https://github.com/bayarsahintekin0/BasicSecurityManagement" target="_blank">https://github.com/bayarsahintekin0/BasicSecurityManagement</a></p>

<h2><strong>Creating a Project</strong></h2>
<p><strong>Step 1</strong>: Start Android Studio.</p>
<p><strong>Step 2</strong>: Choose <strong>File</strong> &gt; <strong>Open</strong>, go to the directory where the sample project is decompressed, and click <strong>OK</strong>.<br><img style="width: 376.00px" src="https://raw.githubusercontent.com/bayarsahintekin0/testRepo/gh-pages/assets/bsm_codelab.PNG" onclick="imageclick(src)"></p>

<p><strong>Step 3</strong>: Download and add securitykit-1.0.1.aar file to <strong>libs</strong> folder. <br><img style="width: 376.00px" src="https://raw.githubusercontent.com/bayarsahintekin0/testRepo/gh-pages/assets/security-kit-library.png" onclick="imageclick(src)"></p>
<p> Download link : <a href="https://github.com/bayarsahintekin0/testRepo/blob/gh-pages/assets/securitykit-1.0.1.aar" target="_blank">https://github.com/bayarsahintekin0/testRepo/blob/gh-pages/assets/securitykit-1.0.1.aar</a></p> 

<p><strong>Step 4  </strong> :Add the dependency to build.gradle(app) file </p>

<pre><div id="copy-button9" class="copy-btn" title="Copy" onclick="copyCode(this.id)"></div><code>dependencies {
    
repositories { 
      flatDir { 
          dirs 'libs' 
      } 
  }  
 dependencies { 
      ...... 
      implementation (name: 'securitykit-1.0.1', ext: 'aar') 
      ...... 
 }
</code></pre>
<p><strong>Step 5</strong>: In the Android Studio window, choose <strong>File</strong> &gt; <strong>Sync Project with Gradle Files</strong> to synchronize the project.</p>
