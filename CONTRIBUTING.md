# Contributing

Contributions to this project are [released](https://help.github.com/articles/github-terms-of-service/#6-contributions-under-repository-license) to the public under the [project's open source license](LICENSE).

Everyone is welcome to contribute to this project. Contributing doesn't just mean submitting pull requests—there are many different ways for you to get involved, including answering questions, reporting issues, improving documentation, or suggesting new features.

## How to Contribute

### Reporting Issues

If you find a bug or have a feature request:
1. Check if the issue already exists in the [GitHub Issues](https://github.com/orassayag/angularil-lottery/issues)
2. If not, create a new issue with:
   - Clear title and description
   - Steps to reproduce (for bugs)
   - Expected vs actual behavior
   - Your environment details (OS, Node version, Angular version)

### Submitting Pull Requests

1. Fork the repository
2. Create a new branch for your feature/fix:
   ```bash
   git checkout -b feature/your-feature-name
   ```
3. Make your changes following the code style guidelines below
4. Test your changes thoroughly
5. Commit with clear, descriptive messages
6. Push to your fork and submit a pull request

### Code Style Guidelines

This project uses:
- **Angular** 4.x framework
- **TypeScript** for type safety
- **Angular Material** for UI components
- **TSLint** for code quality

Before submitting:
```bash
# Install dependencies
npm install

# Run the development server
ng serve

# Run the JSON server for API
npm run db

# Build for production
ng build --prod
```

### Coding Standards

1. **TypeScript best practices**: Use proper types, avoid `any` when possible
2. **Component structure**: Keep components focused and single-purpose
3. **Service pattern**: Use services for data management and API calls
4. **Angular Material**: Use Material Design components for consistency
5. **Naming conventions**: Follow Angular style guide naming conventions
6. **Comments**: Add meaningful comments for complex logic

### Adding New Features

When adding new features:
1. Update component templates and styles as needed
2. Add service methods in appropriate service files
3. Update the `db.json` if data structure changes
4. Test with both Hebrew and English names
5. Ensure responsive design

### Testing Your Changes

1. Test the lottery animation with different name lengths
2. Verify Hebrew text displays correctly (right-to-left)
3. Test the winner selection logic
4. Ensure the init button resets state properly
5. Verify JSON server connectivity

## Questions or Need Help?

Please feel free to contact me with any question, comment, pull-request, issue, or any other thing you have in mind.

* Or Assayag <orassayag@gmail.com>
* GitHub: https://github.com/orassayag
* StackOverflow: https://stackoverflow.com/users/4442606/or-assayag?tab=profile
* LinkedIn: https://linkedin.com/in/orassayag

Thank you for contributing! 🙏
