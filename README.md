# Instruction
## Create simple HTML file (index.htm.)

```
<!DOCTYPE html>
<html>
<head>
    <title>My Freelance Project</title>
</head>
<body>
    <h1>Success! The DevOps Robot Deployed This Site.</h1>
    <p>This project proves I can automate deployments.</p>
</body>
</html>

```

## Create deploy.yaml file
In GitHub, this robot is called GitHub Actions.its job is to watch your code and follow a "To-Do List" every time you save a change. To earn a customer's trust, you show them that your robot checks the code for errors before putting it live.

directory structure: .github/workflows/deploy.yml

```
name: My First Deployment Robot

# 1. When should the robot work?
on:
  push:
    branches: [ "main" ]

# 2. What should the robot do?
jobs:
  build-and-test:
    runs-on: ubuntu-latest
    steps:
      - name: Checkout code
        uses: actions/checkout@v4

      - name: Check if file exists
        run: |
          if [ -f index.html ]; then
            echo "Success: index.html is present!"
          else
            echo "Error: index.html is missing!"
            exit 1
          fi
```

### Watch the Robot Work

Now, let's see if the robot is alive:

Click the Actions tab at the top of your GitHub page.

You should see a workflow run starting up (it might have a yellow spinning circle or a green checkmark).

Click on the name of the run ("My First Deployment Robot").

**Did you see a green checkmark appearing next to your run?** it should be green.

**Test**  Try to delete the index.html file => Expected the jobs fail - **RED CROSS SIGN** - due to missign file.



# Automated Deployment Pipeline Project
By [Bunna CHOM]

## 🎯 The Goal
To create a "Safety-First" deployment system that prevents broken code from reaching production.

## 🛠️ Tools Used
* **GitHub Actions** (Automation Robot)
* **YAML** (Configuration)
* **Bash Scripting** (Logic Checks)

## 🛡️ Trust Features
* **Auto-Testing**: The system automatically checks if core files (index.html) exist.
* **Failure Prevention**: If a file is missing, the deployment stops immediately to protect the user experience.
* **Speed**: Updates happen in under 60 seconds without human intervention.

