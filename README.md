# react-router-dom

```
npm install react-router-dom
```


```
// App.jsx
import { Routes, Route } from 'react-router-dom';
import HomePage from './pages/HomePage';
import ServicesPage from './pages/ServicesPage';

function App() {
  return (
    <Routes>
      <Route path="/" element={<HomePage />} />
      <Route path="/services" element={<ServicesPage />} />
      <Route path="/appointment" element={<AppointmentPage />} />
      <Route path="*" element={<NotFoundPage />} />
    </Routes>
  );
}
```


```
// App.jsx
import { Routes, Route } from 'react-router-dom';
import Layout from './components/Layout';
import HomePage from './pages/HomePage';
import ServicesPage from './pages/ServicesPage';
import NotFoundPage from './pages/NotFoundPage';

function App() {
  return (
    <Routes>
      <Route path="/" element={<Layout />}>
        <Route index element={<HomePage />} />
        <Route path="services" element={<ServicesPage />} />
        <Route path="services/:serviceId" element={<ServiceDetailPage />} />
        <Route path="*" element={<NotFoundPage />} />
      </Route>
    </Routes>
  );
}
```


### Базовый компонент Layout (`Layout.jsx`)
```
import { Outlet } from 'react-router-dom';
import Header from './Header';
import Footer from './Footer';

const Layout = () => {
  return (
    <div className="flex flex-col min-h-screen">
      <Header />
      
      <main className="flex-grow">
        <Outlet /> {/* Здесь будут отображаться дочерние страницы */}
      </main>
      
      <Footer />
    </div>
  );
};

export default Layout;
```


### Навигация
```
<NavLink 
  to="/services"
   className={({isActive}) => 
        isActive 
          ? "text-blue-600 font-medium border-b-2 border-blue-600 pb-1" 
          : "text-gray-600 hover:text-blue-500 transition-colors"
      }
    >
    Услуги
</NavLink>
```
