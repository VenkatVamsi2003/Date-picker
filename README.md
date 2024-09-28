# Date-picker
import React, { useState } from "react";
import DatePicker from 'react-datepicker';
import './App.css';
import 'react-datepicker/dist/react-datepicker.css';
import 'bootstrap/dist/css/bootstrap.min.css';
import { FaCalendarAlt } from 'react-icons/fa';

// Custom input component for the DatePicker
function CustomInput({ value, onClick }) {
  return (
    <div className="input-group">
      <input type="text" className="form-control" value={value} onClick={onClick} readOnly />
      <div className="input-group-append">
        <span className="input-group-text">
          <FaCalendarAlt />
        </span>
      </div>
    </div>
  );
}

function App() {
  const [selectedDate, setDate] = useState(null);

  return (
    <div className="App">
      <DatePicker 
        selected={selectedDate} 
        onChange={(date) => setDate(date)}  // Fixed typo: 'dateate' is now 'date'
        customInput={<CustomInput />} 
      />
    </div>
  );
}

export default App;
