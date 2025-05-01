## 🔹 What is "Code Checkout" or "Git Checkout Stage"?

In a CI/CD pipeline (like Jenkins), the **"checkout" stage** refers to the step where Jenkins:

👉 **Connects to your Git repository (like GitHub, GitLab, Bitbucket, etc.)**  
👉 **Downloads (clones) the code to the Jenkins workspace** on the machine (or container) running the job

---

### 🔄 What Actually Happens During "Checkout"?

When you see something like this in a Jenkinsfile:

```groovy
stage('Checkout Code') {
  steps {
    git branch: 'main', url: 'https://github.com/username/myrepo.git'
  }
}
```

Jenkins will:
1. Connect to the GitHub repo.
2. Go to the specified branch (here, `main`).
3. Clone/download the repository contents into the Jenkins workspace.
4. Now the pipeline can **use the code** — e.g., to build, test, or deploy it.

---

## 🧠 Why is This Step Important?

Because **all other stages (like build, test, package, deploy)** need access to the **actual source code**. Without checkout, there's no code to work on!

---

## 💡 Related Git Command

The `git checkout` command on its own (in CLI) is used to:
- Switch between branches,
- Or restore files.

Example:

```bash
git checkout main  # switches to the 'main' branch
```

But in Jenkins pipeline, `checkout` = clone the code from a Git repository.

---

Would you like me to show you a full Jenkinsfile with this stage and what happens next?
