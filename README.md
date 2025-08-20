# <html>
    import React, { useCallback, useEffect, useMemo, useRef, useState } from "react";
position={fen}
onPieceDrop={onDrop}
boardOrientation={orientation}
customBoardStyle={customBoardStyle}
customSquareStyles={customSquareStyles}
animationDuration={200}
areArrowsAllowed
arePiecesDraggable
boardWidth={Math.min(560, typeof window !== "undefined" ? window.innerWidth - 48 : 560)}
/>
</div>
</CardContent>
</Card>


<div className="lg:col-span-2 space-y-6">
<Card>
<CardHeader>
<CardTitle className="text-lg">الحالة</CardTitle>
</CardHeader>
<CardContent>
<div className="flex items-center justify-between">
<div className="text-slate-700 font-medium">
{status}
</div>
<div className="flex items-center gap-2">
<Button className="rounded-2xl" onClick={() => setVsComputer((v) => !v)}>
{vsComputer ? (
<>
<Swords className="mr-2 h-4 w-4" /> لاعبان
</>
) : (
<>
<Bot className="mr-2 h-4 w-4" /> ضد الحاسوب
</>
)}
</Button>
</div>
</div>
<div className="mt-2 text-sm text-slate-500">الدور الحالي: {turnArabic}</div>
</CardContent>
</Card>


<Card>
<CardHeader>
<CardTitle className="text-lg">سجل النقلات</CardTitle>
</CardHeader>
<CardContent>
{history.length === 0 ? (
<div className="text-slate-400">لا توجد نقلات بعد.</div>
) : (
<ol className="grid grid-cols-2 gap-x-6 gap-y-1 text-sm">
{history.map((h, idx) => (
<li key={idx} className="flex items-center justify-between py-1 border-b last:border-b-0">
<span className="text-slate-600">{Math.floor(idx / 2) + 1}{idx % 2 === 0 ? "." : "..."}</span>
<span className="font-mono">{h.san}</span>
</li>
))}
</ol>
)}
</CardContent>
</Card>


<Card>
<CardHeader>
<CardTitle className="text-lg">نصائح سريعة</CardTitle>
</CardHeader>
<CardContent className="text-sm text-slate-600 space-y-2">
<p>اسحب القطع لإجراء نقلة. سيقوم المحرك بالتحقق من صحة النقلات تلقائيًا.</p>
<p>يمكنك الترويج للبيادق إلى وزير تلقائيًا عند الوصول للصف الأخير.</p>
<p>استخدم الأزرار للتراجع خطوة، إعادة البداية، أو قلب اللوح.</p>
<p>فعّل خيار <strong>ضد الحاسوب</strong> للعب أمام خصم بسيط.</p>
</CardContent>
</Card>
</div>
</div>
</div>
</div>
);
}
</html>
