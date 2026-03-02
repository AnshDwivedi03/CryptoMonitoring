# CoinPulse 🚀

A modern, real-time cryptocurrency tracking and analytics platform built with Next.js 16. Track live Bitcoin prices, view detailed coin data, analyze market trends with interactive candlestick charts, and convert cryptocurrencies to multiple fiat currencies.

<div align="center">
  <img src="https://img.shields.io/badge/-Next.js_16-black?style=for-the-badge&logo=Next.js&logoColor=white" />
  <img src="https://img.shields.io/badge/-React_19-61DAFB?style=for-the-badge&logo=React&logoColor=black" />
  <img src="https://img.shields.io/badge/-TypeScript-3178C6?style=for-the-badge&logo=Typescript&logoColor=white" />
  <img src="https://img.shields.io/badge/-Tailwind_CSS_4-06B6D4?style=for-the-badge&logo=tailwindcss&logoColor=white" />
  <img src="https://img.shields.io/badge/-Radix_UI-9E5DFF?style=for-the-badge&logo=radix-ui&logoColor=white" />
  <img src="https://img.shields.io/badge/-CoinGecko_API-F0CA3F?style=for-the-badge&logo=coingecko&logoColor=black" />
</div>

---

## ✨ Features

### 📊 Real-Time Data & Charts

- **Live Candlestick Charts**: Interactive charting with lightweight-charts library
- **WebSocket Integration**: Real-time price updates and OHLCV (Open, High, Low, Close, Volume) data streams
- **Multiple Time Periods**: Daily, weekly, monthly, quarterly, semi-annual, yearly, and maximum history views
- **Live Data Modes**: Switch between 1-second and 1-minute interval updates

### 💰 Cryptocurrency Features

- **Home Page**: Display top trending coins with Bitcoin market overview
- **All Coins Page**: Browse all major cryptocurrencies with pagination (10 per page)
- **Detailed Coin Pages**: View comprehensive data for individual coins including:
  - Current price and 24h changes
  - Market cap and ranking
  - All-time high (ATH) and all-time low (ATL)
  - Circulating and total supply
  - Market tickers and trading pairs

### 🔄 Currency Converter

- Convert crypto prices to multiple fiat currencies (USD, EUR, JPY, GBP, etc.)
- Real-time exchange rate calculations
- Interactive currency selector

### 🎨 User Interface

- Clean, modern design with Tailwind CSS
- Responsive components using Radix UI
- Data tables with smart formatting
- Loading fallbacks with Suspense boundaries
- Dark theme optimized for financial data

### 📱 Pagination

- Efficient pagination for coin listings
- Dynamic page navigation

---

## 🛠️ Tech Stack

### Core Framework

- **Next.js 16.1.0** - React framework with server & client components
- **React 19.2.3** - UI library
- **TypeScript 5** - Type-safe development

### UI & Styling

- **Tailwind CSS 4** - Utility-first CSS framework
- **Radix UI** - Unstyled, accessible component primitives
  - `@radix-ui/react-select` - Accessible select component
  - `@radix-ui/react-separator` - Visual divider
  - `@radix-ui/react-slot` - Slot primitive
- **Lucide React** - Icon library
- **Class Variance Authority** - CSS class composition
- **clsx** - Conditional class utilities
- **Tailwind Merge** - Intelligent Tailwind CSS merging

### Charts & Data

- **Lightweight Charts** - Professional charting library for OHLCV data
- **Query String** - URL query parameter parsing and stringification

### Development Tools

- **ESLint 9** - Code linting
- **Prettier 3.7.4** - Code formatting
- **TypeScript** - Static type checking

---

## 🚀 Getting Started

### Prerequisites

- Node.js 18+
- npm or yarn package manager
- CoinGecko API key (Pro tier for WebSocket access)

### Installation

1. **Clone the repository:**

```bash
git clone https://github.com/yourusername/coinpulse.git
cd coinpulse
```

2. **Install dependencies:**

```bash
npm install
```

3. **Set up environment variables:**

Create a `.env.local` file in the root directory:

```env
# CoinGecko API Configuration
COINGECKO_BASE_URL=https://pro-api.coingecko.com/api/v3
COINGECKO_API_KEY=your_coingecko_pro_api_key
NEXT_PUBLIC_COINGECKO_WEBSOCKET_URL=wss://ws.coingecko.com/
NEXT_PUBLIC_COINGECKO_API_KEY=your_public_api_key
```

Get your API key from [CoinGecko Pro](https://www.coingecko.com/en/api)

4. **Run the development server:**

```bash
npm run dev
```

Open [http://localhost:3000](http://localhost:3000) in your browser to see the application.

---

## 📋 Available Scripts

```bash
# Start development server with hot reload
npm run dev

# Build for production
npm run build

# Start production server
npm start

# Run ESLint to check code quality
npm run lint

# Format code with Prettier
npm run format
```

---

## 📁 Project Structure

```
CoinPulse/
├── app/                              # Next.js App Router
│   ├── layout.tsx                    # Root layout wrapper
│   ├── page.tsx                      # Home page (trending coins & overview)
│   ├── globals.css                   # Global styles
│   └── coins/
│       ├── page.tsx                  # All coins with pagination
│       └── [id]/
│           └── page.tsx              # Individual coin detail page
│
├── components/                       # React components
│   ├── CandlestickChart.tsx         # Interactive candlestick chart
│   ├── CoinHeader.tsx               # Coin header information
│   ├── CoinsPagination.tsx          # Pagination controls
│   ├── Converter.tsx                # Crypto to fiat converter
│   ├── DataTable.tsx                # Reusable data table component
│   ├── Header.tsx                   # Navigation header
│   ├── LiveDataWrapper.tsx          # WebSocket data wrapper
│   ├── home/                        # Home page components
│   │   ├── CoinOverview.tsx         # Bitcoin overview section
│   │   ├── TrendingCoins.tsx        # Top trending coins display
│   │   ├── Categories.tsx           # Crypto categories
│   │   └── fallback.tsx             # Loading fallback UI
│   └── ui/                          # Radix UI component wrappers
│       ├── badge.tsx
│       ├── button.tsx
│       ├── input.tsx
│       ├── pagination.tsx
│       ├── select.tsx
│       ├── separator.tsx
│       └── table.tsx
│
├── hooks/                           # Custom React hooks
│   └── useCoinGeckoWebSocket.ts     # WebSocket connection hook
│
├── lib/                             # Utility functions
│   ├── coingecko.actions.ts         # CoinGecko API server actions
│   └── utils.ts                     # Helper functions
│
├── public/                          # Static assets
├── constants.ts                     # App-wide constants
├── type.d.ts                        # TypeScript type definitions
├── next.config.ts                   # Next.js configuration
├── tailwind.config.ts               # Tailwind CSS configuration
├── tsconfig.json                    # TypeScript configuration
├── components.json                  # shadcn/ui config
├── eslint.config.mjs                # ESLint configuration
├── postcss.config.mjs               # PostCSS configuration
└── package.json                     # Dependencies & scripts
```

---

## 🔗 API Integration

The app uses the **CoinGecko API** for all cryptocurrency data:

### Key API Endpoints Used:

- `GET /coins/markets` - Market data for multiple coins
- `GET /coins/{id}` - Detailed coin information
- `GET /coins/{id}/ohlc` - OHLCV candlestick data
- `GET /coins/{id}/tickers` - Trading pairs and tickers
- `GET /coins/{id}/market_chart` - Historical price data
- `GET /search/trending` - Trending coins
- `GET /coins/categories` - Crypto categories
- WebSocket subscriptions for real-time price & trade updates

---

## 🎯 Key Features In Detail

### Candlestick Charts

- Historical data visualization with multiple time periods
- Live streaming updates via WebSocket
- Interactive crosshairs and price tracking
- Responsive chart sizing for all devices

### CoinGecko WebSocket Hook (`useCoinGeckoWebSocket`)

The custom hook provides:

- Real-time price updates
- Live trade data
- OHLCV updates
- Automatic WebSocket connection management
- Message parsing and state updates

### Data Table Component

- Flexible column definitions
- Custom cell rendering
- Responsive layout
- Sortable columns

### Suspense Boundaries

- Progressive loading with fallback UI
- Improved perceived performance
- Server-side component streaming

---

## 🔐 Security Considerations

- **API Keys**: Private keys stored in environment variables (not in `.env`)
- **Public Keys**: Only `NEXT_PUBLIC_` prefixed keys exposed to client
- **Server Actions**: Private API calls executed server-side via Server Actions
- **Input Validation**: Form field validation before API calls
- **Error Handling**: Graceful error messages without exposing sensitive data

---

## 📱 Responsive Design

- Mobile-first approach with Tailwind CSS
- Responsive grid layouts
- Touch-friendly interactive elements
- Optimized chart rendering for all screen sizes
- Flexible component sizing

---

## 🎨 Color Scheme

| Element          | Color     | Purpose                |
| ---------------- | --------- | ---------------------- |
| Chart Background | `#0b1116` | Dark theme base        |
| Candle Up        | `#158A6E` | Green (price increase) |
| Candle Down      | `#EB1C36` | Red (price decrease)   |
| Text             | `#8f9fb1` | Secondary text color   |
| Grid             | `#1a2332` | Chart grid lines       |

---

## 🔄 Data Flow

```
Home Page
├── CoinOverview (Server Component)
│   ├── Fetches Bitcoin details & OHLCV data
│   └── Renders CandlestickChart
├── TrendingCoins (Server Component)
│   └── Fetches trending coins list
└── Categories (Server Component)
    └── Fetches crypto categories

Coins Page
├── Fetches paginated coins list
├── Renders DataTable with coin data
└── CoinsPagination for navigation

Coin Detail Page
├── Fetches coin details & OHLCV data
├── Renders CandlestickChart (with live WebSocket data)
├── LiveDataWrapper (WebSocket hook)
└── Converter component
```

---

## 🧪 Testing

To test the application:

1. **Test Data Fetching**: Navigate through pages to verify data loads correctly
2. **Test Live Updates**: Open a coin detail page and watch real-time price updates
3. **Test Converter**: Convert amounts between different currencies
4. **Test Pagination**: Navigate through different pages of coins
5. **Test Responsive Design**: Open DevTools and test on different screen sizes

---

## 🤝 Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

### Steps to contribute:

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

---


## 🙏 Acknowledgments

- [CoinGecko](https://www.coingecko.com/) for the comprehensive crypto API
- [TradingView](https://www.tradingview.com/) for the lightweight-charts library
- [Vercel](https://vercel.com/) for Next.js
- [Radix UI](https://www.radix-ui.com/) for accessible components
- [Tailwind CSS](https://tailwindcss.com/) for utility-first CSS

---

Built with ❤️ using **Next.js 16**, **React 19**, **TypeScript**, and **Tailwind CSS**
