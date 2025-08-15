# OutfitRater - Anonymous Style Feedback Platform

OutfitRater is a web application that allows users to upload their outfit photos and receive anonymous feedback from others. Users can create accounts, upload outfits, and share links for others to rate their style.

## Features

### 🔐 User Authentication
- **Sign Up**: Create a new account with email and password
- **Sign In**: Log in to your existing account
- **Sign Out**: Securely log out from your account
- **Persistent Sessions**: Stay logged in across browser sessions

### 👕 Outfit Management
- **Upload Outfits**: Upload photos of your outfits with optional descriptions
- **My Outfits**: View all your uploaded outfits in one place
- **Outfit Details**: See detailed statistics and comments for each outfit
- **Shareable Links**: Generate unique links to share your outfits for rating

### ⭐ Rating System
- **Anonymous Ratings**: Others can rate your outfits anonymously
- **Star Ratings**: 1-5 star rating system
- **Comments**: Optional text feedback on outfits
- **Rating Statistics**: View average ratings and rating breakdowns
- **Duplicate Prevention**: Users can only rate each outfit once

### 📊 Analytics
- **Rating Breakdown**: See how many people gave each star rating
- **Total Ratings**: Track the number of ratings received
- **Average Rating**: Calculate overall outfit score
- **Comments Section**: Read all feedback comments

## Technology Stack

- **Frontend**: HTML5, CSS3, JavaScript (ES6+)
- **Backend**: Firebase
  - **Authentication**: Firebase Auth
  - **Database**: Firestore
  - **Hosting**: Firebase Hosting

## Getting Started

### Prerequisites
- A modern web browser
- Firebase project with Authentication and Firestore enabled

### Installation

1. **Clone the repository**
   ```bash
   git clone <repository-url>
   cd outfitrater
   ```

2. **Configure Firebase**
   - Create a new Firebase project
   - Enable Authentication (Email/Password)
   - Enable Firestore Database
   - Update the Firebase configuration in both `index.html` and `rate.html`

3. **Deploy to Firebase Hosting**
   ```bash
   npm install -g firebase-tools
   firebase login
   firebase init hosting
   firebase deploy
   ```

## Usage

### For Outfit Uploaders
1. **Create Account**: Sign up with your email and password
2. **Upload Outfit**: Click "Upload Outfit" tab and select a photo
3. **Add Description**: Optionally describe your outfit or ask for specific feedback
4. **Share Link**: Copy the generated shareable link and share it with others
5. **View Feedback**: Check the "My Outfits" tab to see ratings and comments

### For Raters
1. **Access Link**: Use the shareable link provided by the outfit owner
2. **Rate Outfit**: Give a 1-5 star rating
3. **Add Comment**: Optionally provide written feedback
4. **Submit**: Your anonymous rating will be saved

## File Structure

```
outfitrater/
├── index.html          # Main application page (upload/view outfits)
├── rate.html           # Rating page (for rating outfits)
├── README.md           # This documentation
└── package-lock.json   # Dependencies
```

## Firebase Configuration

The application uses the following Firebase services:

### Authentication
- **Provider**: Email/Password
- **Features**: Sign up, sign in, sign out, persistent sessions

### Firestore Collections

#### `outfits`
```javascript
{
  id: "unique_outfit_id",
  userId: "user_uid",
  userEmail: "user@example.com",
  image: "base64_image_data",
  description: "Outfit description",
  createdAt: "2024-01-01T00:00:00.000Z",
  totalRatings: 5,
  averageRating: 4.2,
  shareableLink: "https://domain.com/rate.html?outfit=id"
}
```

#### `ratings`
```javascript
{
  id: "unique_rating_id",
  outfitId: "outfit_id",
  rating: 4,
  comment: "Great style!",
  createdAt: "2024-01-01T00:00:00.000Z",
  userFingerprint: "browser_fingerprint",
  raterEmail: "rater@example.com",
  raterId: "rater_uid"
}
```

## Security Features

- **User Authentication**: All outfit uploads are tied to authenticated users
- **Data Isolation**: Users can only see their own outfits
- **Anonymous Ratings**: Raters remain anonymous to outfit owners
- **Duplicate Prevention**: Browser fingerprinting prevents multiple ratings from same user
- **Input Validation**: Client-side validation for all forms

## Browser Support

- Chrome (recommended)
- Firefox
- Safari
- Edge

## Contributing

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Test thoroughly
5. Submit a pull request

## License

This project is licensed under the MIT License.

## Support

For support or questions, please open an issue in the repository. 