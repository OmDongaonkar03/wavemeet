# WaveMeet

A simple, browser-based video conferencing tool designed for quick and easy virtual meetings. Create or join meetings with a unique code, featuring video, audio, screen sharing, chat, and participant management - all through your browser.

## Features

- **Create Meetings**: Generate a unique meeting ID to start a new session
- **Join Meetings**: Enter a meeting code to participate in an existing session
- **Video and Audio Controls**: Toggle camera and microphone with real-time feedback
- **Screen Sharing**: Share your screen with participants
- **Chat**: Send and receive messages during the meeting
- **Participant Management**: View attendees, raise hands, or kick participants (moderator only)
- **Invite Links**: Copy meeting IDs or shareable URLs for easy access
- **Responsive Design**: Works on desktops, tablets, and mobile devices

## Technologies Used

- **HTML5**: Structure of the web pages
- **CSS3**: Custom styles with glassmorphism effects and responsive design
- **JavaScript**: Client-side logic for meeting controls and Jitsi API integration
- **8x8 Jitsi Meet API**: Powers video conferencing functionality
- **Bootstrap 5**: Responsive layout and form styling in index.html
- **Font Awesome**: Icons for buttons and controls

## Project Structure

```
wavemeet/
├── index.html        # Landing page to create or join meetings
└── meeting.html      # Video conference interface
```

## Prerequisites

- A modern web browser (Chrome, Firefox, Safari, Edge)
- Internet connection for accessing the Jitsi Meet API and CDNs
- An 8x8 Jitsi Meet API key (replace the default one for production use)

## Setup and Usage

### Step 1: Clone or Download

Download the index.html and meeting.html files or clone the repository:

```bash
git clone https://github.com/yourusername/wavemeet.git
cd wavemeet
```

### Step 2: Configure the Jitsi API Key

To use WaveMeet with your own 8x8 Jitsi Meet instance, replace the default API key in meeting.html:

```javascript
const domain = '8x8.vc';
const appId = 'YOUR_APP_ID'; // Replace with your 8x8 Jitsi app ID
const fullRoomName = `${appId}/${roomName}`;
```

#### How to Get an App ID:
1. Sign up for an 8x8 Jitsi-as-a-Service account at [8x8.vc](https://8x8.vc)
2. Obtain your app ID and (optionally) a JWT for premium features like recording
3. If you don't have an app ID, the default key may work for testing but has limitations

### Step 3: Host the Application

WaveMeet is a static web app, so you can host it on:

- **GitHub Pages**:
  - Push files to a GitHub repository
  - Enable GitHub Pages in repository settings
  - Access at `https://yourusername.github.io/wavemeet/`

- **Netlify**:
  - Sign up at [netlify.com](https://netlify.com)
  - Drag and drop the wavemeet folder or link your Git repository
  - Deploy and get a URL like `https://wavemeet.netlify.app`

- **Vercel**:
  - Sign up at [vercel.com](https://vercel.com)
  - Import your repository or use the Vercel CLI
  - Run `vercel` to deploy

- **Firebase Hosting or Traditional Hosts**:
  - Upload files to the public directory via CLI or FTP
  - Ensure both files are in the same directory

### Step 4: Use WaveMeet

#### Access the App:
Open the hosted URL (e.g., `https://yourdomain.com/index.html`) in a browser.

#### Create a Meeting:
1. On the landing page, fill out the "New Meeting" form
2. Enter your name
3. Toggle video and audio preferences
4. Click "Create Meeting" to generate a unique meeting ID

#### Join a Meeting:
1. Enter a meeting code (e.g., WM-abc123) in the "Join Meeting" form
2. Provide your name and toggle video/audio settings
3. Click "Join Meeting" to enter the session

#### In-Meeting Features:
- Use the control bar to toggle video, audio, or screen sharing
- Open the chat panel to send messages
- View and manage participants
- Copy the meeting ID or invite link to share with others
- Click "Leave" to exit

## Example URLs

- Landing page: `https://yourdomain.com/index.html`
- Meeting page: `https://yourdomain.com/meeting.html?room=abc123&name=John&video=true&audio=true`

## Limitations

- **Recording**: Disabled by default with the public API key
- **Passwords**: Form fields exist but are unimplemented
- **Participant Limits**: The public API key may cap participants (typically 10–25)
- **Features**: Some Jitsi features require a JWT and premium plan

## Customization

- **Branding**: Modify the `NATIVE_APP_NAME` and `PROVIDER_NAME` in meeting.html
- **Styles**: Edit the CSS in both files to adjust colors, layouts, or effects
- **Features**: Add password support or backend integration by extending the Jitsi API

## Troubleshooting

- **Jitsi Not Loading**:
  - Check your API key and internet connection
  - Ensure 8x8.vc isn't blocked by your network or browser

- **Redirect Issues**:
  - Verify both files are hosted in the same directory
  - Check the browser console for errors

- **Invite Links Broken**:
  - Confirm your domain is correct in `copyInviteLink`

- **Mobile Issues**:
  - Test on multiple devices for optimal experience

## Contributing

Feel free to fork the project, add features (e.g., password support, meeting history), or improve the UI. Submit pull requests or open issues on the repository.

## License

This project is open-source under the MIT License. Use it freely, but ensure compliance with 8x8's terms for their API.

## Acknowledgments

- Built with the 8x8 Jitsi Meet API for robust video conferencing
- Styled with Bootstrap and Font Awesome for a polished look
- Inspired by the need for simple, accessible virtual meetings
