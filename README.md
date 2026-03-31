# -{/* แก้ไขส่วน Footer ในโค้ดเดิมของคุณ */}
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
