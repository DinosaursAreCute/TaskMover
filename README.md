# TaskMover

**Intelligent File Organization System with Pattern-Based Rules**

TaskMover is an advanced file organization tool that uses intelligent pattern matching and rule-based systems to automatically organize your files. Built with AI-assisted development, it features a sophisticated backend with conflict resolution, pattern suggestions, and comprehensive logging.

## 🎉 Latest Update: Pattern System Backend Complete!

**Date**: June 29, 2025  
**Status**: ✅ Backend implementation for the Pattern System is now complete and production-ready!

### ✅ What's New in This Release
- 🏗️ **Complete Backend Implementation**: Full unified Pattern System according to technical specification v3.0
- 🧠 **Intelligent Pattern Parser**: Advanced parsing that translates user-friendly input to optimized queries
- ⚡ **Unified Pattern Matching**: Single matching engine handling glob-like patterns with SQL-like power
- 🤖 **Context-Aware Suggestions**: Workspace analysis and intelligent pattern auto-completion
- 🔧 **Advanced Conflict Resolution**: Comprehensive conflict detection with multiple resolution strategies
- 📊 **Performance Optimization**: Multi-level caching system for handling large file sets
- 🎯 **Clean Architecture**: SOLID principles with dependency injection and interface-based design
- ✅ **Full Test Coverage**: 65+ comprehensive tests with 100% pass rate
- 📝 **Comprehensive Logging**: Structured logging with configurable output and detailed error tracking

### 🚧 Current Development Status
- ✅ **Backend**: Pattern System fully implemented and tested (COMPLETE)
- 🔄 **Frontend**: UI integration and visual builder (next phase)
- ⏳ **Integration**: Backend/frontend integration (upcoming)

## 🚀 Quick Start

### Prerequisites
- Python 3.11+
- Windows (primary platform, cross-platform support planned)

### Installation
```bash
# Clone the repository
git clone https://github.com/yourusername/TaskMover.git
cd TaskMover

# Install dependencies
pip install -r requirements.txt

# Run the application
python -m taskmover
```

### Running Tests
```bash
# Run all tests
python -m pytest tests/ -v

# Run specific test suites
python -m pytest tests/integration/ -v  # Integration tests
python -m pytest tests/unit/ -v        # Unit tests
```

## 📖 Documentation

### Core Documentation
- **[User Guide](docs/USER_GUIDE.md)**: How to use TaskMover effectively
- **[API Reference](docs/API_REFERENCE.md)**: Complete backend API documentation
- **[Architecture Overview](docs/ARCHITECTURE.md)**: System design and architecture
- **[Contributing Guide](docs/CONTRIBUTING.md)**: How to contribute to the project

### Technical Documentation
- **[Pattern System Technical Spec](docs/Architechture/PatternSystem_TechnicalSpecification_v3.md)**: Complete technical specification
- **[Backend Implementation](docs/Architechture/PatternSystem_BACKEND_COMPLETE.md)**: Implementation details and status
- **[Conflict Resolution](docs/Architechture/ConflictResolution.md)**: Conflict handling system design
- **[Logging System](docs/Architechture/LoggingSystem.md)**: Logging architecture and configuration

## 🏗️ Architecture Overview

TaskMover is built with a clean, modular architecture:

```
taskmover/
├── core/                      # Core business logic
│   ├── patterns/             # Pattern system (COMPLETE)
│   │   ├── models/          # Data models and structures
│   │   ├── parsing/         # Intelligent pattern parsing
│   │   ├── matching/        # Unified pattern matching
│   │   ├── storage/         # Pattern storage and caching
│   │   ├── suggestions/     # Context-aware suggestions
│   │   └── validation/      # Pattern validation
│   ├── conflict_resolution/ # Conflict handling (COMPLETE)
│   ├── logging/            # Structured logging (COMPLETE)
│   ├── di/                 # Dependency injection (COMPLETE)
│   └── settings/           # Configuration management
├── ui/                      # User interface components
└── tests/                   # Comprehensive test suite
    ├── integration/         # Integration tests
    ├── unit/               # Unit tests
    └── fixtures/           # Test data and fixtures
```

## 🎯 Key Features

### ✅ Implemented (Backend)
- **Intelligent Pattern Parsing**: Natural language-like pattern expressions
- **Unified Matching Engine**: Single system handling multiple pattern types
- **Advanced Conflict Resolution**: Multiple strategies with user interaction
- **Context-Aware Suggestions**: Intelligent auto-completion based on workspace analysis
- **Performance Optimization**: Multi-level caching for large file operations
- **Comprehensive Logging**: Structured logging with configurable output
- **Clean Architecture**: SOLID principles with full dependency injection
- **Extensive Testing**: 65+ tests covering all functionality

### 🔄 In Development (Frontend)
- **Visual Pattern Builder**: Drag-and-drop pattern construction
- **Real-time Preview**: Live preview of pattern matching results
- **Interactive Conflict Resolution**: GUI for handling file conflicts
- **Pattern Library**: Pre-built patterns for common use cases
- **Workspace Integration**: Seamless integration with file explorers

## 🧪 Development Philosophy

TaskMover serves as a showcase for effective AI-assisted development using tools like:
- **GitHub Copilot**: Code completion and suggestion
- **Claude Sonnet**: Architecture design and complex problem solving

### Development Principles
- 🎯 **High Code Quality**: Comprehensive testing and documentation
- 🏗️ **Clean Architecture**: SOLID principles and separation of concerns
- 📝 **Comprehensive Documentation**: Every component thoroughly documented
- 🔄 **Iterative Improvement**: Continuous refactoring and enhancement
- 🤖 **AI-Assisted Development**: Leveraging AI tools effectively

## 📊 Project Status

### Completed ✅
- Core backend architecture and implementation
- Pattern system with intelligent parsing and matching
- Conflict resolution system with multiple strategies
- Comprehensive logging and error handling
- Full test coverage (65+ tests, 100% pass rate)
- Documentation and technical specifications
- Clean workspace organization

### Next Phase 🔄
- UI/Backend integration
- Visual pattern builder frontend
- Interactive conflict resolution interface
- Pattern library and templates
- Enhanced user experience features

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](docs/LICENSE) file for details.

## 🤝 Contributing

We welcome contributions! Please see our [Contributing Guide](docs/CONTRIBUTING.md) for details on how to get started.

## 📞 Support

- **Documentation**: Check the [docs/](docs/) directory for comprehensive guides
- **Issues**: Report bugs or request features via GitHub Issues
- **Discussions**: Join project discussions in GitHub Discussions

---

**Note**: This is an experimental project focused on AI-assisted development. While we strive for production-quality code, this remains a work in progress and learning experience.
