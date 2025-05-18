# Contributing to Sanskrit Programming Language

[![License](https://img.shields.io/badge/license-MIT-blue.svg)](LICENSE)
[![Contributors](https://img.shields.io/github/contributors/Yantrika-Programming-language/Yantrika.svg)](https://github.com/Yantrika-Programming-language/Yantrika/graphs/contributors)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](http://makeapullrequest.com)

*"सर्वे भवन्तु सुखिनः" - May all be happy*

Thank you for your interest in contributing to the Sanskrit Programming Language! This project aims to bridge ancient wisdom with modern technology, creating a programming language that honors Sanskrit's rich heritage while providing contemporary programming capabilities.

## Table of Contents

- [Code of Conduct](#code-of-conduct)
- [Ways to Contribute](#ways-to-contribute)
- [Getting Started](#getting-started)
- [Development Setup](#development-setup)
- [Contribution Guidelines](#contribution-guidelines)
- [Pull Request Process](#pull-request-process)
- [Issue Guidelines](#issue-guidelines)
- [Documentation Contributions](#documentation-contributions)
- [Translation and Localization](#translation-and-localization)
- [Community Involvement](#community-involvement)
- [Recognition](#recognition)

## Code of Conduct

### Our Pledge

In the spirit of "वसुधैव कुटुम्बकम्" (Vasudhaiva Kutumbakam - the world is one family), we pledge to make participation in our project a harassment-free experience for everyone, regardless of age, body size, disability, ethnicity, gender identity and expression, level of experience, nationality, personal appearance, race, religion, or sexual identity and orientation.

### Our Standards

**Positive behaviors include:**
- Using welcoming and inclusive language
- Being respectful of differing viewpoints and experiences
- Gracefully accepting constructive criticism
- Focusing on what is best for the community
- Showing empathy towards other community members
- Honoring Sanskrit's cultural significance with respect

**Unacceptable behaviors include:**
- Harassment, discrimination, or offensive language
- Personal attacks or inflammatory comments
- Cultural appropriation or disrespectful use of Sanskrit terms
- Spam, trolling, or deliberately disruptive behavior
- Publishing others' private information without permission

### Enforcement

Instances of abusive, harassing, or otherwise unacceptable behavior may be reported by contacting the project team at conduct@sanskrit-lang.org. All complaints will be reviewed and investigated promptly and fairly.

## Ways to Contribute

### 🧑‍💻 Code Contributions
- **Core Compiler**: Lexer, parser, semantic analysis, code generation
- **Standard Library**: Built-in functions and modules
- **Tooling**: IDE plugins, debugger, formatter, package manager
- **Build System**: CMake improvements, CI/CD enhancements
- **Performance**: Optimization and benchmarking

### 📚 Documentation
- **Technical Documentation**: API docs, architecture guides
- **User Guides**: Tutorials, examples, best practices
- **Language Reference**: Grammar specification, standard library docs
- **Cultural Context**: Sanskrit language background, terminology explanations

### 🌍 Translation & Localization
- **Error Messages**: Translate compiler errors to various languages
- **Documentation**: Localize guides and tutorials
- **Website**: Multi-language support for project website
- **Comments**: Sanskrit code comments and examples

### 🧪 Testing & Quality Assurance
- **Unit Tests**: Test individual components
- **Integration Tests**: End-to-end testing
- **Performance Tests**: Benchmarking and profiling
- **Platform Testing**: Cross-platform compatibility
- **Security**: Vulnerability testing and reporting

### 🎨 Design & User Experience
- **Logo and Branding**: Visual identity design
- **Website Design**: User interface improvements
- **IDE Integration**: Syntax highlighting, themes
- **Documentation Layout**: Improved readability and navigation

### 🗣️ Community Building
- **Mentoring**: Help newcomers get started
- **Events**: Organize meetups, workshops, conferences
- **Content Creation**: Blog posts, videos, presentations
- **Feedback**: User experience insights and suggestions

## Getting Started

### Prerequisites

Before contributing, ensure you have:

- **Git**: Version control system
- **C/C++ Compiler**: GCC 9+ or Clang 10+
- **CMake**: Build system (3.16+)
- **ICU Library**: Unicode and internationalization support
- **Basic Sanskrit Knowledge**: Helpful but not required (we'll help you learn!)

### First Steps

1. **Join the Community**
   - Join our [Discord server](https://discord.gg/sanskrit-lang)
   - Subscribe to our [mailing list](mailto:sanskrit-dev@lists.example.com)
   - Follow us on [Twitter](https://twitter.com/SanskritLang)

2. **Explore the Project**
   - Read the [README](README.md)
   - Browse the [documentation](https://docs.sanskrit-lang.org)
   - Check out [example programs](examples/)

3. **Find Your First Contribution**
   - Look for [good first issues](https://github.com/Yantrika-Programming-language/Yantrika/labels/good%20first%20issue)
   - Check [help wanted](https://github.com/Yantrika-Programming-language/Yantrika/labels/help%20wanted) issues
   - Ask in Discord #development channel

## Development Setup

### Environment Setup

#### Using Nix (Recommended)

```bash
# Clone the repository
git clone https://github.com/Yantrika-Programming-language/Yantrika.git
cd sanskrit-compiler

# Enter development environment
nix develop

# Build the project
make build

# Run tests
make test
```

#### Manual Setup

**Ubuntu/Debian:**
```bash
# Install dependencies
sudo apt update
sudo apt install build-essential cmake git libicu-dev valgrind

# Clone and build
git clone https://github.com/Yantrika-Programming-language/Yantrika.git
cd sanskrit-compiler
mkdir build && cd build
cmake ..
make -j$(nproc)
```

**macOS:**
```bash
# Install dependencies
brew install cmake icu4c

# Clone and build
git clone https://github.com/Yantrika-Programming-language/Yantrika.git
cd sanskrit-compiler
mkdir build && cd build
cmake ..
make -j$(sysctl -n hw.ncpu)
```

### Development Workflow

```bash
# Create feature branch
git checkout -b feature/your-feature-name

# Make changes
# ... edit files ...

# Build and test
make build
make test

# Commit changes
git add .
git commit -m "feat: add your feature description"

# Push and create PR
git push origin feature/your-feature-name
```

### Dev Tools Setup

**VS Code Extensions:**
```bash
# Install Sanskrit language support
code --install-extension sanskrit-lang.sanskrit-support

# Recommended extensions
code --install-extension ms-vscode.cpptools
code --install-extension ms-vscode.cmake-tools
code --install-extension vadimcn.vscode-lldb
```

**Vim/Neovim:**
```vim
" Add to your vimrc
Plug 'sanskrit-lang/vim-sanskrit'
```

## Contribution Guidelines

### Code Style

#### C/C++ Code

**General Principles:**
- Follow the [Google C++ Style Guide](https://google.github.io/styleguide/cppguide.html) with Sanskrit-specific modifications
- Use descriptive variable names
- Comment complex logic
- Prefer readability over cleverness

**Naming Conventions:**
```c
// Functions: snake_case with module prefix
int scanner_get_token(Scanner* scanner);
bool parser_parse_expression(Parser* parser);

// Types: PascalCase
typedef struct Scanner Scanner;
typedef enum TokenType TokenType;

// Constants: UPPER_SNAKE_CASE
#define MAX_IDENTIFIER_LENGTH 256
#define SANSKRIT_VERSION_MAJOR 1

// Variables: snake_case
int current_line;
char* token_text;
```

**File Organization:**
```c
// file_header.c
#include "config.h"
#include "sanskrit.h"

#include <stdlib.h>
#include <string.h>

// Constants and macros
#define BUFFER_SIZE 1024

// Type definitions
typedef struct {
    // ...
} LocalStruct;

// Static function declarations
static bool validate_input(const char* input);

// Global function implementations
ReturnType public_function(ParamType param) {
    // Implementation
}

// Static function implementations
static bool validate_input(const char* input) {
    // Implementation
}
```

#### Sanskrit Code Style

**Basic Principles:**
- Use meaningful Sanskrit terms for identifiers
- Maintain consistency with existing terminology
- Include transliteration comments for clarity
- Respect Sanskrit grammatical rules

**Example:**
```sanskrit
// Good: Descriptive and culturally appropriate
कार्य गणना_करें(प्रथम_संख्या: पूर्णक, द्वितीय_संख्या: पूर्णक) -> पूर्णक {
    प्रत्यावर्तन प्रथम_संख्या + द्वितीय_संख्या;
}

// Avoid: Generic or inappropriate terms
कार्य func(a: पूर्णक, b: पूर्णक) -> पूर्णक {
    प्रत्यावर्तन a + b;
}
```

### Git Commit Guidelines

We follow [Conventional Commits](https://www.conventionalcommits.org/) specification:

**Format:**
```
<type>[optional scope]: <description>

[optional body]

[optional footer(s)]
```

**Types:**
- `feat`: New feature
- `fix`: Bug fix
- `docs`: Documentation only changes
- `style`: Formatting, missing semicolons, etc.
- `refactor`: Code change that neither fixes a bug nor adds a feature
- `perf`: Performance improvements
- `test`: Adding missing tests
- `chore`: Changes to build process or auxiliary tools

**Examples:**
```bash
feat(parser): add support for array literals

fix(scanner): handle Unicode combining characters correctly

docs(api): update function documentation with examples

test(integration): add compiler end-to-end tests

chore(deps): update ICU library to latest version
```

### Testing Requirements

All contributions must include appropriate tests:

**Unit Tests:**
```c
// test_scanner.c
#include "test_framework.h"
#include "scanner.h"

TEST(scanner_tokenizes_devanagari_numbers) {
    Scanner* scanner = scanner_create("१२३");
    Token* token = scanner_next_token(scanner);
    
    ASSERT_EQ(TOKEN_INTEGER, token->type);
    ASSERT_EQ(123, token->value.integer);
    
    token_free(token);
    scanner_destroy(scanner);
}
```

**Integration Tests:**
```bash
# Test files in tests/integration/
# test_basic_program.sans
कार्य मुख्य() -> शून्य {
    मुद्रण("परीक्षण सफल");
}
```

### Documentation Standards

**Code Documentation:**
```c
/**
 * @brief Scans the next token from source
 * 
 * This function processes Devanagari and ASCII input,
 * handling Unicode normalization and combining characters.
 * 
 * @param scanner Scanner instance
 * @return Next token or NULL on error
 * 
 * @note Returned token must be freed with token_free()
 * @see token_free(), scanner_create()
 */
Token* scanner_next_token(Scanner* scanner);
```

**API Documentation:**
- Use Doxygen-style comments
- Include parameter descriptions
- Provide usage examples
- Document error conditions
- Reference related functions

**User Documentation:**
- Write in clear, simple language
- Include code examples
- Provide cultural context for Sanskrit terms
- Test all examples for accuracy

## Pull Request Process

### Before Submitting

1. **Check Requirements:**
   - [ ] Code follows style guidelines
   - [ ] Tests pass locally (`make test`)
   - [ ] Documentation is updated
   - [ ] Commit messages follow convention
   - [ ] No merge conflicts with main branch

2. **Self-Review:**
   - [ ] Review your own changes first
   - [ ] Remove debug code and comments
   - [ ] Verify examples work correctly
   - [ ] Check for potential performance issues

### Submitting a PR

1. **Create Pull Request:**
   - Use descriptive title
   - Fill out PR template completely
   - Link related issues
   - Add screenshots for UI changes

2. **PR Template:**
   ```markdown
   ## Description
   Brief description of changes and motivation.

   ## Type of Change
   - [ ] Bug fix (non-breaking change fixing an issue)
   - [ ] New feature (non-breaking change adding functionality)
   - [ ] Breaking change (fix or feature causing existing functionality to break)
   - [ ] Documentation update

   ## Testing
   - [ ] Unit tests pass
   - [ ] Integration tests pass
   - [ ] Manual testing completed
   - [ ] Performance tested (if applicable)

   ## Documentation
   - [ ] Code comments updated
   - [ ] API documentation updated
   - [ ] User guides updated (if applicable)
   - [ ] CHANGELOG.md updated

   ## Cultural Considerations
   - [ ] Sanskrit terms used appropriately
   - [ ] Cultural context preserved
   - [ ] Transliterations provided where helpful

   ## Related Issues
   Closes #issue_number
   Related to #issue_number
   ```

### Review Process

1. **Automated Checks:**
   - CI builds on all platforms
   - Test suite execution
   - Code style verification
   - Documentation build

2. **Human Review:**
   - Code quality and correctness
   - Cultural appropriateness
   - Documentation clarity
   - Test coverage

3. **Approval Requirements:**
   - At least one maintainer approval
   - All CI checks passing
   - No requested changes pending
   - Squash commits if requested

## Issue Guidelines

### Reporting Bugs

Use the bug report template:

```markdown
**Bug Description**
Clear and concise description of the bug.

**Steps to Reproduce**
1. Step one
2. Step two
3. ...

**Expected Behavior**
What should happen.

**Actual Behavior**
What actually happens.

**Environment**
- OS: [e.g., Ubuntu 22.04]
- Sanskrit version: [e.g., 0.1.0]
- Compiler: [e.g., GCC 11.2]

**Code Sample**
```sanskrit
// Minimal reproducible example
कार्य मुख्य() -> शून्य {
    // Problem code here
}
```

**Additional Context**
Any other relevant information.
```

### Feature Requests

```markdown
**Feature Description**
Clear description of the proposed feature.

**Motivation**
Why is this feature needed? What problem does it solve?

**Detailed Design**
How should this feature work? Include examples.

**Cultural Considerations**
How does this feature relate to Sanskrit concepts?

**Implementation Ideas**
Any thoughts on implementation approach.

**Alternatives Considered**
Other solutions you've considered.
```

### Cultural Sensitivity Issues

For issues related to cultural appropriateness:

```markdown
**Cultural Concern**
Description of the cultural issue.

**Context**
Background information and Sanskrit linguistic context.

**Proposed Solution**
How should this be addressed?

**Sanskrit Expertise**
Your background with Sanskrit (helps us understand perspective).
```

## Documentation Contributions

### Types of Documentation

1. **Technical Documentation:**
   - API references
   - Architecture guides
   - Build instructions
   - Troubleshooting guides

2. **User Documentation:**
   - Language tutorials
   - Example programs
   - Best practices
   - Migration guides

3. **Cultural Documentation:**
   - Sanskrit terminology explanations
   - Historical context
   - Linguistic background
   - Cultural significance

### Writing Guidelines

**General Principles:**
- Write for your audience (beginners vs. experts)
- Use clear, concise language
- Provide practical examples
- Include cultural context when relevant

**Structure:**
```markdown
# Title

## Overview
Brief introduction and purpose.

## Prerequisites
What readers need to know beforehand.

## Main Content
### Subsection 1
Content with code examples.

### Subsection 2
More content.

## Examples
Practical examples and use cases.

## See Also
Related documentation links.
```

**Sanskrit Terms:**
- Always provide transliteration
- Explain cultural context
- Use consistent terminology
- Create a glossary for complex terms

## Translation and Localization

### Supported Languages

**Current:**
- English (primary)
- हिंदी (Hindi)
- ગુજરાતી (Gujarati)
- தமிழ் (Tamil)

**Planned:**
- বাংলা (Bengali)
- తెలుగు (Telugu)
- ಕನ್ನಡ (Kannada)
- മലയാളം (Malayalam)
- मराठी (Marathi)

### Translation Process

1. **Join Translation Team:**
   - Sign up on our [Crowdin project](https://crowdin.com/project/sanskrit-lang)
   - Join relevant language channel on Discord
   - Review existing translations

2. **Translation Guidelines:**
   - Maintain technical accuracy
   - Preserve cultural context
   - Use appropriate formality level
   - Consult with native speakers

3. **Review Process:**
   - Native speaker review required
   - Technical accuracy verification
   - Cultural appropriateness check
   - Integration testing

### Priority Content for Translation

1. **High Priority:**
   - Compiler error messages
   - Core documentation
   - Installation guides
   - Getting started tutorial

2. **Medium Priority:**
   - API documentation
   - Advanced tutorials
   - Example programs
   - FAQ

3. **Low Priority:**
   - Blog posts
   - Community content
   - Historical documents

## Community Involvement

### Communication Channels

**Discord Server:** [discord.gg/sanskrit-lang](https://discord.gg/sanskrit-lang)
- `#general` - General discussion
- `#development` - Technical discussions
- `#help` - Getting help with code
- `#documentation` - Documentation discussions
- `#translation` - Localization efforts
- `#cultural` - Sanskrit language and culture
- `#events` - Community events

**Mailing Lists:**
- `sanskrit-dev@lists.example.com` - Development discussions
- `sanskrit-announce@lists.example.com` - Announcements

**Social Media:**
- Twitter: [@SanskritLang](https://twitter.com/SanskritLang)
- Reddit: [r/SanskritProgramming](https://reddit.com/r/SanskritProgramming)

### Events and Meetups

**Regular Events:**
- Weekly office hours (Fridays, 3 PM UTC)
- Monthly community calls (First Thursday)
- Quarterly contributor meetings

**Annual Events:**
- SanskritConf (Annual conference)
- Summer of Code mentoring
- Hacktoberfest participation

**Local Meetups:**
To start a local meetup:
1. Contact community@sanskrit-lang.org
2. Find 3+ local members
3. Plan first event
4. Receive startup support and resources

### Mentorship Program

**For Mentees:**
- Get paired with experienced contributor
- Work on curated beginner issues
- Receive code review and guidance
- Graduate to independent contribution

**For Mentors:**
- Help newcomers get started
- Share your expertise
- Guide technical decisions
- Build the community

**Application Process:**
1. Fill out application form
2. Attend orientation session
3. Get matched with mentor/mentee
4. Begin 8-week program
5. Graduation and recognition

## Recognition

### Contributor Benefits

**All Contributors:**
- Listed in project credits
- Access to contributor Discord channels
- Early access to new features
- Sanskrit programming language swag

**Regular Contributors:**
- Invitation to contributor meetings
- Input on project roadmap
- Speaking opportunities at events
- Reference letters for employment

**Core Contributors:**
- Commit access to repositories
- Project decision-making input
- Conference travel support
- Direct line to maintainers

### Awards and Recognition

**Monthly Recognition:**
- Contributor of the Month
- Documentation Hero
- Bug Hunter
- Community Builder

**Annual Awards:**
- Outstanding Contributor
- Innovation Award
- Cultural Ambassador
- Lifetime Achievement

### Contribution Tracking

We track contributions across:
- Code commits and PRs
- Documentation improvements
- Issue reports and triage
- Community support and mentoring
- Event organization
- Translation efforts

## Getting Help

### Before Asking for Help

1. Check existing documentation
2. Search previous issues and discussions
3. Try the minimal reproduction
4. Gather relevant information

### Where to Get Help

**Technical Issues:**
- Discord #development channel
- GitHub Discussions
- Stack Overflow (tag: sanskrit-lang)

**Cultural Questions:**
- Discord #cultural channel
- Mailing list cultural discussions
- Academic partnerships

**Career and Learning:**
- Discord #careers channel
- Mentorship program
- Community networking events

### How to Ask for Help

**Good Question Format:**
```markdown
**Context:** What are you trying to accomplish?
**Problem:** What specific issue are you facing?
**Environment:** OS, versions, installation method
**Code:** Minimal example that reproduces the issue
**Attempted Solutions:** What you've already tried
**Expected Outcome:** What you think should happen
```

## Conclusion

Contributing to Sanskrit Programming Language is more than just writing code—it's about participating in a cultural bridge between ancient wisdom and modern technology. Whether you're fixing a small bug, translating documentation, or sharing your cultural knowledge, every contribution helps make programming more inclusive and culturally rich.

### Next Steps

1. **Join the Community:** Connect with us on Discord
2. **Choose Your Path:** Pick a contribution area that interests you
3. **Start Small:** Begin with good first issues
4. **Grow Together:** Help others as you learn and grow

### Contact

- **General Questions:** hello@sanskrit-lang.org
- **Technical Issues:** dev@sanskrit-lang.org
- **Cultural Concerns:** cultural@sanskrit-lang.org
- **Security Issues:** security@sanskrit-lang.org

---

*"आत्मानं विद्धि" - Know thyself*

Thank you for contributing to preserving and advancing Sanskrit through modern technology. Together, we're building something that honors the past while embracing the future.

---

**License:** By contributing to this project, you agree that your contributions will be licensed under the project's [MIT License](LICENSE).

**Code of Conduct:** All contributors are expected to abide by our [Code of Conduct](CODE_OF_CONDUCT.md).

*Last updated: [Current Date] | Version: 1.0 | [Edit this page](https://github.com/Yantrika-Programming-language/Yantrika/edit/main/CONTRIBUTING.md)*
