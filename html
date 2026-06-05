// App.tsx - Главный файл приложения
import React, { useState, useEffect, createContext, useContext } from 'react';
import { BrowserRouter as Router, Routes, Route, useNavigate, useLocation } from 'react-router-dom';
import { 
  Home, Search, Heart, MessageCircle, User, Bell, Settings, 
  Moon, Sun, ChevronLeft, MapPin, Phone, Send, Camera,
  Filter, Star, CheckCircle, Shield, Zap, Building,
  Plus, X, LogOut, Menu, MoreVertical, Video, Mic
} from 'lucide-react';

// ==================== TYPES ====================
interface User {
  id: string;
  name: string;
  phone: string;
  email?: string;
  avatar?: string;
  role: 'client' | 'realtor';
  isVerified?: boolean;
}

interface Property {
  id: string;
  title: string;
  address: string;
  price: number;
  rooms: number;
  area: number;
  floor: number;
  images: string[];
  video?: string;
  description: string;
  amenities: string[];
  location: { lat: number; lng: number };
  realtor: User;
  isVerified: boolean;
  createdAt: string;
  reviews: Review[];
  rating: number;
}

interface Review {
  id: string;
  userId: string;
  userName: string;
  rating: number;
  comment: string;
  date: string;
}

interface Message {
  id: string;
  senderId: string;
  receiverId: string;
  text: string;
  timestamp: Date;
  read: boolean;
  type: 'text' | 'image' | 'voice';
}

interface Chat {
  id: string;
  participant: User;
  lastMessage: Message;
  unreadCount: number;
  property?: Property;
}

// ==================== CONTEXT ====================
interface AppContextType {
  user: User | null;
  setUser: (user: User | null) => void;
  isDarkMode: boolean;
  toggleTheme: () => void;
  properties: Property[];
  chats: Chat[];
  currentUser: User;
}

const AppContext = createContext<AppContextType | undefined>(undefined);

const useAppContext = () => {
  const context = useContext(AppContext);
  if (!context) throw new Error('useAppContext must be used within AppProvider');
  return context;
};

// ==================== MOCK DATA ====================
const mockProperties: Property[] = [
  {
    id: '1',
    title: 'ЖК Highvill Astana - 2-комнатная',
    address: 'Левый берег, ул. Кабанбай батыра',
    price: 350000,
    rooms: 2,
    area: 68,
    floor: 18,
    images: [
      'https://images.unsplash.com/photo-1502672260266-1c1ef2d93688?w=800',
      'https://images.unsplash.com/photo-1560448204-e02f11c3d0e2?w=800',
      'https://images.unsplash.com/photo-1484154218962-a1c002085d2f?w=800'
    ],
    video: 'https://example.com/video.mp4',
    description: 'Роскошная 2-комнатная квартира в ЖК Highvill с панорамным видом на город. Полностью меблирована, вся бытовая техника.',
    amenities: ['Парковка', 'Кондиционер', 'Балкон', 'Охрана'],
    location: { lat: 51.1605, lng: 71.4704 },
    realtor: {
      id: 'r1',
      name: 'Данияр Н.',
      phone: '+7 701 234 5678',
      role: 'realtor',
      isVerified: true,
      avatar: 'https://i.pravatar.cc/150?img=11'
    },
    isVerified: true,
    createdAt: '2024-01-15',
    rating: 4.9,
    reviews: [
      {
        id: 'rev1',
        userId: 'u1',
        userName: 'Айгуль',
        rating: 5,
        comment: 'Всё как на фото, тихий двор, хозяин адекватный.',
        date: '2024-01-10'
      }
    ]
  },
  {
    id: '2',
    title: 'ЖК Highvill - 2-комн. квартира',
    address: 'ул. Керей Жәнібек, 12/1',
    price: 280000,
    rooms: 2,
    area: 65,
    floor: 12,
    images: [
      'https://images.unsplash.com/photo-1522708323590-d24dbb6b0267?w=800',
      'https://images.unsplash.com/photo-1505691938895-1758d7feb511?w=800'
    ],
    description: 'Уютная 2-комнатная квартира в ЖК Highvill. Полностью меблирована, бытовая техника, кондиционер, балкон.',
    amenities: ['Парковка', 'Кондиционер', 'Балкон'],
    location: { lat: 51.1505, lng: 71.4604 },
    realtor: {
      id: 'r2',
      name: 'Алия С.',
      phone: '+7 701 123 4567',
      role: 'realtor',
      isVerified: true,
      avatar: 'https://i.pravatar.cc/150?img=5'
    },
    isVerified: true,
    createdAt: '2024-01-14',
    rating: 4.9,
    reviews: []
  }
];

const mockChats: Chat[] = [
  {
    id: 'c1',
    participant: {
      id: 'r1',
      name: 'Данияр Н.',
      phone: '+7 701 234 5678',
      role: 'realtor',
      avatar: 'https://i.pravatar.cc/150?img=11'
    },
    lastMessage: {
      id: 'm1',
      senderId: 'r1',
      receiverId: 'current',
      text: 'Да, актуальна. Можем показать сегодня в 19:00',
      timestamp: new Date('2024-01-15T11:42:00'),
      read: true,
      type: 'text'
    },
    unreadCount: 0,
    property: mockProperties[0]
  }
];

const mockMessages: Message[] = [
  {
    id: 'm1',
    senderId: 'current',
    receiverId: 'r1',
    text: 'Здравствуйте! Квартира ещё актуальна?',
    timestamp: new Date('2024-01-15T11:40:00'),
    read: true,
    type: 'text'
  },
  {
    id: 'm2',
    senderId: 'r1',
    receiverId: 'current',
    text: 'Да, актуальна. Можем показать сегодня в 19:00',
    timestamp: new Date('2024-01-15T11:42:00'),
    read: true,
    type: 'text'
  },
  {
    id: 'm3',
    senderId: 'current',
    receiverId: 'r1',
    text: 'Да, удобно',
    timestamp: new Date('2024-01-15T11:45:00'),
    read: true,
    type: 'text'
  }
];

// ==================== COMPONENTS ====================

// Theme Toggle Component
const ThemeToggle: React.FC = () => {
  const { isDarkMode, toggleTheme } = useAppContext();
  
  return (
    <button
      onClick={toggleTheme}
      className="p-2 rounded-full hover:bg-gray-200 dark:hover:bg-gray-700 transition-colors"
    >
      {isDarkMode ? <Sun size={20} /> : <Moon size={20} />}
    </button>
  );
};

// Auth Button Component
const AuthButton: React.FC = () => {
  const { user } = useAppContext();
  const navigate = useNavigate();
  
  if (user) {
    return (
      <button
        onClick={() => navigate('/profile')}
        className="flex items-center gap-2 px-4 py-2 bg-blue-500 text-white rounded-full hover:bg-blue-600 transition-colors"
      >
        <User size={18} />
        <span className="hidden sm:inline">{user.name}</span>
      </button>
    );
  }
  
  return (
    <div className="flex gap-2">
      <button
        onClick={() => navigate('/login')}
        className="px-4 py-2 text-blue-500 hover:bg-blue-50 dark:hover:bg-gray-800 rounded-full transition-colors"
      >
        Войти
      </button>
      <button
        onClick={() => navigate('/register')}
        className="px-4 py-2 bg-blue-500 text-white rounded-full hover:bg-blue-600 transition-colors"
      >
        Регистрация
      </button>
    </div>
  );
};

// Header Component
const Header: React.FC<{ showBack?: boolean; title?: string }> = ({ showBack = false, title }) => {
  const navigate = useNavigate();
  
  return (
    <header className="sticky top-0 z-50 bg-white dark:bg-gray-900 border-b border-gray-200 dark:border-gray-800">
      <div className="max-w-7xl mx-auto px-4 h-14 flex items-center justify-between">
        <div className="flex items-center gap-3">
          {showBack && (
            <button
              onClick={() => navigate(-1)}
              className="p-2 -ml-2 hover:bg-gray-100 dark:hover:bg-gray-800 rounded-full transition-colors"
            >
              <ChevronLeft size={24} />
            </button>
          )}
          <h1 
            onClick={() => navigate('/')}
            className="text-xl font-bold bg-gradient-to-r from-blue-600 to-cyan-500 bg-clip-text text-transparent cursor-pointer"
          >
            {title || 'QalaRent'}
          </h1>
        </div>
        
        <div className="flex items-center gap-2">
          <ThemeToggle />
          <AuthButton />
        </div>
      </div>
    </header>
  );
};

// Bottom Navigation
const BottomNav: React.FC = () => {
  const navigate = useNavigate();
  const location = useLocation();
  
  const navItems = [
    { icon: Home, label: 'Главная', path: '/' },
    { icon: Search, label: 'Поиск', path: '/search' },
    { icon: Heart, label: 'Избранное', path: '/favorites' },
    { icon: MessageCircle, label: 'Сообщения', path: '/messages', badge: 2 },
    { icon: User, label: 'Профиль', path: '/profile' },
  ];
  
  return (
    <nav className="fixed bottom-0 left-0 right-0 bg-white dark:bg-gray-900 border-t border-gray-200 dark:border-gray-800 pb-safe">
      <div className="max-w-7xl mx-auto px-4">
        <div className="flex justify-around items-center h-16">
          {navItems.map((item) => {
            const isActive = location.pathname === item.path;
            return (
              <button
                key={item.path}
                onClick={() => navigate(item.path)}
                className={`relative flex flex-col items-center justify-center w-full h-full ${
                  isActive ? 'text-blue-500' : 'text-gray-500 dark:text-gray-400'
                }`}
              >
                <item.icon size={24} />
                <span className="text-xs mt-1">{item.label}</span>
                {item.badge && (
                  <span className="absolute top-2 right-6 bg-red-500 text-white text-xs rounded-full w-5 h-5 flex items-center justify-center">
                    {item.badge}
                  </span>
                )}
              </button>
            );
          })}
        </div>
      </div>
    </nav>
  );
};

// Property Card Component
const PropertyCard: React.FC<{ property: Property; onClick?: () => void }> = ({ property, onClick }) => {
  return (
    <div 
      onClick={onClick}
      className="bg-white dark:bg-gray-800 rounded-2xl overflow-hidden shadow-lg hover:shadow-xl transition-shadow cursor-pointer"
    >
      <div className="relative aspect-[4/3]">
        <img 
          src={property.images[0]} 
          alt={property.title}
          className="w-full h-full object-cover"
        />
        {property.video && (
          <div className="absolute inset-0 flex items-center justify-center bg-black/30">
            <div className="w-16 h-16 bg-white/90 rounded-full flex items-center justify-center">
              <Video size={32} className="text-gray-800 ml-1" />
            </div>
          </div>
        )}
        {property.isVerified && (
          <div className="absolute top-3 left-3 bg-green-500 text-white px-3 py-1 rounded-full text-sm flex items-center gap-1">
            <CheckCircle size={16} />
            Проверено
          </div>
        )}
        <button className="absolute top-3 right-3 p-2 bg-white/90 dark:bg-gray-800/90 rounded-full hover:bg-white transition-colors">
          <Heart size={20} className="text-gray-600 dark:text-gray-300" />
        </button>
      </div>
      
      <div className="p-4">
        <div className="flex justify-between items-start mb-2">
          <h3 className="font-semibold text-lg dark:text-white">{property.price.toLocaleString()} ₸/мес</h3>
          <div className="flex items-center gap-1 text-yellow-500">
            <Star size={16} fill="currentColor" />
            <span className="text-sm font-medium">{property.rating}</span>
          </div>
        </div>
        
        <p className="text-gray-600 dark:text-gray-300 mb-2">{property.title}</p>
        <p className="text-gray-500 dark:text-gray-400 text-sm mb-3">{property.address}</p>
        
        <div className="flex items-center gap-4 text-sm text-gray-500 dark:text-gray-400">
          <span>{property.rooms}-комн.</span>
          <span>{property.area} м²</span>
          <span>{property.floor} этаж</span>
        </div>
        
        <div className="mt-3 pt-3 border-t border-gray-100 dark:border-gray-700 flex items-center gap-2">
          <img 
            src={property.realtor.avatar} 
            alt={property.realtor.name}
            className="w-8 h-8 rounded-full"
          />
          <div className="flex-1">
            <p className="text-sm font-medium dark:text-white">{property.realtor.name}</p>
            {property.realtor.isVerified && (
              <p className="text-xs text-green-500">Проверенный риелтор</p>
            )}
          </div>
        </div>
      </div>
    </div>
  );
};

// Map Component (Simplified)
const MapView: React.FC<{ properties: Property[] }> = ({ properties }) => {
  return (
    <div className="relative w-full h-full bg-gray-100 dark:bg-gray-800 rounded-2xl overflow-hidden">
      <div className="absolute inset-0 bg-gradient-to-br from-blue-50 to-cyan-50 dark:from-gray-800 dark:to-gray-900">
        {/* Simplified map visualization */}
        <div className="absolute inset-0 opacity-20">
          <svg className="w-full h-full" viewBox="0 0 100 100">
            <pattern id="grid" width="10" height="10" patternUnits="userSpaceOnUse">
              <path d="M 10 0 L 0 0 0 10" fill="none" stroke="currentColor" strokeWidth="0.5"/>
            </pattern>
            <rect width="100" height="100" fill="url(#grid)" />
          </svg>
        </div>
        
        {/* Property markers */}
        {properties.map((property, index) => (
          <div
            key={property.id}
            className="absolute transform -translate-x-1/2 -translate-y-1/2"
            style={{
              left: `${30 + index * 20}%`,
              top: `${40 + (index % 2) * 20}%`
            }}
          >
            <div className="bg-blue-500 text-white px-3 py-1.5 rounded-full text-sm font-semibold shadow-lg whitespace-nowrap">
              {(property.price / 1000).toFixed(0)}k
            </div>
          </div>
        ))}
      </div>
      
      <div className="absolute bottom-4 left-4 right-4 bg-white dark:bg-gray-800 p-3 rounded-xl shadow-lg">
        <div className="flex items-center justify-between">
          <div className="flex items-center gap-2">
            <MapPin size={20} className="text-blue-500" />
            <span className="font-medium dark:text-white">Астана</span>
          </div>
          <button className="p-2 bg-gray-100 dark:bg-gray-700 rounded-lg">
            <Filter size={20} />
          </button>
        </div>
      </div>
    </div>
  );
};

// Chat Interface (WhatsApp-like)
const ChatInterface: React.FC<{ chat: Chat }> = ({ chat }) => {
  const [messages, setMessages] = useState<Message[]>(mockMessages);
  const [inputText, setInputText] = useState('');
  const messagesEndRef = React.useRef<HTMLDivElement>(null);
  
  const scrollToBottom = () => {
    messagesEndRef.current?.scrollIntoView({ behavior: 'smooth' });
  };
  
  useEffect(() => {
    scrollToBottom();
  }, [messages]);
  
  const handleSend = () => {
    if (!inputText.trim()) return;
    
    const newMessage: Message = {
      id: Date.now().toString(),
      senderId: 'current',
      receiverId: chat.participant.id,
      text: inputText,
      timestamp: new Date(),
      read: false,
      type: 'text'
    };
    
    setMessages([...messages, newMessage]);
    setInputText('');
    
    // Simulate reply
    setTimeout(() => {
      const reply: Message = {
        id: (Date.now() + 1).toString(),
        senderId: chat.participant.id,
        receiverId: 'current',
        text: 'Спасибо за сообщение! Я скоро отвечу.',
        timestamp: new Date(),
        read: false,
        type: 'text'
      };
      setMessages(prev => [...prev, reply]);
    }, 2000);
  };
  
  const formatTime = (date: Date) => {
    return date.toLocaleTimeString('ru-RU', { hour: '2-digit', minute: '2-digit' });
  };
  
  return (
    <div className="flex flex-col h-[calc(100vh-140px)]">
      {/* Chat Header */}
      <div className="flex items-center gap-3 p-4 border-b border-gray-200 dark:border-gray-700 bg-white dark:bg-gray-900">
        <img 
          src={chat.participant.avatar} 
          alt={chat.participant.name}
          className="w-10 h-10 rounded-full"
        />
        <div className="flex-1">
          <h3 className="font-semibold dark:text-white">{chat.participant.name}</h3>
          <p className="text-xs text-green-500">онлайн</p>
        </div>
        <button className="p-2 hover:bg-gray-100 dark:hover:bg-gray-800 rounded-full">
          <Phone size={20} className="text-blue-500" />
        </button>
      </div>
      
      {/* Messages */}
      <div className="flex-1 overflow-y-auto p-4 space-y-4 bg-gray-50 dark:bg-gray-950">
        {messages.map((message) => {
          const isMe = message.senderId === 'current';
          return (
            <div
              key={message.id}
              className={`flex ${isMe ? 'justify-end' : 'justify-start'}`}
            >
              <div
                className={`max-w-[70%] px-4 py-2 rounded-2xl ${
                  isMe
                    ? 'bg-blue-500 text-white rounded-br-none'
                    : 'bg-white dark:bg-gray-800 dark:text-white rounded-bl-none shadow'
                }`}
              >
                <p>{message.text}</p>
                <div className={`flex items-center gap-1 mt-1 text-xs ${isMe ? 'text-blue-100' : 'text-gray-400'}`}>
                  <span>{formatTime(message.timestamp)}</span>
                  {isMe && (
                    <CheckCircle size={12} className={message.read ? 'text-white' : 'text-blue-200'} />
                  )}
                </div>
              </div>
            </div>
          );
        })}
        <div ref={messagesEndRef} />
      </div>
      
      {/* Input */}
      <div className="p-4 bg-white dark:bg-gray-900 border-t border-gray-200 dark:border-gray-700">
        <div className="flex items-center gap-2">
          <button className="p-2 hover:bg-gray-100 dark:hover:bg-gray-800 rounded-full">
            <Camera size={24} className="text-gray-500" />
          </button>
          <button className="p-2 hover:bg-gray-100 dark:hover:bg-gray-800 rounded-full">
            <Mic size={24} className="text-gray-500" />
          </button>
          <input
            type="text"
            value={inputText}
            onChange={(e) => setInputText(e.target.value)}
            onKeyPress={(e) => e.key === 'Enter' && handleSend()}
            placeholder="Введите сообщение..."
            className="flex-1 px-4 py-2 bg-gray-100 dark:bg-gray-800 rounded-full outline-none dark:text-white"
          />
          <button
            onClick={handleSend}
            className="p-3 bg-blue-500 text-white rounded-full hover:bg-blue-600 transition-colors"
          >
            <Send size={20} />
          </button>
        </div>
      </div>
    </div>
  );
};

// ==================== PAGES ====================

// Home Page
const HomePage: React.FC = () => {
  const navigate = useNavigate();
  const { properties } = useAppContext();
  const [showMap, setShowMap] = useState(false);
  
  const quickFilters = [
    { icon: Building, label: '2-комн до 350k', color: 'bg-blue-100 text-blue-600' },
    { icon: Building, label: 'Коммерция', color: 'bg-red-100 text-red-600' },
    { icon: Building, label: 'Посуточно', color: 'bg-orange-100 text-orange-600' },
    { icon: Building, label: 'Дом с участком', color: 'bg-purple-100 text-purple-600' },
  ];
  
  return (
    <div className="pb-20">
      {/* Search Bar */}
      <div className="p-4 bg-white dark:bg-gray-900 sticky top-14 z-40 border-b border-gray-200 dark:border-gray-800">
        <div className="relative">
          <Search className="absolute left-4 top-1/2 transform -translate-y-1/2 text-gray-400" size={20} />
          <input
            type="text"
            placeholder="Что ищем?"
            className="w-full pl-12 pr-4 py-3 bg-gray-100 dark:bg-gray-800 rounded-2xl outline-none dark:text-white"
          />
          <button className="absolute right-3 top-1/2 transform -translate-y-1/2 p-2">
            <Mic size={20} className="text-gray-400" />
          </button>
        </div>
        
        {/* Quick Filters */}
        <div className="flex gap-2 mt-3 overflow-x-auto pb-2">
          {quickFilters.map((filter, index) => (
            <button
              key={index}
              className={`flex items-center gap-2 px-4 py-2 rounded-full whitespace-nowrap ${filter.color}`}
            >
              <filter.icon size={16} />
              <span className="text-sm font-medium">{filter.label}</span>
            </button>
          ))}
        </div>
        
        {/* Map Toggle */}
        <div className="mt-3 flex gap-2">
          <button
            onClick={() => setShowMap(!showMap)}
            className={`flex-1 py-2 rounded-xl font-medium transition-colors ${
              showMap 
                ? 'bg-blue-500 text-white' 
                : 'bg-gray-100 dark:bg-gray-800 dark:text-white'
            }`}
          >
            {showMap ? 'Список' : 'Карта'}
          </button>
        </div>
      </div>
      
      {/* Content */}
      {showMap ? (
        <div className="p-4 h-[calc(100vh-280px)]">
          <MapView properties={properties} />
        </div>
      ) : (
        <div className="p-4 grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-4">
          {properties.map((property) => (
            <PropertyCard 
              key={property.id} 
              property={property}
              onClick={() => navigate(`/property/${property.id}`)}
            />
          ))}
        </div>
      )}
    </div>
  );
};

// Property Detail Page
const PropertyDetailPage: React.FC<{ propertyId: string }> = ({ propertyId }) => {
  const { properties } = useAppContext();
  const navigate = useNavigate();
  const property = properties.find(p => p.id === propertyId);
  
  if (!property) return <div>Not found</div>;
  
  return (
    <div className="pb-20">
      {/* Image Gallery */}
      <div className="relative aspect-[4/3]">
        <img 
          src={property.images[0]} 
          alt={property.title}
          className="w-full h-full object-cover"
        />
        <div className="absolute top-4 left-4 right-4 flex justify-between">
          <button
            onClick={() => navigate(-1)}
            className="p-2 bg-white/90 dark:bg-gray-800/90 rounded-full"
          >
            <ChevronLeft size={24} />
          </button>
          <div className="flex gap-2">
            <button className="p-2 bg-white/90 dark:bg-gray-800/90 rounded-full">
              <Heart size={24} />
            </button>
            <button className="p-2 bg-white/90 dark:bg-gray-800/90 rounded-full">
              <MoreVertical size={24} />
            </button>
          </div>
        </div>
        <div className="absolute bottom-4 right-4 bg-black/60 text-white px-3 py-1 rounded-full text-sm">
          1/{property.images.length}
        </div>
      </div>
      
      <div className="p-4 space-y-6">
        {/* Price and Title */}
        <div>
          <div className="flex items-center gap-2 mb-2">
            {property.isVerified && (
              <span className="bg-green-500 text-white px-3 py-1 rounded-full text-sm flex items-center gap-1">
                <CheckCircle size={16} />
                Проверено
              </span>
            )}
          </div>
          <h1 className="text-2xl font-bold dark:text-white mb-2">{property.price.toLocaleString()} ₸/мес</h1>
          <h2 className="text-lg text-gray-600 dark:text-gray-300">{property.title}</h2>
          <p className="text-gray-500 dark:text-gray-400 flex items-center gap-1 mt-1">
            <MapPin size={16} />
            {property.address}
          </p>
        </div>
        
        {/* Features */}
        <div className="flex gap-4">
          <div className="flex-1 bg-gray-50 dark:bg-gray-800 p-3 rounded-xl text-center">
            <p className="text-2xl font-bold text-blue-500">{property.rooms}</p>
            <p className="text-sm text-gray-500">комнаты</p>
          </div>
          <div className="flex-1 bg-gray-50 dark:bg-gray-800 p-3 rounded-xl text-center">
            <p className="text-2xl font-bold text-blue-500">{property.area}</p>
            <p className="text-sm text-gray-500">м² площадь</p>
          </div>
          <div className="flex-1 bg-gray-50 dark:bg-gray-800 p-3 rounded-xl text-center">
            <p className="text-2xl font-bold text-blue-500">{property.floor}</p>
            <p className="text-sm text-gray-500">этаж</p>
          </div>
        </div>
        
        {/* Description */}
        <div>
          <h3 className="font-semibold text-lg mb-2 dark:text-white">Описание</h3>
          <p className="text-gray-600 dark:text-gray-300">{property.description}</p>
        </div>
        
        {/* Amenities */}
        <div>
          <h3 className="font-semibold text-lg mb-3 dark:text-white">Удобства</h3>
          <div className="flex flex-wrap gap-2">
            {property.amenities.map((amenity, index) => (
              <span 
                key={index}
                className="px-3 py-1 bg-blue-50 dark:bg-blue-900/30 text-blue-600 dark:text-blue-400 rounded-full text-sm"
              >
                {amenity}
              </span>
            ))}
          </div>
        </div>
        
        {/* Reviews */}
        <div>
          <div className="flex items-center justify-between mb-3">
            <h3 className="font-semibold text-lg dark:text-white">Отзывы ({property.reviews.length})</h3>
            <div className="flex items-center gap-1">
              <Star size={20} className="text-yellow-500" fill="currentColor" />
              <span className="font-semibold dark:text-white">{property.rating}</span>
            </div>
          </div>
          {property.reviews.map((review) => (
            <div key={review.id} className="border-b border-gray-100 dark:border-gray-800 pb-4 mb-4">
              <div className="flex items-center gap-2 mb-2">
                <div className="w-8 h-8 bg-blue-500 rounded-full flex items-center justify-center text-white font-semibold">
                  {review.userName[0]}
                </div>
                <div>
                  <p className="font-medium dark:text-white">{review.userName}</p>
                  <div className="flex text-yellow-500">
                    {[...Array(review.rating)].map((_, i) => (
                      <Star key={i} size={12} fill="currentColor" />
                    ))}
                  </div>
                </div>
              </div>
              <p className="text-gray-600 dark:text-gray-300 text-sm">{review.comment}</p>
            </div>
          ))}
        </div>
        
        {/* Realtor */}
        <div className="bg-gray-50 dark:bg-gray-800 p-4 rounded-2xl">
          <div className="flex items-center gap-3 mb-4">
            <img 
              src={property.realtor.avatar} 
              alt={property.realtor.name}
              className="w-12 h-12 rounded-full"
            />
            <div className="flex-1">
              <h3 className="font-semibold dark:text-white">{property.realtor.name}</h3>
              <p className="text-sm text-gray-500">Риелтор</p>
            </div>
            {property.realtor.isVerified && (
              <CheckCircle size={20} className="text-blue-500" />
            )}
          </div>
          <div className="grid grid-cols-2 gap-2">
            <button 
              onClick={() => navigate('/messages')}
              className="py-3 bg-blue-500 text-white rounded-xl font-medium hover:bg-blue-600 transition-colors"
            >
              Написать
            </button>
            <button className="py-3 bg-green-500 text-white rounded-xl font-medium hover:bg-green-600 transition-colors flex items-center justify-center gap-2">
              <Phone size={18} />
              Позвонить
            </button>
          </div>
        </div>
      </div>
    </div>
  );
};

// Messages Page
const MessagesPage: React.FC = () => {
  const { chats } = useAppContext();
  const navigate = useNavigate();
  
  return (
    <div className="pb-20">
      <div className="p-4 border-b border-gray-200 dark:border-gray-800 bg-white dark:bg-gray-900 sticky top-14">
        <h1 className="text-2xl font-bold dark:text-white">Сообщения</h1>
      </div>
      
      <div className="divide-y divide-gray-100 dark:divide-gray-800">
        {chats.map((chat) => (
          <div
            key={chat.id}
            onClick={() => navigate(`/chat/${chat.id}`)}
            className="p-4 hover:bg-gray-50 dark:hover:bg-gray-800 cursor-pointer transition-colors"
          >
            <div className="flex gap-3">
              <div className="relative">
                <img 
                  src={chat.participant.avatar} 
                  alt={chat.participant.name}
                  className="w-12 h-12 rounded-full"
                />
                {chat.unreadCount > 0 && (
                  <div className="absolute -top-1 -right-1 bg-blue-500 text-white text-xs rounded-full w-5 h-5 flex items-center justify-center">
                    {chat.unreadCount}
                  </div>
                )}
              </div>
              <div className="flex-1 min-w-0">
                <div className="flex justify-between items-start mb-1">
                  <h3 className="font-semibold dark:text-white truncate">{chat.participant.name}</h3>
                  <span className="text-xs text-gray-400">
                    {new Date(chat.lastMessage.timestamp).toLocaleTimeString('ru-RU', { 
                      hour: '2-digit', 
                      minute: '2-digit' 
                    })}
                  </span>
                </div>
                <p className={`text-sm truncate ${chat.unreadCount > 0 ? 'font-semibold dark:text-white' : 'text-gray-500'}`}>
                  {chat.lastMessage.text}
                </p>
                {chat.property && (
                  <p className="text-xs text-blue-500 mt-1">{chat.property.title}</p>
                )}
              </div>
            </div>
          </div>
        ))}
      </div>
    </div>
  );
};

// Chat Page
const ChatPage: React.FC<{ chatId: string }> = ({ chatId }) => {
  const { chats } = useAppContext();
  const chat = chats.find(c => c.id === chatId);
  
  if (!chat) return <div>Chat not found</div>;
  
  return <ChatInterface chat={chat} />;
};

// Login Page
const LoginPage: React.FC = () => {
  const { setUser } = useAppContext();
  const navigate = useNavigate();
  const [phone, setPhone] = useState('');
  
  const handleLogin = (e: React.FormEvent) => {
    e.preventDefault();
    const user: User = {
      id: 'current',
      name: 'Пользователь',
      phone,
      role: 'client'
    };
    setUser(user);
    navigate('/');
  };
  
  return (
    <div className="min-h-screen flex items-center justify-center p-4 bg-gray-50 dark:bg-gray-950">
      <div className="w-full max-w-md bg-white dark:bg-gray-900 rounded-3xl p-8 shadow-xl">
        <h1 className="text-3xl font-bold text-center mb-2 bg-gradient-to-r from-blue-600 to-cyan-500 bg-clip-text text-transparent">
          QalaRent
        </h1>
        <p className="text-center text-gray-500 mb-8">Недвижимость без стресса</p>
        
        <form onSubmit={handleLogin} className="space-y-4">
          <div>
            <label className="block text-sm font-medium mb-2 dark:text-white">Телефон</label>
            <input
              type="tel"
              value={phone}
              onChange={(e) => setPhone(e.target.value)}
              placeholder="+7 (___) ___-__-__"
              className="w-full px-4 py-3 bg-gray-100 dark:bg-gray-800 rounded-xl outline-none dark:text-white"
              required
            />
          </div>
          
          <button
            type="submit"
            className="w-full py-3 bg-blue-500 text-white rounded-xl font-semibold hover:bg-blue-600 transition-colors"
          >
            Войти
          </button>
        </form>
        
        <div className="mt-6 text-center">
          <button
            onClick={() => navigate('/register')}
            className="text-blue-500 hover:underline"
          >
            Нет аккаунта? Зарегистрироваться
          </button>
        </div>
        
        <button
          onClick={() => navigate('/')}
          className="mt-4 w-full py-2 text-gray-500 hover:text-gray-700 dark:hover:text-gray-300"
        >
          Продолжить без регистрации
        </button>
      </div>
    </div>
  );
};

// Register Page
const RegisterPage: React.FC = () => {
  const { setUser } = useAppContext();
  const navigate = useNavigate();
  const [formData, setFormData] = useState({
    name: '',
    phone: '',
    role: 'client' as 'client' | 'realtor'
  });
  
  const handleRegister = (e: React.FormEvent) => {
    e.preventDefault();
    const user: User = {
      id: 'current',
      ...formData,
      isVerified: false
    };
    setUser(user);
    navigate('/');
  };
  
  return (
    <div className="min-h-screen flex items-center justify-center p-4 bg-gray-50 dark:bg-gray-950">
      <div className="w-full max-w-md bg-white dark:bg-gray-900 rounded-3xl p-8 shadow-xl">
        <h1 className="text-3xl font-bold text-center mb-8 dark:text-white">Регистрация</h1>
        
        <form onSubmit={handleRegister} className="space-y-4">
          <div>
            <label className="block text-sm font-medium mb-2 dark:text-white">Имя</label>
            <input
              type="text"
              value={formData.name}
              onChange={(e) => setFormData({...formData, name: e.target.value})}
              className="w-full px-4 py-3 bg-gray-100 dark:bg-gray-800 rounded-xl outline-none dark:text-white"
              required
            />
          </div>
          
          <div>
            <label className="block text-sm font-medium mb-2 dark:text-white">Телефон</label>
            <input
              type="tel"
              value={formData.phone}
              onChange={(e) => setFormData({...formData, phone: e.target.value})}
              placeholder="+7 (___) ___-__-__"
              className="w-full px-4 py-3 bg-gray-100 dark:bg-gray-800 rounded-xl outline-none dark:text-white"
              required
            />
          </div>
          
          <div>
            <label className="block text-sm font-medium mb-2 dark:text-white">Выберите роль</label>
            <div className="space-y-2">
              <label className="flex items-center gap-3 p-3 border-2 border-gray-200 dark:border-gray-700 rounded-xl cursor-pointer hover:border-blue-500 transition-colors">
                <input
                  type="radio"
                  name="role"
                  value="client"
                  checked={formData.role === 'client'}
                  onChange={(e) => setFormData({...formData, role: e.target.value as 'client'})}
                  className="w-4 h-4 text-blue-500"
                />
                <span className="dark:text-white">Клиент</span>
              </label>
              <label className="flex items-center gap-3 p-3 border-2 border-gray-200 dark:border-gray-700 rounded-xl cursor-pointer hover:border-blue-500 transition-colors">
                <input
                  type="radio"
                  name="role"
                  value="realtor"
                  checked={formData.role === 'realtor'}
                  onChange={(e) => setFormData({...formData, role: e.target.value as 'realtor'})}
                  className="w-4 h-4 text-blue-500"
                />
                <span className="dark:text-white">Риелтор</span>
              </label>
            </div>
          </div>
          
          <button
            type="submit"
            className="w-full py-3 bg-blue-500 text-white rounded-xl font-semibold hover:bg-blue-600 transition-colors"
          >
            Зарегистрироваться
          </button>
        </form>
        
        <div className="mt-6 text-center">
          <button
            onClick={() => navigate('/login')}
            className="text-blue-500 hover:underline"
          >
            Уже есть аккаунт? Войти
          </button>
        </div>
      </div>
    </div>
  );
};

// Profile Page
const ProfilePage: React.FC = () => {
  const { user, setUser } = useAppContext();
  const navigate = useNavigate();
  
  const handleLogout = () => {
    setUser(null);
    navigate('/');
  };
  
  const menuItems = [
    { icon: User, label: 'Мои данные', onClick: () => {} },
    { icon: Heart, label: 'Избранное', onClick: () => navigate('/favorites') },
    { icon: MessageCircle, label: 'Мои объявления', onClick: () => {} },
    { icon: Settings, label: 'Настройки', onClick: () => {} },
  ];
  
  return (
    <div className="pb-20">
      <div className="p-4 bg-gradient-to-br from-blue-500 to-cyan-500 text-white">
        <div className="flex items-center gap-4">
          <div className="w-20 h-20 bg-white/20 rounded-full flex items-center justify-center text-3xl font-bold">
            {user?.name?.[0] || 'U'}
          </div>
          <div>
            <h1 className="text-2xl font-bold">{user?.name || 'Гость'}</h1>
            <p className="opacity-90">{user?.phone}</p>
          </div>
        </div>
      </div>
      
      <div className="p-4 space-y-2">
        {menuItems.map((item, index) => (
          <button
            key={index}
            onClick={item.onClick}
            className="w-full flex items-center gap-3 p-4 bg-white dark:bg-gray-800 rounded-xl hover:bg-gray-50 dark:hover:bg-gray-700 transition-colors"
          >
            <item.icon size={24} className="text-blue-500" />
            <span className="flex-1 text-left dark:text-white">{item.label}</span>
            <ChevronLeft size={20} className="rotate-180 text-gray-400" />
          </button>
        ))}
        
        <button
          onClick={handleLogout}
          className="w-full flex items-center gap-3 p-4 bg-white dark:bg-gray-800 rounded-xl hover:bg-red-50 dark:hover:bg-red-900/20 transition-colors text-red-500"
        >
          <LogOut size={24} />
          <span className="flex-1 text-left">Выйти</span>
        </button>
      </div>
    </div>
  );
};

// Add Property Page
const AddPropertyPage: React.FC = () => {
  const navigate = useNavigate();
  
  return (
    <div className="pb-20">
      <div className="p-4 border-b border-gray-200 dark:border-gray-800 bg-white dark:bg-gray-900 sticky top-14">
        <h1 className="text-2xl font-bold dark:text-white">Добавить объявление</h1>
      </div>
      
      <div className="p-4 space-y-4">
        {/* Photo Upload */}
        <div>
          <label className="block text-sm font-medium mb-2 dark:text-white">Фото / Видео</label>
          <div className="grid grid-cols-3 gap-2">
            {[1, 2, 3, 4, 5].map((i) => (
              <div key={i} className="aspect-square bg-gray-100 dark:bg-gray-800 rounded-xl flex items-center justify-center">
                <Camera size={32} className="text-gray-400" />
              </div>
            ))}
            <div className="aspect-square bg-blue-50 dark:bg-blue-900/20 rounded-xl flex items-center justify-center border-2 border-dashed border-blue-300 dark:border-blue-700">
              <Plus size={32} className="text-blue-500" />
            </div>
          </div>
        </div>
        
        {/* Property Type */}
        <div>
          <label className="block text-sm font-medium mb-2 dark:text-white">Тип квартиры</label>
          <select className="w-full px-4 py-3 bg-gray-100 dark:bg-gray-800 rounded-xl outline-none dark:text-white">
            <option>1-комнатная</option>
            <option>2-комнатная</option>
            <option>3-комнатная</option>
            <option>4+ комнатная</option>
          </select>
        </div>
        
        {/* Address */}
        <div>
          <label className="block text-sm font-medium mb-2 dark:text-white">Адрес</label>
          <input
            type="text"
            placeholder="Введите адрес"
            className="w-full px-4 py-3 bg-gray-100 dark:bg-gray-800 rounded-xl outline-none dark:text-white"
          />
        </div>
        
        {/* Description */}
        <div>
          <label className="block text-sm font-medium mb-2 dark:text-white">Описание</label>
          <textarea
            placeholder="Подробное описание..."
            rows={4}
            className="w-full px-4 py-3 bg-gray-100 dark:bg-gray-800 rounded-xl outline-none dark:text-white resize-none"
          />
        </div>
        
        {/* Price */}
        <div>
          <label className="block text-sm font-medium mb-2 dark:text-white">Цена</label>
          <div className="flex gap-2">
            <input
              type="number"
              placeholder="0"
              className="flex-1 px-4 py-3 bg-gray-100 dark:bg-gray-800 rounded-xl outline-none dark:text-white"
            />
            <span className="px-4 py-3 bg-gray-100 dark:bg-gray-800 rounded-xl dark:text-white">₸ / мес</span>
          </div>
        </div>
        
        <button
          onClick={() => navigate('/')}
          className="w-full py-3 bg-blue-500 text-white rounded-xl font-semibold hover:bg-blue-600 transition-colors"
        >
          Опубликовать
        </button>
      </div>
    </div>
  );
};

// Admin Page
const AdminPage: React.FC = () => {
  const stats = [
    { label: 'Объявления', value: 128, sublabel: 'Активные', color: 'bg-blue-500' },
    { label: 'Пользователи', value: 342, sublabel: 'Всего', color: 'bg-green-500' },
    { label: 'Отзывы', value: 256, sublabel: 'Всего', color: 'bg-purple-500' },
    { label: 'Жалобы', value: 8, sublabel: 'Новые', color: 'bg-red-500' },
  ];
  
  return (
    <div className="pb-20">
      <div className="p-4 border-b border-gray-200 dark:border-gray-800 bg-white dark:bg-gray-900 sticky top-14">
        <h1 className="text-2xl font-bold dark:text-white">Админка</h1>
      </div>
      
      <div className="p-4">
        <div className="grid grid-cols-2 gap-4 mb-6">
          {stats.map((stat, index) => (
            <div key={index} className="bg-white dark:bg-gray-800 p-4 rounded-2xl shadow">
              <div className={`w-10 h-10 ${stat.color} rounded-xl flex items-center justify-center mb-3`}>
                <span className="text-white font-bold text-lg">{stat.value}</span>
              </div>
              <p className="text-sm text-gray-500">{stat.label}</p>
              <p className="text-xs text-gray-400">{stat.sublabel}</p>
            </div>
          ))}
        </div>
        
        <h2 className="font-semibold text-lg mb-4 dark:text-white">Последние объявления</h2>
        <div className="space-y-3">
          {mockProperties.map((property) => (
            <div key={property.id} className="bg-white dark:bg-gray-800 p-3 rounded-xl flex gap-3">
              <img 
                src={property.images[0]} 
                alt={property.title}
                className="w-20 h-20 object-cover rounded-lg"
              />
              <div className="flex-1">
                <p className="font-medium dark:text-white line-clamp-1">{property.title}</p>
                <p className="text-blue-500 font-semibold">{property.price.toLocaleString()} ₸/мес</p>
                <p className="text-xs text-gray-400">1 мин назад</p>
              </div>
            </div>
          ))}
        </div>
        
        <button className="w-full mt-6 py-3 bg-red-500 text-white rounded-xl font-semibold hover:bg-red-600 transition-colors">
          Выйти
        </button>
      </div>
    </div>
  );
};

// Favorites Page
const FavoritesPage: React.FC = () => {
  const { properties } = useAppContext();
  
  return (
    <div className="pb-20">
      <div className="p-4 border-b border-gray-200 dark:border-gray-800 bg-white dark:bg-gray-900 sticky top-14">
        <h1 className="text-2xl font-bold dark:text-white">Избранное</h1>
      </div>
      
      <div className="p-4 grid grid-cols-1 md:grid-cols-2 gap-4">
        {properties.map((property) => (
          <PropertyCard key={property.id} property={property} />
        ))}
      </div>
    </div>
  );
};

// Search Page
const SearchPage: React.FC = () => {
  return (
    <div className="pb-20">
      <div className="p-4 bg-white dark:bg-gray-900 sticky top-14 border-b border-gray-200 dark:border-gray-800">
        <div className="relative mb-4">
          <Search className="absolute left-4 top-1/2 transform -translate-y-1/2 text-gray-400" size={20} />
          <input
            type="text"
            placeholder="Поиск по адресу, ЖК..."
            className="w-full pl-12 pr-4 py-3 bg-gray-100 dark:bg-gray-800 rounded-2xl outline-none dark:text-white"
          />
        </div>
        
        <div className="space-y-4">
          <div>
            <label className="block text-sm font-medium mb-2 dark:text-white">Цена</label>
            <div className="flex gap-2">
              <input type="number" placeholder="От" className="flex-1 px-4 py-2 bg-gray-100 dark:bg-gray-800 rounded-xl dark:text-white" />
              <input type="number" placeholder="До" className="flex-1 px-4 py-2 bg-gray-100 dark:bg-gray-800 rounded-xl dark:text-white" />
            </div>
          </div>
          
          <div>
            <label className="block text-sm font-medium mb-2 dark:text-white">Комнат</label>
            <div className="flex gap-2">
              {['Студия', '1', '2', '3', '4+'].map((room) => (
                <button key={room} className="flex-1 py-2 bg-gray-100 dark:bg-gray-800 rounded-xl dark:text-white hover:bg-gray-200 dark:hover:bg-gray-700">
                  {room}
                </button>
              ))}
            </div>
          </div>
        </div>
      </div>
    </div>
  );
};

// ==================== MAIN APP ====================

const AppContent: React.FC = () => {
  const location = useLocation();
  const hideNavPaths = ['/login', '/register'];
  const showNav = !hideNavPaths.includes(location.pathname);
  
  return (
    <div className="min-h-screen bg-gray-50 dark:bg-gray-950 transition-colors">
      <Header 
        showBack={location.pathname !== '/' && !hideNavPaths.includes(location.pathname)}
      />
      
      <main className={showNav ? 'pb-16' : ''}>
        <Routes>
          <Route path="/" element={<HomePage />} />
          <Route path="/property/:propertyId" element={<PropertyDetailPage propertyId="" />} />
          <Route path="/messages" element={<MessagesPage />} />
          <Route path="/chat/:chatId" element={<ChatPage chatId="" />} />
          <Route path="/login" element={<LoginPage />} />
          <Route path="/register" element={<RegisterPage />} />
          <Route path="/profile" element={<ProfilePage />} />
          <Route path="/add-property" element={<AddPropertyPage />} />
          <Route path="/admin" element={<AdminPage />} />
          <Route path="/favorites" element={<FavoritesPage />} />
          <Route path="/search" element={<SearchPage />} />
        </Routes>
      </main>
      
      {showNav && <BottomNav />}
    </div>
  );
};

const App: React.FC = () => {
  const [user, setUser] = useState<User | null>(null);
  const [isDarkMode, setIsDarkMode] = useState(false);
  
  useEffect(() => {
    if (isDarkMode) {
      document.documentElement.classList.add('dark');
    } else {
      document.documentElement.classList.remove('dark');
    }
  }, [isDarkMode]);
  
  const toggleTheme = () => setIsDarkMode(!isDarkMode);
  
  const contextValue: AppContextType = {
    user,
    setUser,
    isDarkMode,
    toggleTheme,
    properties: mockProperties,
    chats: mockChats,
    currentUser: {
      id: 'current',
      name: 'Пользователь',
      phone: '+7 777 777 7777',
      role: 'client'
    }
  };
  
  return (
    <AppContext.Provider value={contextValue}>
      <Router>
        <AppContent />
      </Router>
    </AppContext.Provider>
  );
};

export default App;
