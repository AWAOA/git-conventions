# Customizing Your Commit Message Template

## Use `git config`  to customize

You can use the following bash file to create commit-message template.

```bash
#!/bin/bash
echo '<type>(<scope>): <subject> (<#work-item-id>)' > ~/.git-hook-prepare-commit-msg.template
echo '' >> ~/.git-hook-prepare-commit-msg.template
echo '<body>' >> ~/.git-hook-prepare-commit-msg.template
echo '' >> ~/.git-hook-prepare-commit-msg.template
echo '<footer>' >> ~/.git-hook-prepare-commit-msg.template
echo '' >> ~/.git-hook-prepare-commit-msg.template
echo '# HINT: Any line cannot be longer 72 characters!' >> ~/.git-hook-prepare-commit-msg.template
echo '# types: build, ci, docs, feat, fix, perf, refactor, style, test' >> ~/.git-hook-prepare-commit-msg.template
echo '#-------------------------------------------------------' >> ~/.git-hook-prepare-commit-msg.template
git config --global commit.template ~/.git-hook-prepare-commit-msg.template # customizing commit template

echo "SUCCESS!"

```

Use command `git commit`to get commit-message template

```wiki
<type>(<scope>): <subject> (<#work-item-id>)

<body>

<footer>

# HINT: Any line cannot be longer 72 characters!
# types: build, ci, docs, feat, fix, perf, refactor, style, test
#-------------------------------------------------------

# change message...
```

If you want to customize your template，use command `vi ~/.git-hook-prepare-commit-msg.template` add customize hints.

## Edit `.git/hooks/prepare-commit-msg`  to customize

Edit the project's `prepare-commit-msg.sample` under `.git/hooks/`, and rename it to `prepare-commit-msg` to create a custom commit template.

```bash
$ ls .git/hooks/
applypatch-msg.sample  post-update.sample     prepare-commit-msg.sample
commit-msg.sample      pre-applypatch.sample  pre-rebase.sample
post-commit.sample     pre-commit.sample      update.sample
post-receive.sample
```

For details, see [Customizing Git - Git Configuration](https://git-scm.com/book/en/v2/Customizing-Git-Git-Configuration#_code_commit_template_code)
