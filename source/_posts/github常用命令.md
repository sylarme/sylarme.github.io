---
title: github常用命令
date: 2025-03-20 12:42:44
tags:git
---
1. 初始化 & 克隆仓库
git init：初始化本地仓库
git clone <仓库URL>：克隆远程仓库到本地（默认克隆 main/master 分支）
bash
git clone https://github.com/user/repo.git
​2. 提交更改
git add <文件名>：添加单个文件到暂存区
bash
git add index.html
git add .：添加所有修改的文件到暂存区
git commit -m "提交说明"：提交暂存区的文件到本地仓库
bash
git commit -m "修复登录页面样式"
​3. 分支管理
git branch：查看本地所有分支
git branch <分支名>：创建新分支
bash
git branch feature-login
git checkout <分支名>：切换到指定分支
bash
git checkout main
git checkout -b <新分支名>：创建并切换到新分支
bash
git checkout -b hotfix-header
git merge <分支名>：将指定分支合并到当前分支
bash
git merge feature-login
git rebase <分支名>：变基操作（常用于整理提交历史）
​4. 远程仓库操作
git remote add origin <仓库URL>：关联远程仓库
bash
git remote add origin https://github.com/user/repo.git
git push origin <分支名>：推送本地分支到远程仓库
bash
git push origin main
git pull origin <分支名>：拉取远程分支并合并到当前分支
bash
git pull origin dev
git fetch origin：获取远程仓库最新改动（不自动合并）
​5. 撤销操作
git reset --hard HEAD^：撤销最近一次提交及所有修改
git checkout -- <文件名>：撤销单个文件的修改
bash
git checkout -- style.css
git revert <commit_id>：撤销指定提交（生成新的反向提交）
​6. 查看状态与历史
git status：查看工作区与暂存区状态
git log：查看提交历史（按 q 退出）
git log --oneline：简洁模式查看提交历史
git diff：查看未暂存的修改内容
​7. 标签管理
git tag：查看所有标签
git tag v1.0.0：创建轻量标签
git tag -a v1.0.0 -m "版本说明"：创建带注释的标签
git push origin --tags：推送所有标签到远程仓库
​8. 协作相关（GitHub流程）​
​同步 Fork 的仓库：
bash
git remote add upstream <原仓库URL>  # 添加上游仓库
git fetch upstream                   # 获取上游更新
git merge upstream/main             # 合并到本地分支
git push origin main                # 推送到自己的远程仓库
​拉取他人 PR 到本地测试：
bash
git fetch origin pull/PR编号/head:本地分支名  
git checkout 本地分支名
​GitHub CLI 工具 (gh 命令)
gh repo clone <仓库名>：克隆仓库（无需输入完整URL）
gh pr create：交互式创建 PR
gh issue list：查看仓库的 Issue 列表
gh repo fork：Fork 远程仓库
