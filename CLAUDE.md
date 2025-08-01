# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This project uses Mermaid.js for creating cloud infrastructure diagrams. Diagrams are stored as `.mmd` files in the `/diagrams` folder and can be viewed/edited using the Mermaid Chart VS Code extension.

## VS Code Extension Setup

1. Install "Mermaid Chart" extension from VS Code marketplace
2. Open any `.mmd` file in the `/diagrams` folder
3. Use Command Palette → "Mermaid: Preview Diagram" to view diagrams
4. For AI-powered diagram generation: use `@mermaid-chart /generate_cloud_architecture_diagram` in GitHub Copilot Chat

## Diagram Files

- `/diagrams/getting-started.mmd` - Basic tutorial diagram
- `/diagrams/simple-examples.mmd` - Common infrastructure patterns

## Usage

- Create new `.mmd` files in `/diagrams` folder
- Use Mermaid syntax for flowcharts, architecture diagrams, sequence diagrams
- AI features require login to Mermaid Chart service