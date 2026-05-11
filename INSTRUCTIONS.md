# Setup and Usage Instructions

## Table of Contents

1. [Prerequisites](#prerequisites)
2. [Initial Setup](#initial-setup)
3. [Configuration](#configuration)
4. [Running the Application](#running-the-application)
5. [Using the Lottery System](#using-the-lottery-system)
6. [Available Commands](#available-commands)
7. [Extending the Application](#extending-the-application)
8. [Best Practices](#best-practices)
9. [Troubleshooting](#troubleshooting)
10. [Documentation](#documentation)

## Prerequisites

### System Requirements

- **Node.js**: Version 6 or higher
- **Package Manager**: npm or yarn
- **Angular CLI**: Version 1.0.1 or higher
- **Operating System**: Windows, macOS, or Linux
- **Memory**: 2GB RAM minimum
- **Disk Space**: 200MB for application and dependencies

### Knowledge Prerequisites

- Basic understanding of Angular and TypeScript
- Familiarity with JSON and REST APIs
- Comfort using the command line

## Initial Setup

### 1. Install Dependencies

**Using npm:**

```bash
npm install
```

**Using yarn:**

```bash
yarn install
```

**Verify installation:**

```bash
ng version
```

## Configuration

### Setting Up Attendee Data

1. Open `db.json` in the root directory
2. Update the attendee list under the `jspoland` array:
   ```json
   {
     "jspoland": [
       { "name": "John Doe" },
       { "name": "Jane Smith" },
       { "name": "ישראל ישראלי" }
     ],
     "meetup": []
   }
   ```
3. The application supports both English and Hebrew names
4. Each entry requires a `name` property

### Component Configuration

To adjust the lottery animation behavior, modify the component inputs in `src/app/app.component.ts`:

- `maxIterations`: Number of animation cycles (default: 250)
- `speed`: Animation speed in milliseconds (default: 17ms)

Lower values make the animation faster, higher values make it slower.

## Running the Application

### Start the JSON Server

The application requires a JSON server to serve attendee data:

```bash
npm run db
```

This starts the JSON server on `http://localhost:3000`

### Start the Development Server

In a separate terminal window:

```bash
ng serve
```

Navigate to `http://localhost:4200` in your browser. The app will automatically reload if you change any source files.

## Using the Lottery System

1. **Initialize**: Click the "INIT" button to select a new random name from the pool
2. **Start**: Click the "START" button to begin the animated reveal
3. **Winner Display**: Watch as the text decodes Matrix-style to reveal the winner
4. **Winners List**: All selected winners are displayed at the bottom of the screen

### Animation Behavior

- The animation cycles through random characters before revealing the actual winner
- Characters include letters (uppercase, lowercase), numbers, and Hebrew letters
- Hebrew names are displayed right-to-left automatically
- The animation completes after reaching `maxIterations` or when the name is revealed

## Build

### Development Build

```bash
ng build
```

Build artifacts will be stored in the `dist/` directory.

### Production Build

```bash
ng build --prod
```

Use the `-prod` flag for a production build with optimizations.

## Available Commands

### Development Commands

**Linting and Formatting:**

```bash
# Check code style and quality
ng lint
```

**Building:**

```bash
# Compile TypeScript to JavaScript
ng build

# Production build
ng build --prod
```

**Testing:**

```bash
# Run unit tests
ng test

# Run e2e tests
ng e2e
```

### Running Scripts

**Start Everything:**

```bash
# Start JSON server and dev server in parallel (if configured)
npm start
```

**Database Server:**

```bash
# Start mock REST API
npm run db
```

## Project Structure

```
angularil-lottery/
├── src/
│   ├── app/
│   │   ├── app.component.ts       # Main application component
│   │   ├── app.module.ts          # Application module
│   │   ├── text.component.ts      # Lottery text animation component
│   │   ├── buttons.component.ts   # Control buttons component
│   │   └── data.service.ts        # Data service for API calls
│   ├── environments/              # Environment configurations
│   └── main.ts                    # Application entry point
├── db.json                        # Attendee data (JSON Server)
└── package.json
```

## Troubleshooting

### JSON Server Not Connecting

- Ensure the JSON server is running on port 3000
- Check that `db.json` exists in the root directory
- Verify the URL in `src/app/data.service.ts` matches your server address

### Animation Issues

- If animation is too fast, increase the `speed` value
- If animation is too slow, decrease the `speed` value
- If text doesn't align properly, check the CSS in `text.component.ts`

### Hebrew Text Display

- Ensure your browser supports UTF-8 encoding
- Hebrew text automatically reverses for right-to-left display
- The `hebrewLetters` constant in `text.component.ts` contains all Hebrew characters

## Development

### Code Scaffolding

Run `ng generate component component-name` to generate a new component.

You can also use:

- `ng generate directive|pipe|service|class|guard|interface|enum|module`

### Testing

Run `ng test` to execute unit tests via Karma.

### Linting

Run `ng lint` to check code quality.

## Notes

- This project was generated with Angular CLI version 1.0.1
- Uses Angular 4.x framework
- Uses Angular Material 2.x for UI components
- Requires Node.js and npm/yarn
- JSON Server is used as a mock backend

## Extending the Application

### Adding New Attendees

1. Update `db.json` with new entries.
2. Restart the JSON server if changes don't reflect immediately.

### Customizing the Animation

1. Modify `characterPool` in `text.component.ts` to add/remove characters.
2. Adjust `maxIterations` for a longer or shorter reveal process.

### UI Enhancements

1. Use Angular Material components to add new features like winner filters or export options.
2. Update `styles.css` for global theme changes.

## Best Practices

- **Component Isolation**: Keep logic within relevant components.
- **Service Usage**: Always use `DataService` for API calls to maintain a clean architecture.
- **Immutable Data**: Handle attendee arrays as immutable to prevent unexpected side effects.
- **Bidi Support**: Ensure all new text components support both LTR and RTL for bilingual consistency.

## Documentation

- **README.md**: Overview of the project, features, and architecture.
- **CODE_OF_CONDUCT.md**: Community guidelines.
- **CONTRIBUTING.md**: Instructions for contributing to the project.

## External Resources

- [Angular Documentation](https://angular.io/docs)
- [Angular Material UI](https://material.angular.io/)
- [JSON Server Guide](https://github.com/typicode/json-server)
- [RxJS Documentation](https://rxjs.dev/)

## Last Updated

2026-05-11

## Version

0.0.0

## Author

- **Or Assayag** - _Initial work_ - [orassayag](https://github.com/orassayag)
- Or Assayag <orassayag@gmail.com>
- GitHub: https://github.com/orassayag
- StackOverflow: https://stackoverflow.com/users/4442606/or-assayag?tab=profile
- LinkedIn: https://linkedin.com/in/orassayag
