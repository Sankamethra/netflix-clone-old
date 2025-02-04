# Netflix Clone

A full-stack Netflix clone built with Next.js, featuring user authentication, multiple account profiles, and streaming capabilities.

## Features

- **User Authentication**: GitHub authentication integration using NextAuth.js
- **Multiple User Profiles**: 
  - Create up to 4 profiles per account
  - PIN protection for each profile
  - Profile management (add/remove)
- **Content Browsing**:
  - Browse movies and TV shows by category
  - Dynamic banner with featured content
  - Search functionality
  - Similar content recommendations
- **Media Player**:
  - Integrated video player for content streaming
  - Trailer playback support
- **Favorites List**:
  - Add/remove content to personal favorites
  - Persistent favorites list per profile

## Tech Stack

- **Frontend**:
  - Next.js 13+ (App Router)
  - Tailwind CSS for styling
  - Framer Motion for animations
  - React Player for video playback
  - Material UI for modals

- **Backend**:
  - Next.js API Routes
  - MongoDB for database
  - NextAuth.js for authentication
  - bcryptjs for password hashing

## Project Structure

```
src/
├── app/                    # Next.js app router pages
│   ├── api/               # API routes
│   ├── browse/            # Browse page
│   ├── movies/            # Movies page
│   ├── tv/               # TV shows page
│   └── watch/            # Video player page
├── components/            # React components
│   ├── banner/           # Featured content banner
│   ├── manage-accounts/  # Account management
│   └── ...
├── context/              # Global state management
├── database/            # Database configuration
└── utils/              # Utility functions
```

## Getting Started

1. Clone the repository:
```bash
git clone [repository-url]
```

2. Install dependencies:
```bash
npm install
# or
yarn install
```

3. Set up environment variables:
```env
# Create a .env.local file with:
GITHUB_ID=your_github_client_id
GITHUB_SECRET=your_github_client_secret
MONGODB_URI=your_mongodb_connection_string
NEXTAUTH_SECRET=your_nextauth_secret
```

4. Run the development server:
```bash
npm run dev
# or
yarn dev
```

5. Open [http://localhost:3000](http://localhost:3000) in your browser.

## API Routes

- `/api/account/*` - Account management endpoints
- `/api/auth/*` - Authentication endpoints
- `/api/favorites/*` - Favorites management endpoints

## Key Features Implementation

### Profile Management
```javascript
// Create new profile
const response = await fetch("/api/account/create-account", {
  method: "POST",
  body: JSON.stringify({
    name,
    pin,
    uid: session?.user?.uid,
  }),
});
```

### Content Streaming
```javascript
<ReactPlayer
  url={`https://www.youtube.com/watch?v=${videoKey}`}
  width="100%"
  height="100%"
  playing
  controls
/>
```

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## License

[Add your license here]

## Acknowledgments

- [TMDB API](https://www.themoviedb.org/documentation/api) for movie and TV show data
- [Next.js Documentation](https://nextjs.org/docs)
- [Tailwind CSS](https://tailwindcss.com/docs)
