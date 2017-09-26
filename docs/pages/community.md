---
layout: default
title: Community Development
---

# Community

To encourage sharing and distribution of useful apps, we have developed an online interface for easily exploring and sharing SCI-F apps, and generating recipes using the apps, available at <a href="http://containers-ftw.org/apps" target="_blank">http://containers-ftw.org/apps.</a>

## Infrastructure Overview
The interface corresponds to a Github repo that renders static template files into a complete website that includes search across all content, exploration by tag, and by way of reading examples and tutorials. Programmatic access to all apps is provided with a RESTful API, as is an rss feed for interested users to be notified when new content is added. The interface also includes a “recipe generator" that allows a user to browse the site, save apps of interest in the browser’s local storage, and then combine them in a Singularity build file that can be downloaded in a compressed archive that includes instructions and any associated, required files for the app.

### Contributing
Importantly, as the infrastructure is served from a Github repository, contributing does not require any expertise with web development or related technologies. The user can simply use Github to fork the repo, add a text file to the “_apps" folder, and submit a pull request (PR) to evaluate the contribution. The text file itself has a header section that contains bulletpointed lists of metadata like name, tags, and files, and the remainder of the file is the Singularity sections for the app (e.g., “%apprun hello-world").  When the PR is approved, the contribution will automatically render into all areas of the site. If an app includes associated files like scripts or configuration, this data is also easily added into a folder named equivalently to the file, alongside it (e.g., _apps/hello-world/hello-world-bash.md would have associated files in _apps/hello-world/hello-world-bash).

### Testing
Github also allows for complete testing of all contributions, and the repository is set up with a continuous integration (CI, which means testing) service called CircleCI that checks the following:

- The file name for the app corresponds with the app’s name declared in the file
- The folder path under “_apps" also corresponds to the app’s file name. For example, an app located at _apps/hello-world/bash/ must start with “hello-world-bash". Matching app names to the folder structure ensures uniqueness of the names within the repository.
- The user has not provided any empty keys or values in the header section.
- Each declared file in the header has been provided in the repo
- The app minimally has a tag for one operating system, to help determine compatibility.
- The header date is in valid format to be rendered correctly
- Fields allowed in the header do not go beyond “author," “title," “date," “files," and “tags."
- Required fields (“author," “title," “date," and “tags" are present

Any contribution that does not meet these requirements will get feedback during the PR, and the contributor can adjust the file to address any issues. As soon as the content is merged into the master branch, it is immediately live on the site.


## Contribute to SCI-F
There are so many ways to contribute! Here are just a few:

 - [Find useful examples](https://containers-ftw.github.io/apps) and apps for your Singularity containers.
 - [Improve SCI-F](https://www.github.com/containers-ftw/SCI-F/): This entire thing is open for suggestions and changes by way of version control (Github). The organizational format will be stronger if you express your thoughts and suggest changes.
 - Contribute to the implementation in the [Singularity](https://www.github.com/singularityware/singularity.git) software.
 - [Contribute an App](https://www.github.com/containers-ftw/apps) for others to use.
 - [Ask a question](https://www.github.com/containers-ftw/SCI-F/issues), anything on your mind.


## Future Work
SCI-F is exciting because it makes basic container development and usage easier. The user can immediately inspect and see the software a container provides, and how to use it. The user can install additional software, copy from one container to another, or view metadata and help documentation. The developer is provided guidance for how and where to install and configure software, but complete freedom with regard to the software itself. The minimum requirements for any package are a name for its folder, and then optionally a runscript and help document for the user.


### Mapping of container landscape
Given separation of the software from the host, we can more easily derive features that compare software modules. These features can be used with standard unsupervised clustering to better understand how groups of software are used together. We can further apply different labels like domains and understand what modules are shared (or not shared) between scientific domains. We can find opportunity by discovering gaps, that perhaps a software module isn't used for a particular domain (and it might be).

### Artificial Intelligence (AI) Generated Containers
Given some functional goal, and given a set of containers with measurable features to achieving it, we can (either by brute force or more elegantly) programmatically generate and test containers toward some metric. The landscape of containers can easily be pruned in that the best containers for specific use cases can be easily determined automatically.