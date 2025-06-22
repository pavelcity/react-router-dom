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
