# -ล้านถ้วยโปรด
import React, { useState } from 'react';

const CoffeeMenuApp = () => {
  const [activeCategory, setActiveCategory] = useState('recommend');
  const [selectedItem, setSelectedItem] = useState(null);
  const [selectedSubItem, setSelectedSubItem] = useState(null);

  // Colors Palette Reference:
  // Brown: #78350f (amber-900)
  // Dark: #111827 (gray-900)
  // Gray: #374151 (gray-700)
  // Pine Green: #064e3b (emerald-900)
  // Blood Red: #7f1d1d (red-900)

  const menuData = {
    recommend: [
     { name: "ลาเต้มะพร้าวปั่น Coconut Latte Frappe", price: "90 บาท" },
      { name: "อเมริกาโนมะพร้าว Coconut Americano", price: "80 บาท" },
      { name: "ชามะขาม Tamarind Tea", price: "60 บาท" },
      { name: "อเมริกาโนส้ม Orange Americano", price: "80 บาท" },
      { name: "เปปเปอร์มิ้นลาเต้ Peppermint Latte", price: "70 บาท" },
      { name: "มอคค่าคาราเมล Mocha Caramel", price: "75 บาท" },
      { name: "พรีเมียมอเมริกาโน Premium Americano", price: "95 บาท" },
      { name: "อเมริกาโนน้ำผึ้งมะนาว Honey Lime Americano", price: "80 บาท" },
      { name: "อเมริกาโนน้ำอ้อย Sugarcane Americano", price: "80 บาท" },
      { name: "อเมริกาโนน้ำผึ้ง Honey Americano", price: "65 บาท" },
      { name: "สละลาเต้ Red Sala Syrup Latte", price: "70 บาท" },
      { name: "คาราเมล มัคคิอาโต้ Caramel Macchiato", price: "65 บาท" },
    ],
    special: [
      { 
        id: 'ethiopia', name: "1. Ethiopia", 
        subItems: [
          { name: "Americano", price: "ร้อน 80 บาท / เย็น 90 บาท" },
          { name: "Espresso", price: "ร้อน 80 บาท / เย็น 100 บาท" },
          { name: "Cappuccino", price: "ร้อน 90 บาท / เย็น 100 บาท" },
          { name: "Latte", price: "ร้อน 90 บาท / เย็น 100 บาท" },
          { name: "Mocha", price: "ร้อน 90 บาท / เย็น 100 บาท" },
          { name: "Long Black", price: "ร้อน 80 บาท / เย็น 90 บาท" },
        ]
      },
      { 
        id: 'guatemala', name: "2. Guatemala", 
        subItems: [
          { name: "Americano", price: "ร้อน 80 บาท / เย็น 90 บาท" },
          { name: "Espresso", price: "ร้อน 80 บาท / เย็น 100 บาท" },
          { name: "Cappuccino", price: "ร้อน 90 บาท / เย็น 100 บาท" },
          { name: "Latte", price: "ร้อน 90 บาท / เย็น 100 บาท" },
          { name: "Mocha", price: "ร้อน 90 บาท / เย็น 100 บาท" },
          { name: "Long Black", price: "ร้อน 80 บาท / เย็น 90 บาท" },
        ]
      },
      { 
        id: 'brazil', name: "3. Brazil", 
        subItems: [
          { name: "Americano", price: "ร้อน 60 บาท / เย็น 70 บาท" },
          { name: "Espresso", price: "ร้อน 60 บาท / เย็น 80 บาท" },
          { name: "Cappuccino", price: "ร้อน 70 บาท / เย็น 80 บาท" },
          { name: "Latte", price: "ร้อน 70 บาท / เย็น 80 บาท" },
          { name: "Mocha", price: "ร้อน 70 บาท / เย็น 80 บาท" },
          { name: "Long Black", price: "ร้อน 60 บาท / เย็น 70 บาท" },
        ]
      },
      { 
        id: 'columbia', name: "4. Columbia", 
        subItems: [
          { name: "Americano", price: "ร้อน 80 บาท / เย็น 90 บาท" },
          { name: "Espresso", price: "ร้อน 80 บาท / เย็น 100 บาท" },
          { name: "Cappuccino", price: "ร้อน 90 บาท / เย็น 100 บาท" },
          { name: "Latte", price: "ร้อน 90 บาท / เย็น 100 บาท" },
          { name: "Mocha", price: "ร้อน 90 บาท / เย็น 100 บาท" },
          { name: "Long Black", price: "ร้อน 80 บาท / เย็น 90 บาท" },
        ]
      },
      { 
        id: 'thailand', name: "5. Thailand", 
        subItems: [
          { name: "Americano", price: "ร้อน 60 บาท / เย็น 70 บาท" },
          { name: "Espresso", price: "ร้อน 60 บาท / เย็น 80 บาท" },
          { name: "Cappuccino", price: "ร้อน 70 บาท / เย็น 80 บาท" },
          { name: "Latte", price: "ร้อน 70 บาท / เย็น 80 บาท" },
          { name: "Mocha", price: "ร้อน 70 บาท / เย็น 80 บาท" },
          { name: "Long Black", price: "ร้อน 60 บาท / เย็น 70 บาท" },
        ]
      },
    ],
    coffee: [
      { name: "1. Americano", options: "ร้อน 50 / เย็น 50" },
      { name: "2. Espresso", options: "ร้อน 50 / เย็น 50" },
      { name: "3. Cappuccino", options: "ร้อน 60 / เย็น 60" },
      { name: "4. Latte", options: "ร้อน 60 / เย็น 60" },
      { name: "5. Mocha", options: "ร้อน 60 / เย็น 65" },
      { name: "6. Long Black", options: "ร้อน 50 / เย็น 50" },
    ],
    tea: [
      { name: "1. ชาไทย Thai Tea", options: "เย็น 40 / ปั่น 50" },
      { name: "2. ชามะนาว Lime Tea", options: "ร้อน 40 / เย็น 50" },
      { name: "3. ชาเขียว Green Tea", options: "เย็น 45 / ปั่น 55" },
      { name: "4. ชาพีช Peach Tea", options: "ร้อน 40 / เย็น 50" },
      { name: "5. ชาซีลอน Ceylon Tea", options: "ร้อน 40 / เย็น 50 / ปั่น 60" },
      { name: "6. ชามะขาม Tamarind Tea", options: "เย็น 60" },
      { name: "7. มัจฉะน้ำผึ้งมะนาว Matcha Honey Lime", options: "เย็น 90" },
      { name: "8. มัจฉะ Pure Matcha", options: "ร้อน 50 / เย็น 60" },
      { name: "9. มัจฉะลาเต้ Matcha Latte", options: "ร้อน 50 / เย็น 60" },
    ],
    cocoa: [
      { name: "1. Chocolate", options: "ร้อน 40 / เย็น 50 / ปั่น 60" },
      { name: "2. Ovaltine", options: "ร้อน 40 / เย็น 50 / ปั่น 60" },
      { name: "3. Cocoa Mint", options: "เย็น 65 / ปั่น 75" },
    ],
    others: [
      { name: "1. น้ำผึ้งมะนาว Honey Lime Soda", options: "เย็น 65" },
      { name: "2. แดงมะนาวโซดา Red Sala Syrup Lime Soda", options: "เย็น 45" },
      { name: "3. นมสดคาราเมล Caramel Milk", options: "เย็น 50 / ปั่น 60" },
      { name: "4. บ๊วยแดงโซดา Red Sala Syrup Plum Soda", options: "เย็น 70" },
      { name: "5. ชาน้ำผึ้งมะนาวโซดา Honey Lime Soda Tea", options: "เย็น 70" },
    ]
  };

  const handleCategoryClick = (cat) => {
    setActiveCategory(cat);
    setSelectedItem(null);
    setSelectedSubItem(null);
  };

  return (
    <div className="min-h-screen bg-black text-white font-sans p-4 pb-20">
      {/* Header */}
      <header className="text-center py-8 border-b border-gray-800 mb-8">
        <h1 className="text-3xl md:text-5xl font-bold text-amber-600 mb-2">
          เมนูกาแฟล้านถ้วยโปรด
        </h1>
        <p className="text-gray-400 text-lg">Coffee Menu</p>
      </header>

      {/* Category Navigation */}
      <nav className="flex flex-wrap justify-center gap-2 mb-10">
        {[
          { id: 'recommend', label: 'Recommend' },
          { id: 'special', label: 'Special Coffee' },
          { id: 'coffee', label: 'Coffee' },
          { id: 'tea', label: 'Tea' },
          { id: 'cocoa', label: 'Cocoa' },
          { id: 'others', label: 'Others' }
        ].map((cat) => (
          <button
            key={cat.id}
            onClick={() => handleCategoryClick(cat.id)}
            className={`px-4 py-2 rounded-full transition-all duration-300 border ${
              activeCategory === cat.id 
              ? 'bg-emerald-900 border-emerald-500 text-white' 
              : 'bg-gray-900 border-gray-700 text-gray-400 hover:border-amber-700'
            }`}
          >
            {cat.label}
          </button>
        ))}
      </nav>

      {/* Menu List Content */}
      <main className="max-w-4xl mx-auto">
        <div className="grid grid-cols-1 gap-4">
          
          {/* Recommend Category */}
          {activeCategory === 'recommend' && menuData.recommend.map((item, idx) => (
            <div key={idx} className="bg-gray-900 p-4 rounded-xl shadow-sm border-l-4 border-amber-900 flex justify-between items-center hover:bg-gray-800 transition-colors">
              <span className="text-lg">{item.name}</span>
              <span className="text-amber-500 font-bold ml-4 whitespace-nowrap">{item.price}</span>
            </div>
          ))}

          {/* Special Coffee Category (Nested Logic) */}
          {activeCategory === 'special' && (
            <div className="space-y-4">
              {menuData.special.map((origin) => (
                <div key={origin.id} className="bg-gray-900 rounded-xl overflow-hidden border border-gray-800">
                  <button 
                    onClick={() => setSelectedItem(selectedItem === origin.id ? null : origin.id)}
                    className="w-full text-left p-5 text-xl font-semibold bg-red-900/30 flex justify-between items-center"
                  >
                    {origin.name}
                    <span>{selectedItem === origin.id ? '−' : '+'}</span>
                  </button>
                  
                  {selectedItem === origin.id && (
                    <div className="p-4 grid grid-cols-1 sm:grid-cols-2 gap-3 bg-black/40">
                      {origin.subItems.map((sub, sIdx) => (
                        <div key={sIdx} className="border border-gray-700 rounded-lg overflow-hidden">
                          <button 
                            onClick={() => setSelectedSubItem(selectedSubItem === sub.name ? null : sub.name)}
                            className="w-full p-3 text-left bg-gray-800 hover:bg-emerald-900/40 transition-colors"
                          >
                            {sub.name}
                          </button>
                          {selectedSubItem === sub.name && (
                            <div className="p-3 bg-amber-900/20 text-center text-amber-400 font-bold border-t border-gray-700 animate-pulse">
                              {sub.price}
                            </div>
                          )}
                        </div>
                      ))}
                    </div>
                  )}
                </div>
              ))}
            </div>
          )}

          {/* Standard Categories (Coffee, Tea, Cocoa, Others) */}
          {['coffee', 'tea', 'cocoa', 'others'].includes(activeCategory) && menuData[activeCategory].map((item, idx) => (
            <div key={idx} className="bg-gray-900 rounded-xl border border-gray-800 overflow-hidden">
              <button 
                onClick={() => setSelectedItem(selectedItem === idx ? null : idx)}
                className="w-full text-left p-4 flex justify-between items-center hover:bg-gray-800 transition-colors"
              >
                <span className="text-lg">{item.name}</span>
                <span className="text-amber-700">🔍</span>
              </button>
              {selectedItem === idx && (
                <div className="p-4 bg-emerald-900/10 text-emerald-400 text-center font-bold border-t border-gray-800 italic">
                   {item.options}
                </div>
              )}
            </div>
          ))}
        </div>
      </main>

      {/* Contact Footer */}
<footer className="fixed bottom-0 left-0 right-0 bg-red-900 text-white p-4 shadow-2xl z-50">
  <div className="max-w-4xl mx-auto flex flex-col sm:flex-row justify-between items-center gap-2">
    <div className="flex items-center gap-2">
      <span className="font-bold">Contact !</span>
      {/* ใช้ href="tel:..." เพื่อให้มือถือเรียกแอปโทรศัพท์ขึ้นมาทันที */}
      <a 
        href="tel:0898909057" 
        className="bg-white text-red-900 px-4 py-1 rounded-full text-sm font-black hover:bg-amber-100 transition-colors"
      >
        📞 โทรสั่ง: 089-890-9057
      </a>
    </div>
    <div className="text-sm font-medium animate-pulse text-amber-200">
      อย่าลืมแจ้งชื่อ Don’t Forget Your NAME
    </div>
  </div>
</footer>

      
      {/* Decorative Elements */}
      <div className="fixed top-0 left-0 w-full h-1 bg-gradient-to-r from-amber-900 via-emerald-900 to-red-900"></div>
    </div>
  );
};

export default CoffeeMenuApp;
