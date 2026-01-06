# afaqfor 
<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>آفاق للخدمات المالية والعقارية</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <script src="https://unpkg.com/react@18/umd/react.production.min.js"></script>
    <script src="https://unpkg.com/react-dom@18/umd/react-dom.production.min.js"></script>
    <script src="https://unpkg.com/@babel/standalone/babel.min.js"></script>
    <script src="https://unpkg.com/framer-motion@10.16.4/dist/framer-motion.js"></script>
    <script src="https://unpkg.com/lucide@latest"></script>
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Tajawal:wght@400;500;700;800&display=swap');
        body { font-family: 'Tajawal', sans-serif; margin:0; }
    </style>
</head>
<body>
<div id="root"></div>

<script type="text/babel">
const { useEffect } = React;
const { motion } = window.Motion;

// أيقونات Lucide جاهزة
const Icon = ({ name, size=24, className="" }) => {
    useEffect(() => { window.lucide.createIcons(); }, []);
    return <i data-lucide={name} className={className} style={{ width:size, height:size }}></i>;
};

const AfaqDesign = () => {
    const phone1 = "+966509709174";
    const phone2 = "+966547776904";

    const services = [
        { title:"استخراج قروض", description:"نساعدك في الحصول على التمويل المناسب بسرعة وبطرق نظامية.", icon:"wallet" },
        { title:"تسديد قروض", description:"حلول متكاملة لتسديد المديونيات وإعادة الجدولة.", icon:"arrow-right-left" }
    ];

    return (
        <div className="min-h-screen bg-slate-50 text-slate-900">
            {/* Header */}
            <header className="relative overflow-hidden bg-gradient-to-br from-blue-900 via-blue-800 to-blue-700 text-white pb-20 pt-10 px-6">
                <div className="absolute top-0 left-0 w-full h-full opacity-10 pointer-events-none">
                    <div className="absolute top-10 left-10 w-64 h-64 rounded-full bg-white blur-3xl"></div>
                    <div className="absolute bottom-10 right-10 w-96 h-96 rounded-full bg-amber-400 blur-3xl"></div>
                </div>

                <nav className="max-w-6xl mx-auto flex justify-between items-center mb-16 relative z-10">
                    <div className="flex items-center gap-3">
                        <div className="bg-white p-2 rounded-xl shadow-lg">
                            <Icon name="building-2" className="text-blue-900" size={32} />
                        </div>
                        <h1 className="text-3xl font-bold tracking-tight">
                            آفاق <span className="text-amber-400">للعقارات</span>
                        </h1>
                    </div>
                    <div className="hidden md:block text-sm font-medium border-r-2 border-amber-400 pr-4">
                        للخدمات المالية والعقارية
                    </div>
                </nav>

                <div className="max-w-6xl mx-auto grid md:grid-cols-2 gap-12 items-center relative z-10">
                    <motion.div initial={{ opacity:0, x:50 }} animate={{ opacity:1, x:0 }} transition={{ duration:0.6 }}>
                        <h2 className="text-4xl md:text-6xl font-extrabold mb-6 leading-tight">
                            حلول مالية <br />
                            <span className="text-amber-400">تفتح لك الآفاق</span>
                        </h2>
                        <p className="text-blue-100 text-lg mb-8 max-w-md leading-relaxed">
                            نقدم خدمات استخراج وتسديد القروض بأفضل الطرق الشرعية والنظامية لضمان راحتك المالية ومستقبلك العقاري.
                        </p>

                        <div className="flex flex-wrap gap-4">
                            <a href={`https://wa.me/${phone1.replace('+','')}`} className="flex items-center gap-2 bg-green-600 hover:bg-green-700 text-white px-6 py-3 rounded-full font-bold shadow-lg hover:scale-105 transition-all"><Icon name="message-circle" size={20}/> تواصل عبر الواتساب
                            </a>
                            <div className="flex items-center gap-2 bg-white/10 backdrop-blur-md border border-white/20 px-6 py-3 rounded-full font-medium">
                                <Icon name="check-circle-2" className="text-amber-400" size={20}/> سرعة في التنفيذ
                            </div>
                        </div>
                    </motion.div>

                    <motion.div initial={{ opacity:0, scale:0.8 }} animate={{ opacity:1, scale:1 }} transition={{ duration:0.6, delay:0.2 }} className="relative">
                        <div className="bg-white/5 backdrop-blur-sm border border-white/10 p-8 rounded-3xl shadow-2xl overflow-hidden">
                            <div className="grid grid-cols-2 gap-4">
                                <div className="bg-white/10 p-6 rounded-2xl flex flex-col items-center">
                                    <Icon name="calculator" className="text-amber-400 mb-2" size={48}/>
                                    <span className="text-sm">حسابات دقيقة</span>
                                </div>
                                <div className="bg-white/10 p-6 rounded-2xl flex flex-col items-center">
                                    <Icon name="building-2" className="text-amber-400 mb-2" size={48}/>
                                    <span className="text-sm">عقارات متميزة</span>
                                </div>
                            </div>
                            <div className="mt-4 bg-amber-400 text-blue-900 p-6 rounded-2xl font-bold text-center text-xl">
                                نظامي 100%
                            </div>
                        </div>
                    </motion.div>
                </div>
            </header>

            {/* Services */}
            <section className="max-w-6xl mx-auto -mt-16 px-6 relative z-20">
                <div className="grid md:grid-cols-2 gap-8">
                    {services.map((s,i)=>(
                        <motion.div key={i} whileHover={{ y:-10 }} className="bg-white p-8 rounded-3xl shadow-xl border border-slate-100 flex items-start gap-6">
                            <div className="bg-amber-50 p-4 rounded-2xl">
                                <Icon name={s.icon} className="text-amber-500" size={32}/>
                            </div>
                            <div>
                                <h3 className="text-2xl font-bold text-blue-900 mb-2">{s.title}</h3>
                                <p className="text-slate-600 leading-relaxed">{s.description}</p>
                            </div>
                        </motion.div>
                    ))}
                </div>
            </section>

            {/* Contact */}
            <section className="max-w-4xl mx-auto py-20 px-6 text-center">
                <h3 className="text-3xl font-bold text-blue-900 mb-4">هل لديك أي استفسار؟</h3>
                <p className="text-slate-500 mb-12">فريقنا جاهز للرد على جميع تساؤلاتكم على مدار الساعة</p>
                <div className="grid sm:grid-cols-2 gap-6">
                    {[{num:phone1,label:"الرقم الأول"},{num:phone2,label:"الرقم الثاني"}].map((p,i)=>(
                        <div key={i} className="bg-white p-6 rounded-2xl shadow-md border border-slate-100 flex flex-col items-center">
                            <div className="w-12 h-12 bg-blue-100 rounded-full flex items-center justify-center text-blue-600 mb-4">
                                <Icon name="phone" size={24}/>
                            </div>
                            <span className="text-slate-400 text-sm mb-1">{p.label}</span>
                            <a href={`tel:${p.num}`} className="text-xl font-bold text-blue-900 tracking-wider" dir="ltr">{p.num}</a>
                        </div>
                    ))}
                </div>
            </section>

            {/* Footer */}<footer className="bg-slate-900 text-slate-400 py-10 px-6 text-center border-t border-slate-800">
                <div className="max-w-6xl mx-auto flex flex-col md:flex-row justify-between items-center gap-6">
                    <div className="flex items-center gap-2">
                        <Icon name="building-2" className="text-amber-500" size={24}/>
                        <span className="text-white font-bold">آفاق للخدمات المالية</span>
                    </div>
                    <p className="text-sm">© 2024 جميع الحقوق محفوظة لشركة آفاق</p>
                    <div className="flex gap-4">
                        <div className="w-8 h-8 rounded-full bg-slate-800 flex items-center justify-center hover:bg-blue-600 transition-colors cursor-pointer">
                            <Icon name="message-circle" size={16} className="text-white"/>
                        </div>
                    </div>
                </div>
            </footer>
        </div>
    );
};

ReactDOM.createRoot(document.getElementById('root')).render(<AfaqDesign />);
</script>
</body>
</html>
