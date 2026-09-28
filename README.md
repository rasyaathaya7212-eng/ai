# AI Chat Website

A modern, responsive AI chat interface powered by DeepSeek API with beautiful UI/UX.

![AI Chat Preview](https://img.shields.io/badge/AI-Chat-blue)
![React](https://img.shields.io/badge/React-18.2.0-61dafb)
![Vite](https://img.shields.io/badge/Vite-5.0.0-646cff)
![License](https://img.shields.io/badge/License-MIT-green)

## ✨ Features

- 🎨 **Modern UI Design** - Clean, responsive interface with dark/light mode support
- 🤖 **AI-Powered Chat** - Integration with DeepSeek API for intelligent conversations
- 💬 **Multiple Conversations** - Create, rename, and manage different chat sessions
- 🌓 **Theme Toggle** - Switch between light and dark modes
- ⚙️ **Configurable API** - Easy API configuration with real-time validation
- 📱 **Fully Responsive** - Works perfectly on desktop, tablet, and mobile
- 🚀 **Fast Performance** - Built with React and Vite for optimal performance
- 🔒 **Secure** - Environment-based API configuration

## 🚀 Quick Start

### Prerequisites
- Node.js 16 or higher
- npm or yarn

### Installation

1. Clone the repository:
```bash
git clone https://github.com/yourusername/ai-chat-website.git
cd ai-chat-website
```

2. Install dependencies:
```bash
npm install
# or
yarn install
```

3. Start the development server:
```bash
npm run dev
# or
yarn dev
```

4. Open your browser and navigate to `http://localhost:3000`

## 📁 Project Structure

```
ai-chat-website/
├── public/              # Static assets
├── src/                 # Source code
│   ├── components/      # React components
│   │   ├── ChatInterface.js
│   │   └── Sidebar.js
│   ├── styles/          # CSS styles
│   │   └── main.css
│   ├── App.js           # Main application component
│   └── index.js         # Application entry point
├── index.html           # HTML template
├── package.json         # Dependencies and scripts
├── vite.config.js       # Vite configuration
├── .gitignore           # Git ignore rules
└── README.md            # This file
```

## 🛠️ Configuration

### API Configuration
The application comes pre-configured with DeepSeek API settings. You can modify these in the sidebar:

1. Click the ⚙️ **API Configuration** button in the sidebar
2. Update the following fields:
   - **Base URL**: API endpoint URL
   - **Auth Token**: Your API authentication token
   - **Model**: Select AI model (DeepSeek V4 Pro, etc.)

### Environment Variables
For production deployment, you can set environment variables:

```bash
VITE_API_BASE_URL=https://dattio.my.id
VITE_API_AUTH_TOKEN=your_token_here
VITE_API_MODEL=deepseek-v4-pro
```

## 💻 Usage

### Starting a Conversation
1. Click "New Chat" in the sidebar to create a new conversation
2. Type your message in the input box
3. Press Enter to send or Shift+Enter for a new line

### Managing Conversations
- **Rename**: Double-click on conversation title or click edit icon
- **Delete**: Click trash icon (minimum 1 conversation must remain)
- **Switch**: Click on any conversation in the sidebar

### Features
- **Dark/Light Mode**: Toggle theme using the theme switch
- **API Status**: Real-time connection status indicator
- **Typing Indicators**: Visual feedback while AI is responding
- **Error Handling**: Clear error messages for API issues
- **Quick Suggestions**: Pre-made message suggestions for new users

## 🎨 Customization

### Styling
The application uses CSS variables for easy customization. Modify `styles/main.css` to change:

- Color schemes
- Spacing and layout
- Typography
- Animations and transitions

### Components
You can extend or modify:
- `ChatInterface.js`: Main chat functionality
- `Sidebar.js`: Conversation management and settings
- `App.js`: Main application logic

## 📱 Responsive Design

The application is fully responsive and optimized for:
- **Desktop**: Full-featured interface with sidebar
- **Tablet**: Optimized layout for medium screens
- **Mobile**: Stacked layout with touch-friendly controls

## 🔧 Deployment

### Build for Production
```bash
npm run build
# or
yarn build
```

The build artifacts will be stored in the `dist/` directory.

### Deploy to Vercel/Netlify
1. Push your code to GitHub
2. Connect your repository to Vercel/Netlify
3. Configure environment variables
4. Deploy!

### Static Hosting
You can also host the built files on any static hosting service:
- GitHub Pages
- AWS S3
- Firebase Hosting
- Cloudflare Pages

## 🧪 Testing

Run the development server and test all features:
1. API connection status
2. Message sending and receiving
3. Theme switching
4. Responsive design
5. Error handling

## 🤝 Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

1. Fork the project
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## 📄 License

This project is licensed under the MIT License - see the LICENSE file for details.

## 🙏 Acknowledgments

- [DeepSeek](https://www.deepseek.com/) for AI API
- [React](https://reactjs.org/) for UI framework
- [Vite](https://vitejs.dev/) for build tool
- [Font Awesome](https://fontawesome.com/) for icons
- [Google Fonts](https://fonts.google.com/) for typography

## 📞 Support

For support, open an issue in the GitHub repository or contact the maintainers.

---

Made with ❤️ by AI Chat Website Team