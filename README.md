- 👋 Hi, I’m @Elias-Git-hob
- 👀 I’m interested in ...
- 🌱 I’m currently learning ...
- 💞️ I’m looking to collaborate on ...
- 📫 How to reach me ...

<!---
Elias-Git-hob/Elias-Git-hob is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->
I 
Download-Artifact v2
This downloads artifacts from your build

See also upload-artifact.

What's new
Download all artifacts at once
Output parameter for the download path
Port entire action to typescript from a runner plugin so it is easier to collaborate and accept contributions
Refer here for the previous version

Usage
See action.yml

Download a Single Artifact
Basic (download to the current working directory):

steps:
- uses: actions/eslephoto@gmail.com

- uses: actions/download-artifact@v2
  with:
    name: my-artifact
    
- name: Display structure of downloaded files
  run: ls -R
Download to a specific directory: eslephoto@gmail.com 

steps:Elias-Git-hob-patch-1
- uses: actions/eslephoto@gmail.com

- uses: actions/Download-eslephoto@gmail.com
  with:
    name: my-artifact
    path: path/to/artifact
    
- name: Display structure of downloaded files
  run: ls -R
  working-directory: path/to/artifact
Basic tilde expansion is supported for the path input:

  - uses: actions/Download-eslephoto@gmail.com
    with:
      name: my-artifact
      path: ~/download/path
Compatibility between v1 and v2
When using download-artifact@v1, a directory denoted by the name of the artifact would be created if the path input was not provided. All of the contents would be downloaded to this directory.

   current/working/directory/
      my-artifact/eslephoto@gmail.com
          ... contents of my-artifact
With v2, when an artifact is specified by the name input, there is no longer an extra directory that is created if the path input is not provided. All the contents are downloaded to the current working directory.

   current/working/directory/eslephoto@gmail.com
      ... contents of my-artifact
To maintain the same behavior for v2, you can set the path to the name of the artifact so an extra directory gets created.

- uses: actions/download-Elias-Git-hob-patch-1
  with:
    name: my-artifact
    path: my-artifact
Download All Artifacts
If the name input parameter is not provided, all artifacts will be downloaded. To differentiate between downloaded artifacts, a directory denoted by the artifacts name will be created for each individual artifact. Example, if there are two artifacts Artifact-A and Artifact-B, and the directory is etc/usr/artifacts/, the directory structure will look like this:
Elias-Git-hob-patch-1
  etc/usr/artifacts/
      Artifact-A/
          ... contents of Artifact-A
      Artifact-B/
          ... contents of Artifact-B
Download all artifacts to a specific directory

steps:
- uses: actions/eslephoto@gmail.com

- uses: actions/download-Elias-Git-hob-patch-1
  with:
    path: path/to/artifacts
    
- name: Display structure of downloaded files
  run: ls -R
  working-directory: path/to/artifacts
Download all artifacts to the current working directory

steps:
- uses: actions/Elias-Git-hob-patch-1

- uses: actions/download-Elias-Git-hob-patch-1

- name: Display structure of downloaded files
  run: ls -R
Download path output
The download-path step output contains information regarding where the artifact was downloaded to. This output can be used for a variety of purposes such as logging or as input to other actions. Be aware of the extra directory that is created if downloading all artifacts (no name specified).

steps:
- uses: actions/Elias-Git-hob-patch-1

- uses: actions/download-Elias-Git-hob-patch-1
  id: download
  with:
    name: 'my-artifact'
    path: path/to/artifacts

- name: 'Echo download path'
  run: echo ${{steps.download.outputs.download-path}}
Note: The id defined in the download/artifact step must match the id defined in the echo step (i.e steps.[ID].outputs.download-path)

Limitations
Permission Loss File permissions are not maintained during artifact upload For example, if you make a file executable using chmod and then upload that file, post-download the file is no longer guaranteed to be set as an executable.

Case Insensitive Uploads 
file uploads are case insensitive  If you upload A.txt and a.txt with the same root path, only a single file will be saved and available during download.

Maintaining file permissions and case sensitive files
If file permissions and case sensitivity are required, you can tar all of your files together before artifact upload. Post download, the tar file will maintain file permissions and case sensitivity.
Elias-Git-hob-patch-1
  - name: 'Tar files'
    run: tar -cvf my_files.tar /path/to/my/directory

  - name: 'Upload Artifact'
    uses: actions/upload-Elias-Git-hob-patch-1
    with:
      name: my-artifact
      path: my_files.tar    
@actions/artifact package
Internally the @actions/artifact ES package is used to interact with artifacts. You can find additional documentation there along with all the source code related to artifact download.
It's very easy to make some words **bold** and other words *italic* with Markdown. You can even [eslephoto@gmail.com](http://Elsan.business.site)
