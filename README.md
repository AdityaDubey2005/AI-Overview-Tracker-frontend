# 📊 AI Overview Tracker - Analytics Dashboard

[![Live Demo](https://img.shields.io/badge/Live-Demo-brightgreen?logo=firebase)](https://ai-overview-extension-de.web.app)
[![Firebase](https://img.shields.io/badge/Deployed-Firebase-orange?logo=firebase)](https://firebase.google.com)
[![React](https://img.shields.io/badge/Built%20with-React-blue?logo=react)](https://reactjs.org)
[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)

**Real-time analytics dashboard for tracking and analyzing Google AI Overview citations.**

A powerful, modern web application that visualizes data collected by the AI Overview Tracker Chrome extension. Get comprehensive insights into AI Overview citation patterns, domain performance, click-through rates, and query trends with beautiful, interactive charts and visualizations.

🔗 **Live Dashboard**: [https://ai-overview-extension-de.web.app](https://ai-overview-extension-de.web.app)

---

## 🎯 What is This?

The AI Overview Tracker Dashboard is the analytics companion to the [AI Overview Tracker Chrome Extension](https://github.com/YOUR-USERNAME/ai-overview-extension). It provides:

- **Real-time visualization** of AI Overview citation data
- **Interactive charts** showing citation trends, CTR, and domain performance
- **Filterable data tables** for deep-dive analysis
- **Topic-based categorization** of queries
- **Time-series analysis** for tracking patterns over time
- **Session management** for organizing related searches
- **Data export** capabilities for external analysis

All data is stored in your personal Firebase database, ensuring complete privacy and control.

---

## ✨ Features

### 📊 **Comprehensive Analytics**

#### Citation Analytics
- Total citations tracked
- Unique domains cited
- Citation frequency rankings
- Domain performance over time
- Citation source diversity metrics

#### Click-Through Rate (CTR) Analysis
- Per-citation CTR tracking
- Domain-level CTR comparison
- Time-to-click metrics
- Engagement patterns

#### Query Analysis
- Total queries tracked
- Auto-categorized topics (Technology, Health, Finance, etc.)
- Query frequency trends
- Search intent detection
- Session-based grouping

#### Temporal Trends
- Time-series visualizations
- Daily/weekly/monthly aggregations
- Peak activity periods
- Historical comparisons

---

### 🎨 **Beautiful User Interface**

#### Modern Design
- Clean, intuitive layout
- Responsive design (mobile, tablet, desktop)
- Dark mode support (coming soon)
- Smooth animations and transitions

#### Interactive Charts
- Line charts for trend analysis
- Bar charts for comparisons
- Pie charts for distributions
- Area charts for cumulative metrics
- Interactive tooltips and legends

#### Data Tables
- Sortable columns
- Filterable data
- Pagination support
- Search functionality
- Export to CSV

---

### 🔐 **Privacy & Security**

#### User Authentication
- Firebase Authentication
- Email/password sign-in
- Secure session management
- Password reset functionality

#### Data Privacy
- All data stored in YOUR Firebase project
- No third-party data sharing
- Client-side data processing
- Configurable data retention
- One-click data deletion

#### Security
- HTTPS encryption
- Firestore security rules
- Protected API endpoints
- CORS configuration

---

### ⚡ **Performance**

- **Fast loading**: Optimized bundle size (~260KB gzipped)
- **Real-time updates**: WebSocket-based data sync
- **Offline support**: Progressive Web App (PWA) ready
- **Caching**: Intelligent data caching strategies
- **Code splitting**: Lazy-loaded components

---

## 🚀 Live Demo

**Dashboard URL**: [https://ai-overview-extension-de.web.app](https://ai-overview-extension-de.web.app)

**Privacy Policy**: [https://ai-overview-extension-de.web.app/privacy.html](https://ai-overview-extension-de.web.app/privacy.html)

**Test Account**: Create your own account with any email address (Firebase Authentication)

---

## 📦 Installation & Deployment

### Prerequisites

- Node.js 16+ and npm
- Firebase account
- Chrome Extension installed (for data collection)

### Local Development

1. **Clone the repository**
git clone https://github.com/YOUR-USERNAME/ai-overview-dashboard.git
cd ai-overview-dashboard

text

2. **Install dependencies**
npm install

text

3. **Configure Firebase**

Create `src/firebaseConfig.js`:
import { initializeApp } from 'firebase/app';
import { getAuth } from 'firebase/auth';
import { getFirestore } from 'firebase/firestore';

const firebaseConfig = {
apiKey: "YOUR_API_KEY",
authDomain: "YOUR_AUTH_DOMAIN",
projectId: "YOUR_PROJECT_ID",
storageBucket: "YOUR_STORAGE_BUCKET",
messagingSenderId: "YOUR_MESSAGING_SENDER_ID",
appId: "YOUR_APP_ID"
};

const app = initializeApp(firebaseConfig);
export const auth = getAuth(app);
export const db = getFirestore(app);

text

4. **Start development server**
npm start

text

Opens at `http://localhost:3000`

5. **Build for production**
npm run build

text

### Deploy to Firebase Hosting

1. **Install Firebase CLI**
npm install -g firebase-tools

text

2. **Login to Firebase**
firebase login

text

3. **Initialize Firebase**
firebase init hosting

text

- Select your Firebase project
- Public directory: `build`
- Configure as single-page app: `Yes`
- Overwrite existing files: `No`

4. **Deploy**
npm run build
firebase deploy --only hosting

text

5. **Your dashboard is now live!**
https://YOUR-PROJECT-ID.web.app

text

---

## 🛠️ Tech Stack

### Frontend Framework
- **React 18** - UI library with Hooks
- **React Router v6** - Client-side routing
- **Create React App** - Build tooling

### UI Components
- **Recharts** - Interactive charts and visualizations
- **Lucide React** - Modern icon library
- **Custom components** - Dashboard, cards, tables

### Styling
- **CSS3** - Custom styling
- **CSS Modules** (optional) - Scoped styling
- **Responsive design** - Mobile-first approach

### Backend & Database
- **Firebase Authentication** - User management
- **Firebase Firestore** - NoSQL database
- **Firebase Hosting** - Static site hosting
- **Firebase Security Rules** - Access control

### Development Tools
- **ESLint** - Code linting
- **Prettier** - Code formatting
- **Git** - Version control

---


text

---

## 🔧 Configuration

### Firebase Security Rules

Configure Firestore security rules to protect user data:

rules_version = '2';
service cloud.firestore {
match /databases/{database}/documents {
match /users/{userId}/{document=**} {
allow read, write: if request.auth != null && request.auth.uid == userId;
}
}
}

text

### Environment Variables

For production deployments, use environment variables:

.env.production
REACT_APP_FIREBASE_API_KEY=your_api_key
REACT_APP_FIREBASE_AUTH_DOMAIN=your_auth_domain
REACT_APP_FIREBASE_PROJECT_ID=your_project_id

text

---

## 📊 Dashboard Features Breakdown

### Main Dashboard View
- **Overview cards**: Total citations, queries, domains, sessions
- **Citation trend chart**: Line chart showing citations over time
- **Top domains table**: Ranked list of most-cited domains
- **Query topics pie chart**: Distribution of query categories
- **Recent activity feed**: Latest tracked searches

### Filters & Controls
- **Date range picker**: Custom date ranges for analysis
- **Topic filter**: Filter by query category
- **Domain filter**: Focus on specific domains
- **Search box**: Find specific queries or citations
- **Export button**: Download data as CSV

### Data Tables
- **Citations table**: All tracked citations with metadata
- **Queries table**: Search history with topics and timestamps
- **Domains table**: Domain performance metrics
- **Sessions table**: Grouped search sessions

---

## 🐛 Troubleshooting

### Dashboard not loading?
**Solution**: Check Firebase configuration in `firebaseConfig.js`

### No data showing?
**Solution**: 
1. Ensure Chrome extension is installed and active
2. Perform searches on Google to generate data
3. Check Firebase Console for data
4. Verify authentication (logged in with same account)

### Login issues?
**Solution**:
1. Clear browser cache and cookies
2. Check Firebase Authentication is enabled
3. Verify email/password is correct
4. Check browser console for errors

### Deployment fails?
**Solution**:
1. Run `npm run build` successfully first
2. Ensure Firebase CLI is installed: `firebase --version`
3. Check `firebase.json` configuration
4. Verify you're logged into correct Firebase account

---

## 🔐 Privacy & Data

### What Data is Stored?

The dashboard accesses data collected by the Chrome extension:
- Search queries and timestamps
- AI Overview citations (URLs, domains, titles)
- Click events and engagement metrics
- Query topics and categorization
- Session identifiers

### Where is Data Stored?

All data is stored in **YOUR personal Firebase Firestore database**. We (the developers) cannot access your data. You have complete control.

### How to Delete Data?

1. **From Dashboard**: Settings → Clear All Data
2. **From Firebase Console**: Delete collections manually
3. **From Extension**: Extension settings → Clear Data

### Privacy Policy

Full privacy policy: [https://ai-overview-extension-de.web.app/privacy.html](https://ai-overview-extension-de.web.app/privacy.html)

---

## 🚀 Roadmap

### Planned Features
- [ ] Dark mode support
- [ ] Export data to JSON/CSV
- [ ] Advanced filtering options
- [ ] Custom dashboard widgets
- [ ] Email reports (daily/weekly summaries)
- [ ] API access for programmatic data retrieval
- [ ] Multi-user collaboration
- [ ] Custom alerts and notifications
- [ ] Mobile app (React Native)

---

## 🤝 Contributing

Contributions are welcome! Here's how:

1. **Fork the repository**
2. **Create a feature branch**
git checkout -b feature/AmazingFeature

text
3. **Commit your changes**
git commit -m 'Add some AmazingFeature'

text
4. **Push to the branch**
git push origin feature/AmazingFeature

text
5. **Open a Pull Request**

### Development Guidelines
- Follow existing code style
- Write clear commit messages
- Add comments for complex logic
- Test thoroughly before submitting
- Update documentation as needed

---

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---

## 📧 Support & Contact

**Developer**: Aditya Dubey / SimPPL

**Email**: [adity.dubey1301@gmail.com](mailto:adity.dubey1301@gmail.com)

**Live Dashboard**: [https://ai-overview-extension-de.web.app](https://ai-overview-extension-de.web.app)

**Chrome Extension**: [GitHub Repository](https://github.com/YOUR-USERNAME/ai-overview-extension)

**Report Issues**: [GitHub Issues](https://github.com/YOUR-USERNAME/ai-overview-dashboard/issues)

---

## 🙏 Acknowledgments

- **Firebase** - Backend infrastructure and hosting
- **React** - Frontend framework
- **Recharts** - Beautiful chart visualizations
- **Lucide** - Icon library
- **Create React App** - Build tooling
- **Open Source Community** - Inspiration and tools

---

## ⭐ Star This Project

If you find this dashboard useful, please star it on GitHub!

---

**Made with ❤️ by Aditya Dubey / SimPPL**



---
