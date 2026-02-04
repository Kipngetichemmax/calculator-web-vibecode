# Advanced Web Calculator

A fully-featured web-based calculator with a clean, modern interface.

## Features

✅ **Basic Operations**: Addition, subtraction, multiplication, division
✅ **Advanced Operations**: Percentage, square root, positive/negative toggle
✅ **Keyboard Support**: Full keyboard input support
✅ **Calculation History**: Stores up to 20 past calculations in localStorage
✅ **Responsive Design**: Works perfectly on desktop, tablet, and mobile
✅ **Modern UI**: Clean gradient design with smooth animations

## How to Use

### On Desktop/Laptop

1. **Double-click** the `calculator.html` file
2. It will open in your default web browser
3. Start calculating!

### Mouse/Touch Controls

- Click number buttons (0-9) to input numbers
- Click operation buttons (+, -, ×, ÷) to perform operations
- Click **=** to calculate the result
- Click **C** to clear the current calculation
- Click **%** to convert the current number to a percentage
- Click **√** to calculate the square root
- Click **+/-** to toggle between positive and negative
- Click any history item to load that result

### Keyboard Shortcuts

| Key | Action |
|-----|--------|
| `0-9` | Input numbers |
| `.` | Decimal point |
| `+` | Addition |
| `-` | Subtraction |
| `*` | Multiplication |
| `/` | Division |
| `Enter` or `=` | Calculate result |
| `Escape` or `C` | Clear |
| `Backspace` | Delete last digit |
| `%` | Percentage |

## Code Structure

### HTML Structure
- **Display area**: Shows current input and previous operation
- **Button grid**: 4×5 grid of calculator buttons
- **History panel**: Scrollable list of past calculations

### CSS Styling
- **Gradient background**: Purple gradient for visual appeal
- **Responsive grid**: Adapts to different screen sizes
- **Color-coded buttons**: Different colors for different button types
  - Gray: Numbers
  - Purple: Operations
  - Green: Equals
  - Red: Clear
  - Orange: Special operations

### JavaScript Logic
- **Calculator class**: Object-oriented design for clean code organization
- **State management**: Tracks current value, previous value, and operation
- **History management**: Uses localStorage for persistent storage
- **Keyboard handling**: Event listeners for keyboard input
- **Error handling**: Prevents division by zero and invalid operations

## Running Locally on Android with Termux

Termux is a terminal emulator for Android that lets you run a local web server.

### Step 1: Install Termux

1. Install **Termux** from F-Droid (recommended) or Google Play Store
   - F-Droid: https://f-droid.org/packages/com.termux/
   - Note: F-Droid version is more up-to-date

### Step 2: Setup Termux

Open Termux and run these commands:

```bash
# Update package list
pkg update

# Upgrade installed packages
pkg upgrade

# Install Python (includes a simple web server)
pkg install python
```

### Step 3: Transfer the Calculator File

**Option A: Download directly in Termux**
```bash
# Install wget
pkg install wget

# Download the calculator file (if hosted online)
wget https://your-url/calculator.html
```

**Option B: Manual transfer**
1. Connect your phone to your computer via USB
2. Copy `calculator.html` to your phone's Downloads folder
3. In Termux, run:
```bash
# Copy from Downloads to current directory
cp ~/storage/downloads/calculator.html ~/
```

Note: First time you might need to allow Termux storage access:
```bash
termux-setup-storage
```

### Step 4: Start the Web Server

```bash
# Navigate to the directory with calculator.html
cd ~

# Start Python's built-in web server on port 8000
python -m http.server 8000
```

You should see output like:
```
Serving HTTP on 0.0.0.0 port 8000 (http://0.0.0.0:8000/) ...
```

### Step 5: Open in Browser

1. Open any web browser on your Android device (Chrome, Firefox, etc.)
2. Go to: **http://localhost:8000/calculator.html**
3. The calculator should now be running!

### Step 6: Stop the Server

When you're done:
- Press `Ctrl + C` in Termux to stop the server
- Type `exit` to close Termux

## Alternative: Direct File Access

You can also open the HTML file directly without a server:

1. Install a file manager app (like "Files by Google")
2. Navigate to where you saved `calculator.html`
3. Tap the file
4. Choose "Open with Browser"

**Note**: History might not work properly when opening files directly due to browser security restrictions. Using a local server (Termux method) is recommended for full functionality.

## Browser Compatibility

Works on all modern browsers:
- ✅ Chrome/Edge (recommended)
- ✅ Firefox
- ✅ Safari
- ✅ Opera
- ✅ Brave

## Customization Ideas

Want to modify the calculator? Here are some ideas:

### Change Colors
Edit the CSS color values:
- Background gradient: Look for `background: linear-gradient(...)`
- Button colors: Modify the `.btn-*` class backgrounds

### Add More Operations
1. Add a button in the HTML
2. Create a method in the Calculator class
3. Add keyboard shortcut (optional)

### Adjust History Size
Change line 349 in the JavaScript:
```javascript
if (this.history.length > 20) {  // Change 20 to your preferred number
```

### Modify Display Precision
Change line 368 in the JavaScript:
```javascript
return num.toExponential(6);  // Change 6 to desired decimal places
```

## Troubleshooting

**Calculator not working?**
- Make sure JavaScript is enabled in your browser
- Try opening in a different browser
- Check browser console for errors (F12 on desktop)

**History not saving?**
- localStorage might be disabled
- Try using a local server instead of opening the file directly
- Check if you're in private/incognito mode (localStorage is cleared)

**Keyboard not responding?**
- Click on the calculator display area first
- Make sure you're not in another input field

## License

Free to use and modify for personal and commercial projects.

## Credits

Created as a demonstration of modern web development practices using vanilla HTML, CSS, and JavaScript.
