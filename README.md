# Project Setup and Environment Management

This guide explains how to set up the project, manage the Conda environment, and ensure consistency when adding or updating dependencies. Follow these steps to get started and collaborate effectively.

---

## Setting Up the Project

1. **Clone the Repository:**
   ```bash
   git clone https://github.com/your-username/your-repo-name.git
   ```

2. **Navigate to the Project Directory:**
   ```bash
   cd your-repo-name
   ```

3. **Create the Conda Environment:**
   Recreate the environment from the provided `environment.yml` file:
   ```bash
   conda env create --file environment.yml
   ```

4. **Activate the Environment:**
   ```bash
   conda activate my_env_name
   ```
   Replace `my_env_name` with the name specified in `environment.yml`.

---

## Adding New Packages

If you need to install a new package:

1. **Install the Package:**
   ```bash
   conda install package_name
   ```
   Or, if using pip:
   ```bash
   pip install package_name
   ```

2. **Update the `environment.yml` File:**
   Export the updated environment to the `environment.yml` file:
   ```bash
   conda env export --no-builds > environment.yml
   ```

3. **Commit the Changes:**
   Add and commit the updated `environment.yml` file:
   ```bash
   git add environment.yml
   git commit -m "Update environment.yml to include package_name"
   ```

4. **Push the Changes to GitHub:**
   ```bash
   git push origin main
   ```

---

## Updating the Environment (For Others)

When someone updates the `environment.yml` file, you need to:

1. **Pull the Latest Changes:**
   ```bash
   git pull origin main
   ```

2. **Update Your Environment:**
   Update your existing Conda environment with the new packages:
   ```bash
   conda env update --file environment.yml
   ```

---

## Best Practices

- Always export and update the `environment.yml` file when adding or removing packages.
- Use clear and descriptive commit messages for changes to the environment.
- Avoid committing the actual Conda environment directory (e.g., `my_local_env`).
- If using pip for package installation, make sure to document the changes in `environment.yml`.

---

By following this workflow, we can ensure consistency and reproducibility across all team members' setups.
