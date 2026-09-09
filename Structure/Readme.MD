# Terraform File Structure

This folder explains how to organize a small Terraform project.

## Files in This Folder

- [Terraform File Structure](Terraform%20file%20structure.md): A simple example project layout.
- [File Structure Explanation](File%20structure%20Explanation.md): The purpose of each common Terraform file.
- [Use Case of File Structure](Use%20case%20of%20file%20structure.md): When and why to use separate files.

## Basic Idea

Terraform reads all `.tf` files in the same folder as one configuration. You can split the configuration into different files to keep it easy to read. The file names do not change how Terraform works; the blocks inside the files are what matter.
