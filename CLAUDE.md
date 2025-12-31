# CLAUDE.md - AI Assistant Guide for meeting-poll

## Project Overview

**meeting-poll** is a meeting scheduling and polling application that allows users to create polls for finding optimal meeting times and gather participant availability.

> **Project Status**: Early development stage - initial setup and architecture decisions pending.

## Repository Structure

```
meeting-poll/
├── README.md          # Project overview and setup instructions
├── CLAUDE.md          # This file - AI assistant guidelines
└── (project files)    # To be added as development progresses
```

## Development Guidelines

### Getting Started

When this project is set up, the typical workflow will be:

```bash
# Install dependencies
npm install

# Start development server
npm run dev

# Run tests
npm test

# Build for production
npm run build
```

### Code Conventions

#### General Principles

1. **Keep it simple** - Prefer straightforward solutions over clever ones
2. **Be consistent** - Follow existing patterns in the codebase
3. **Document intent** - Add comments only where the "why" isn't obvious
4. **Avoid over-engineering** - Only build what's needed now

#### File Naming

- Use `kebab-case` for file names: `meeting-poll.ts`, `user-service.ts`
- React components use `PascalCase`: `MeetingCard.tsx`, `PollForm.tsx`
- Test files: `*.test.ts` or `*.spec.ts`

#### TypeScript

- Prefer interfaces over type aliases for object shapes
- Use strict type checking (`strict: true` in tsconfig)
- Avoid `any` - use `unknown` with proper type guards when needed
- Export types alongside their implementations

#### React (if applicable)

- Functional components with hooks
- Keep components focused and single-responsibility
- Colocate tests with components
- Use descriptive prop interfaces

### Git Workflow

#### Branch Naming

- Feature branches: `feature/<description>`
- Bug fixes: `fix/<description>`
- Claude AI branches: `claude/<description>-<session-id>`

#### Commit Messages

Write clear, concise commit messages:
- Use imperative mood: "Add feature" not "Added feature"
- First line: summary under 72 characters
- Body (optional): explain what and why, not how

```
Add poll creation endpoint

- Implement POST /api/polls with validation
- Add database schema for polls table
- Include unit tests for poll service
```

### Testing

#### Test Organization

```
src/
├── components/
│   ├── PollCard.tsx
│   └── PollCard.test.tsx    # Colocated unit tests
└── __tests__/               # Integration tests
    └── api/
        └── polls.test.ts
```

#### Testing Principles

1. Test behavior, not implementation
2. Prefer integration tests for API endpoints
3. Use descriptive test names that explain the scenario
4. Keep tests focused and independent

### API Design (if applicable)

- RESTful endpoints following standard conventions
- Consistent error response format
- Input validation on all endpoints
- Proper HTTP status codes

## Key Patterns and Conventions

### Error Handling

- Use typed error classes for different error categories
- Always log errors with context
- Return user-friendly error messages to clients
- Never expose sensitive information in error responses

### Security Considerations

- Validate and sanitize all user input
- Use parameterized queries for database operations
- Implement proper authentication/authorization
- Follow OWASP guidelines for common vulnerabilities

### Environment Configuration

- Use `.env` files for local development (never commit)
- Document all required environment variables in `.env.example`
- Use different configurations for dev/test/production

## Commands Reference

| Command | Description |
|---------|-------------|
| `npm install` | Install dependencies |
| `npm run dev` | Start development server |
| `npm run build` | Build for production |
| `npm test` | Run test suite |
| `npm run lint` | Run linting |
| `npm run format` | Format code with Prettier |

## Architecture Notes

### Technology Stack (Planned/Recommended)

- **Runtime**: Node.js
- **Language**: TypeScript
- **Framework**: TBD (Next.js, Express, etc.)
- **Database**: TBD (PostgreSQL, SQLite, etc.)
- **Testing**: Jest or Vitest
- **Linting**: ESLint + Prettier

### Core Concepts

- **Poll**: A survey to determine meeting availability
- **Participant**: A user responding to a poll
- **Time Slot**: A proposed date/time option in a poll
- **Response**: A participant's availability for each time slot

## AI Assistant Instructions

### When Making Changes

1. **Read before modifying** - Always read files before making changes
2. **Understand context** - Check related files and dependencies
3. **Make minimal changes** - Only change what's necessary
4. **Verify changes** - Run tests and linting after modifications
5. **Commit appropriately** - Use clear commit messages

### Common Tasks

#### Adding a New Feature

1. Understand the requirements
2. Check existing patterns in the codebase
3. Implement with tests
4. Update documentation if needed
5. Commit with clear message

#### Fixing a Bug

1. Reproduce the issue
2. Identify the root cause
3. Write a failing test
4. Fix the bug
5. Verify the test passes
6. Commit with reference to the issue

#### Refactoring

1. Ensure test coverage exists
2. Make small, incremental changes
3. Run tests after each change
4. Keep commits atomic

### Things to Avoid

- Don't add features not explicitly requested
- Don't refactor code unless asked
- Don't add excessive comments or documentation
- Don't create abstraction layers prematurely
- Don't ignore existing patterns in favor of "better" approaches

## Project-Specific Notes

### Current State

This project is in early development. As the codebase grows, this document should be updated to reflect:

- Actual project structure
- Installed dependencies and their versions
- Specific coding patterns adopted
- API documentation
- Database schema details
- Deployment procedures

### Updating This Document

Keep CLAUDE.md updated when:
- Major architectural decisions are made
- New conventions are established
- Key dependencies are added
- Important patterns emerge

---

*Last updated: December 2024*
