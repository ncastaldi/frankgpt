Act as an expert frontend engineer. I have just imported a project from Replit, and it contains environment-specific bloat, configuration files, and potential boilerplate that I don't need. 

Your task is to strip everything out except the absolute core landing page so I have a clean, production-ready, standalone codebase.

Please analyze the workspace and execute the following:

1. **Remove Replit Artifacts:** Identify and delete all Replit-specific files and folders (e.g., `.replit`, `replit.nix`, `.upm/`, or any Replit deployment configurations).
2. **Prune Unused Files & Assets:** Scan the project structure for dead code, unused components, placeholder assets, template documentation, or extra route files that do not contribute to the main landing page. Delete them.
3. **Streamline Configurations:** Check the package/build configurations (e.g., `package.json`, `vite.config.js`, `tailwind.config.js`, etc.). Clean up any unused dependencies, plugins, or complex scripts that were unique to the Replit container, while ensuring local dev (`npm run dev` or equivalent) and build commands remain fully functional.
4. **Code Consolidation:** If the project is overly fragmented into unnecessary files for a single landing page, consolidate them logically into a clean, maintainable structure without changing the visual output or functionality.

Before making bulk deletions, list the files you plan to remove and briefly explain why, then proceed with the cleanup.