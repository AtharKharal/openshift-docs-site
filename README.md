# OpenShift Docs Site (Multi-Repo, Multi-Version Documentation Portal)

This repository serves as the orchestration layer for a structured, scalable documentation portal built with **Antora**, using the **Docs-as-Code** approach. It aggregates content from multiple versioned component repositories and generates a unified static site using AsciiDoc, Git, and a custom UI bundle.

## Overview

- **Framework**: Antora 3.x (CLI + Site Generator)
- **Markup**: AsciiDoc (modularized per component)
- **Version Control**: Git (multi-branch strategy for content versioning)
- **Publishing**: Generates static HTML content
- **UI Layer**: Custom Antora UI bundle (Handlebars templating)
- **Hosting**: Static site ready for GitHub Pages or CI/CD pipeline deployment

## Architecture

This project follows Red Hat–style documentation architecture with the following characteristics:

- Multiple documentation components (e.g., Networking, Security, Core)
- Each component resides in its own Git repository
- Each component supports versioned content (e.g., `4.13`, `4.14`)
- Aggregated using a centralized `antora-playbook.yml` file

## Repository Layout

```bash
openshift-docs-site/
├── antora-playbook.yml         # Master playbook to orchestrate content
├── site-generator/             # Build scripts, Antora CLI context
├── public/                     # Generated HTML output
├── antora-ui-bundle/           # UI bundle (externalized for reuse)
├── ocp-networking-docs/        # Networking component repo (local clone)
├── ocp-security-docs/          # Security component repo (local clone)
├── openshift-docs/             # Core documentation component (local clone)
