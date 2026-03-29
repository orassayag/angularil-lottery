# Instructions

## Setup Instructions

1. Open the project in your IDE (VSCode recommended)
2. Install Angular CLI globally (if not already installed):
   ```bash
   npm install -g @angular/cli
   ```
3. Install dependencies:
   ```bash
   npm install
   # or
   yarn install
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

## Author

* **Or Assayag** - *Initial work* - [orassayag](https://github.com/orassayag)
* Or Assayag <orassayag@gmail.com>
* GitHub: https://github.com/orassayag
* StackOverflow: https://stackoverflow.com/users/4442606/or-assayag?tab=profile
* LinkedIn: https://linkedin.com/in/orassayag
