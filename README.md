# Business AI Assistant

Complete Business AI solution with integrated APIs for payment processing, e-commerce, email marketing, and analytics.

## Features

✅ **Payment Processing** - Stripe integration  
✅ **E-commerce** - Shopify integration  
✅ **Email Marketing** - MailChimp integration  
✅ **Analytics** - Google Analytics integration  
✅ **Web Scraping** - Competitor data extraction  
✅ **Authentication** - JWT-based auth  
✅ **Dashboard** - Business metrics & reporting  

## Quick Start

### Prerequisites
- Node.js 18+
- PostgreSQL 12+
- Docker & Docker Compose (optional)

### Installation

1. **Clone the repository**
```bash
git clone https://github.com/kingleonrico-web/business-ai-assistant.git
cd business-ai-assistant
```

2. **Install dependencies**
```bash
npm install
```

3. **Set up environment variables**
```bash
cp .env.example .env
# Edit .env with your API keys
```

4. **Initialize database**
```bash
psql -U user -d business_ai -f db/schema.sql
```

5. **Start the server**
```bash
npm start
# Or for development with auto-reload
npm run dev
```

Server runs on `http://localhost:3000`

## Docker Deployment

```bash
docker-compose up -d
```

## API Endpoints

### Authentication
- `POST /api/auth/register` - Register new user
- `POST /api/auth/login` - Login user

### Payments (Stripe)
- `POST /api/stripe/payment-intent` - Create payment intent

### E-commerce (Shopify)
- `GET /api/shopify/products` - List products
- `GET /api/shopify/orders` - List orders

### Email Marketing (MailChimp)
- `GET /api/mailchimp/lists` - List email lists
- `POST /api/mailchimp/campaign` - Create campaign

### Analytics
- `GET /api/analytics/report` - Get analytics report
- `GET /api/dashboard/metrics` - Get business metrics

### Web Scraper
- `POST /api/scraper/fetch` - Scrape website data

## Configuration

### Required API Keys

**Stripe**
- Get keys from: https://dashboard.stripe.com/apikeys

**Shopify**
- Store URL: `your-store.myshopify.com`
- Access Token: From Shopify Admin

**MailChimp**
- API Key: From MailChimp Account Settings

**Google Analytics**
- Service Account JSON from Google Cloud Console

## Database Schema

- **users** - User accounts
- **metrics** - Business metrics
- **transactions** - Payment transactions
- **campaigns** - Marketing campaigns
- **analytics_data** - Web analytics

## Development

```bash
npm run dev        # Start with nodemon
npm run build      # Build TypeScript
npm test           # Run tests
npm run lint       # Lint code
```

## Deployment

### DigitalOcean App Platform
1. Connect GitHub repository
2. Set environment variables
3. Deploy

### Manual Deployment
```bash
# Build Docker image
docker build -t business-ai-assistant .

# Push to registry
docker push your-registry/business-ai-assistant

# Deploy to server
docker run -p 3000:3000 \
  -e DATABASE_URL=your_db_url \
  -e STRIPE_SECRET_KEY=your_key \
  business-ai-assistant
```

## Support

For issues and feature requests, create an issue on GitHub.

## License

MIT
