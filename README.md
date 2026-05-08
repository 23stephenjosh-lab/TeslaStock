# TeslaStockimport { useState } from 'react'; import { LineChart, Line, ResponsiveContainer, XAxis, Tooltip } from 'recharts'; import { Bell, Bitcoin, Wallet, ShieldCheck, TrendingUp, UserCircle2 } from 'lucide-react';

export default function TeslaInvestorDashboard() { const [balance] = useState('$24,820.18');

const chartData = [ { day: 'Mon', value: 160 }, { day: 'Tue', value: 180 }, { day: 'Wed', value: 175 }, { day: 'Thu', value: 210 }, { day: 'Fri', value: 240 }, { day: 'Sat', value: 225 }, { day: 'Sun', value: 280 }, ]; const stats = [ { title: 'TSLA Price', value: '$198.42', change: '+4.12%' }, { title: 'Market Cap', value: '$632B', change: '+2.08%' }, { title: '24H Volume', value: '$18.3B', change: '+8.74%' }, { title: 'Portfolio Growth', value: '+32.8%', change: '+12.1%' }, ];

const news = [ 'Tesla expands AI and robotics division', 'Analysts predict strong TSLA rebound', 'Cybertruck production continues scaling globally', 'Tesla energy storage revenue increases significantly', ];

return ( <div className="min-h-screen bg-black text-white overflow-hidden"> <div className="absolute inset-0 bg-[radial-gradient(circle_at_top_right,rgba(220,38,38,0.18),transparent_35%)]"></div>

<nav className="relative z-10 border-b border-zinc-800 bg-black/70 backdrop-blur-xl px-6 py-4">
    <div className="max-w-7xl mx-auto flex items-center justify-between">
      <div className="flex items-center gap-3">
        <div className="w-11 h-11 rounded-2xl bg-red-600 flex items-center justify-center text-xl font-bold">
          T
        </div>
        <div>
          <h1 className="text-2xl font-bold">TeslaX Invest</h1>
          <p className="text-xs text-gray-400">Crypto & Stock Trading Platform</p>
        </div>
      </div>

      <div className="hidden md:flex items-center gap-6 text-gray-300">
        <span className="hover:text-white cursor-pointer">Dashboard</span>
        <span className="hover:text-white cursor-pointer">Markets</span>
        <span className="hover:text-white cursor-pointer">Analytics</span>
        <span className="hover:text-white cursor-pointer">Portfolio</span>
      </div>

      <div className="flex items-center gap-4">
        <Bell className="w-5 h-5 text-gray-300" />
        <UserCircle2 className="w-8 h-8 text-red-500" />
      </div>
    </div>
  </nav>

  <div className="relative z-10 min-h-screen bg-black text-white p-6">
<div className="min-h-screen bg-black text-white p-6">
  <div className="max-w-7xl mx-auto">
    <header className="flex flex-col lg:flex-row items-start lg:items-center justify-between mb-10 gap-6">
      <div>
        <h1 className="text-5xl font-bold tracking-tight">TESLA INVEST</h1>
        <p className="text-gray-400 mt-2 text-lg">
          Premium Crypto & Investor Dashboard
        </p>
      </div>

      <div className="flex gap-4 flex-wrap">
        <button className="bg-red-600 hover:bg-red-700 transition-all px-6 py-3 rounded-2xl text-lg font-semibold shadow-lg">
          Start Investing
        </button>

        <button className="bg-zinc-900 border border-zinc-700 hover:border-red-500 transition-all px-6 py-3 rounded-2xl text-lg font-semibold">
          Connect Wallet
        </button>
      </div>
    </header>

    <section className="grid grid-cols-1 lg:grid-cols-3 gap-6 mb-10">
      <div className="lg:col-span-2 bg-zinc-900 border border-zinc-800 rounded-3xl p-8 shadow-2xl">
        <div className="flex items-center justify-between mb-6">
          <div>
            <p className="text-gray-400">Total Portfolio Balance</p>
            <h2 className="text-5xl font-bold mt-2">{balance}</h2>
          </div>

          <div className="bg-green-500/10 text-green-400 px-4 py-2 rounded-2xl font-semibold">
            +18.4% This Month
          </div>
        </div>

        <div className="h-80 mt-8">
          <ResponsiveContainer width="100%" height="100%">
            <LineChart data={chartData}>
              <XAxis dataKey="day" stroke="#666" />
              <Tooltip />
              <Line type="monotone" dataKey="value" stroke="#ef4444" strokeWidth={4} dot={false} />
            </LineChart>
          </ResponsiveContainer>
        </div>
      </div>

      <div className="bg-zinc-900 border border-zinc-800 rounded-3xl p-6 shadow-2xl">
        <h2 className="text-2xl font-bold mb-6">Account Access</h2>

        <div className="space-y-4">
          <input
            type="email"
            placeholder="Email address"
            className="w-full bg-black border border-zinc-800 rounded-2xl p-4 outline-none focus:border-red-500"
          />

          <input
            type="password"
            placeholder="Password"
            className="w-full bg-black border border-zinc-800 rounded-2xl p-4 outline-none focus:border-red-500"
          />

          <button className="w-full bg-red-600 hover:bg-red-700 transition-all rounded-2xl py-4 font-semibold text-lg">
            Login / Register
          </button>

          <div className="flex items-center justify-center gap-2 text-green-400 text-sm pt-2">
            <ShieldCheck className="w-4 h-4" />
            SSL Secured Authentication
          </div>
        </div>
      </div>
    </section>

    <section className="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-4 gap-6 mb-10">
      {stats.map((stat, index) => (
        <div
          key={index}
          className="bg-zinc-900 border border-zinc-800 rounded-3xl p-6 shadow-2xl"
        >
          <p className="text-gray-400 text-sm mb-2">{stat.title}</p>
          <h2 className="text-3xl font-bold">{stat.value}</h2>
          <p className="text-green-400 mt-3 font-medium">{stat.change}</p>
        </div>
      ))}
    </section>

    <section className="grid grid-cols-1 lg:grid-cols-3 gap-6">
      <div className="lg:col-span-2 bg-zinc-900 border border-zinc-800 rounded-3xl p-6 shadow-2xl">
        <div className="flex items-center justify-between mb-6">
          <h2 className="text-2xl font-bold">TSLA Performance</h2>
          <span className="text-green-400 font-semibold">Live Market</span>
        </div>

        <div className="h-80 rounded-2xl bg-gradient-to-br from-red-600/20 to-black border border-zinc-800 p-6">
          <div className="grid grid-cols-2 gap-4 h-full">
            <div className="bg-black/40 rounded-2xl border border-zinc-800 p-5 flex flex-col justify-between">
              <div>
                <Bitcoin className="text-yellow-500 w-8 h-8 mb-3" />
                <h3 className="text-2xl font-bold">BTC/USD</h3>
              </div>
              <div>
                <p className="text-3xl font-bold">$102,884</p>
                <p className="text-green-400">+6.4%</p>
              </div>
            </div>

            <div className="bg-black/40 rounded-2xl border border-zinc-800 p-5 flex flex-col justify-between">
              <div>
                <TrendingUp className="text-green-400 w-8 h-8 mb-3" />
                <h3 className="text-2xl font-bold">TSLA</h3>
              </div>
              <div>
                <p className="text-3xl font-bold">$198.42</p>
                <p className="text-green-400">+4.12%</p>
              </div>
            </div>

            <div className="col-span-2 bg-black/40 rounded-2xl border border-zinc-800 p-5 flex items-center justify-between">
              <div>
                <p className="text-gray-400">AI Trading Signals</p>
                <h3 className="text-3xl font-bold mt-2">Bullish Market Detected</h3>
              </div>

              <button className="bg-red-600 hover:bg-red-700 transition-all px-5 py-3 rounded-2xl font-semibold">
                Activate Bot
              </button>
            </div>
          </div>
        </div>
      </div>
      </div>

      <div className="bg-zinc-900 border border-zinc-800 rounded-3xl p-6 shadow-2xl">
        <h2 className="text-2xl font-bold mb-6">Latest News</h2>

        <div className="space-y-4">
          {news.map((item, index) => (
            <div
              key={index}
              className="bg-black border border-zinc-800 rounded-2xl p-4 hover:border-red-500 transition-all"
            >
              <p className="text-gray-200">{item}</p>
            </div>
          ))}
        </div>
      </div>
    </section>

    <section className="grid grid-cols-1 lg:grid-cols-2 gap-6 mt-10">
      <div className="bg-zinc-900 border border-zinc-800 rounded-3xl p-6 shadow-2xl">
        <h2 className="text-2xl font-bold mb-6">Portfolio Allocation</h2>

        <div className="space-y-5">
          <div>
            <div className="flex justify-between mb-2">
              <span>TSLA</span>
              <span>68%</span>
            </div>
            <div className="w-full h-3 bg-zinc-800 rounded-full overflow-hidden">
              <div className="h-full w-[68%] bg-red-600 rounded-full"></div>
            </div>
          </div>

          <div>
            <div className="flex justify-between mb-2">
              <span>BTC</span>
              <span>22%</span>
            </div>
            <div className="w-full h-3 bg-zinc-800 rounded-full overflow-hidden">
              <div className="h-full w-[22%] bg-green-500 rounded-full"></div>
            </div>
          </div>

          <div>
            <div className="flex justify-between mb-2">
              <span>ETH</span>
              <span>10%</span>
            </div>
            <div className="w-full h-3 bg-zinc-800 rounded-full overflow-hidden">
              <div className="h-full w-[10%] bg-blue-500 rounded-full"></div>
            </div>
          </div>
        </div>
      </div>

      <div className="bg-zinc-900 border border-zinc-800 rounded-3xl p-6 shadow-2xl">
        <h2 className="text-2xl font-bold mb-6">Quick Actions & Payments</h2>

        <div className="grid grid-cols-2 gap-4">
          <button className="bg-red-600 hover:bg-red-700 transition-all rounded-2xl py-4 font-semibold text-lg">
            Buy TSLA
          </button>

          <button className="bg-green-600 hover:bg-green-700 transition-all rounded-2xl py-4 font-semibold text-lg">
            Trade Crypto
          </button>

          <button className="bg-zinc-800 hover:bg-zinc-700 transition-all rounded-2xl py-4 font-semibold text-lg">
            View Analytics
          </button>

          <button className="bg-zinc-800 hover:bg-zinc-700 transition-all rounded-2xl py-4 font-semibold text-lg">
            Investor Reports
          </button>

          <button className="bg-purple-600 hover:bg-purple-700 transition-all rounded-2xl py-4 font-semibold text-lg col-span-2 flex items-center justify-center gap-2">
            <Wallet className="w-5 h-5" />
            Deposit Funds
          </button>
        </div>
      </div>
    </section>

    <footer className="mt-12 text-center text-gray-500 text-sm">
      Tesla Investor Dashboard • Premium Financial Interface
    </footer>
  </div>
</div>

); }