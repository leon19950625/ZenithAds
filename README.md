<!DOCTYPE html>
<html lang="zh-CN">
<head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Zenith | 数字广告平台</title>
    <style>
        /* ===== 全局重置 ===== */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, "Helvetica Neue", Arial, sans-serif;
            background: #0b1120;
            color: #e8edf5;
            line-height: 1.7;
            -webkit-font-smoothing: antialiased;
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 24px;
        }

        /* ===== 导航栏 ===== */
        .navbar {
            padding: 18px 0;
            display: flex;
            justify-content: space-between;
            align-items: center;
            border-bottom: 1px solid rgba(255, 255, 255, 0.06);
            position: sticky;
            top: 0;
            background: rgba(11, 17, 32, 0.92);
            backdrop-filter: blur(12px);
            z-index: 100;
        }

        .logo {
            font-size: 24px;
            font-weight: 700;
            letter-spacing: -0.5px;
            cursor: default;
        }

        .logo span {
            color: #4f8cf7;
        }

        .nav-links {
            display: flex;
            align-items: center;
            gap: 32px;
            font-size: 14px;
            font-weight: 500;
        }

        .nav-links a {
            color: #b0bcd9;
            text-decoration: none;
            transition: color 0.2s;
        }

        .nav-links a:hover {
            color: #ffffff;
        }

        .nav-btn {
            background: #4f8cf7;
            color: #ffffff !important;
            padding: 8px 22px;
            border-radius: 30px;
            font-weight: 600;
            font-size: 13px;
            transition: background 0.2s;
        }

        .nav-btn:hover {
            background: #6ba0f9 !important;
        }

        /* ---- 一体式语言切换按钮 ---- */
        .lang-toggle {
            background: rgba(255, 255, 255, 0.06);
            border: 1px solid rgba(255, 255, 255, 0.12);
            color: #b0bcd9;
            padding: 4px 14px;
            border-radius: 20px;
            font-size: 13px;
            font-weight: 500;
            cursor: pointer;
            transition: all 0.2s;
            user-select: none;
            letter-spacing: 0.5px;
        }

        .lang-toggle:hover {
            border-color: #4f8cf7;
            color: #ffffff;
            background: rgba(79, 140, 247, 0.08);
        }

        /* ===== 主横幅 ===== */
        .hero {
            padding: 80px 0 60px;
            text-align: center;
            border-bottom: 1px solid rgba(255, 255, 255, 0.04);
        }

        .hero-badge {
            display: inline-block;
            background: rgba(79, 140, 247, 0.12);
            border: 1px solid rgba(79, 140, 247, 0.2);
            color: #7aa9fa;
            padding: 4px 18px;
            border-radius: 30px;
            font-size: 13px;
            font-weight: 500;
            letter-spacing: 0.3px;
            margin-bottom: 28px;
        }

        .hero h1 {
            font-size: 48px;
            font-weight: 700;
            letter-spacing: -1px;
            margin-bottom: 16px;
        }

        .hero h1 span {
            color: #4f8cf7;
        }

        .hero p {
            font-size: 19px;
            color: #94a3c8;
            max-width: 620px;
            margin: 0 auto 20px;
        }

        .hero .desc {
            font-size: 15px;
            color: #6b7ba3;
            max-width: 620px;
            margin: 0 auto 32px;
            line-height: 1.8;
        }

        /* ===== 关于区域 ===== */
        .about {
            padding: 70px 0 50px;
            border-bottom: 1px solid rgba(255, 255, 255, 0.04);
        }

        .about-grid {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 60px;
            align-items: center;
        }

        .about-text h2 {
            font-size: 30px;
            font-weight: 700;
            margin-bottom: 16px;
            letter-spacing: -0.5px;
        }

        .about-text p {
            color: #94a3c8;
            font-size: 15px;
            margin-bottom: 12px;
        }

        .about-stats {
            display: grid;
            grid-template-columns: repeat(3, 1fr);
            gap: 20px;
            background: rgba(255, 255, 255, 0.03);
            border: 1px solid rgba(255, 255, 255, 0.06);
            padding: 28px 20px;
            border-radius: 16px;
            text-align: center;
        }

        .about-stats .stat .number {
            font-size: 30px;
            font-weight: 700;
            color: #4f8cf7;
        }

        .about-stats .stat .label {
            font-size: 13px;
            color: #6b7ba3;
            margin-top: 2px;
        }

        /* ===== 服务/业务 ===== */
        .services {
            padding: 70px 0 50px;
            border-bottom: 1px solid rgba(255, 255, 255, 0.04);
        }

        .section-title {
            text-align: center;
            margin-bottom: 48px;
        }

        .section-title h2 {
            font-size: 30px;
            font-weight: 700;
            letter-spacing: -0.5px;
        }

        .section-title p {
            color: #94a3c8;
            font-size: 15px;
            margin-top: 8px;
        }

        .services-grid {
            display: grid;
            grid-template-columns: repeat(4, 1fr);
            gap: 24px;
        }

        .service-card {
            background: rgba(255, 255, 255, 0.03);
            border: 1px solid rgba(255, 255, 255, 0.06);
            padding: 28px 20px;
            border-radius: 14px;
            text-align: center;
            transition: border-color 0.2s, transform 0.2s;
        }

        .service-card:hover {
            border-color: rgba(79, 140, 247, 0.3);
            transform: translateY(-3px);
        }

        .service-card .icon {
            font-size: 28px;
            margin-bottom: 10px;
        }

        .service-card h4 {
            font-size: 16px;
            font-weight: 600;
            margin-bottom: 6px;
        }

        .service-card p {
            font-size: 13px;
            color: #6b7ba3;
        }

        /* ===== 结算方式标签 ===== */
        .pricing-tags {
            display: flex;
            flex-wrap: wrap;
            justify-content: center;
            gap: 12px;
            margin: 24px 0 10px;
        }

        .pricing-tags span {
            background: rgba(79, 140, 247, 0.08);
            border: 1px solid rgba(79, 140, 247, 0.12);
            color: #7aa9fa;
            padding: 4px 16px;
            border-radius: 30px;
            font-size: 13px;
            font-weight: 500;
        }

        /* ===== 行业标签 ===== */
        .industry-tags {
            display: flex;
            flex-wrap: wrap;
            justify-content: center;
            gap: 12px 20px;
            margin: 20px 0 10px;
        }

        .industry-tags span {
            color: #b0bcd9;
            font-size: 14px;
            font-weight: 500;
        }

        .industry-tags span::before {
            content: "▸ ";
            color: #4f8cf7;
        }

        /* ===== 合作伙伴 ===== */
        .partners {
            padding: 60px 0 50px;
            border-bottom: 1px solid rgba(255, 255, 255, 0.04);
        }

        .partners-grid {
            display: grid;
            grid-template-columns: repeat(6, 1fr);
            gap: 24px;
            text-align: center;
            align-items: center;
        }

        .partner-item {
            color: #6b7ba3;
            font-size: 14px;
            font-weight: 500;
            padding: 12px 0;
            border-radius: 10px;
            background: rgba(255, 255, 255, 0.02);
            transition: color 0.2s, background 0.2s;
        }

        .partner-item:hover {
            color: #ffffff;
            background: rgba(255, 255, 255, 0.05);
        }

        .partner-item .logo-placeholder {
            font-size: 22px;
            font-weight: 600;
            color: #4a5a7a;
            letter-spacing: -0.5px;
        }

        /* ===== 联系区 ===== */
        .contact {
            padding: 70px 0 60px;
            text-align: center;
        }

        .contact h2 {
            font-size: 28px;
            font-weight: 700;
            margin-bottom: 12px;
        }

        .contact p {
            color: #94a3c8;
            font-size: 16px;
            margin-bottom: 28px;
        }

        .contact .email-box {
            display: inline-block;
            background: rgba(255, 255, 255, 0.04);
            border: 1px solid rgba(255, 255, 255, 0.08);
            padding: 14px 44px;
            border-radius: 50px;
            font-size: 18px;
            font-weight: 500;
            color: #7aa9fa;
        }

        .contact .email-box small {
            display: block;
            font-size: 13px;
            font-weight: 400;
            color: #5a6a8a;
            margin-top: 4px;
        }

        /* ===== 页脚 ===== */
        .footer {
            padding: 24px 0;
            text-align: center;
            font-size: 13px;
            color: #3d4a66;
            border-top: 1px solid rgba(255, 255, 255, 0.04);
        }

        /* ===== 响应式 ===== */
        @media (max-width: 1024px) {
            .services-grid {
                grid-template-columns: repeat(2, 1fr);
            }
            .partners-grid {
                grid-template-columns: repeat(3, 1fr);
            }
        }

        @media (max-width: 768px) {
            .navbar {
                flex-wrap: wrap;
                gap: 12px;
                padding: 14px 0;
            }
            .nav-links {
                flex-wrap: wrap;
                gap: 16px;
                font-size: 13px;
            }
            .hero h1 {
                font-size: 32px;
            }
            .hero p {
                font-size: 16px;
            }
            .about-grid {
                grid-template-columns: 1fr;
                gap: 30px;
            }
            .about-stats {
                grid-template-columns: 1fr 1fr 1fr;
            }
            .services-grid {
                grid-template-columns: 1fr;
            }
            .partners-grid {
                grid-template-columns: repeat(2, 1fr);
            }
            .contact .email-box {
                font-size: 15px;
                padding: 12px 24px;
            }
        }

        @media (max-width: 480px) {
            .about-stats {
                grid-template-columns: 1fr;
            }
            .partners-grid {
                grid-template-columns: 1fr 1fr;
            }
            .nav-links {
                gap: 12px;
                font-size: 12px;
            }
            .hero h1 {
                font-size: 26px;
            }
        }
    </style>
</head>
<body>

    <!-- ===== 导航栏 ===== -->
    <nav class="navbar container">
        <div class="logo">Zenith</div>
        <div class="nav-links">
            <a href="#about" data-key="nav_about">关于</a>
            <a href="#services" data-key="nav_services">业务</a>
            <a href="#partners" data-key="nav_partners">合作伙伴</a>
            <a href="#contact" class="nav-btn" data-key="nav_cta">获取方案</a>
            <!-- 一体式语言切换按钮 -->
            <button class="lang-toggle" id="langToggle" onclick="toggleLang()">CN/EN</button>
        </div>
    </nav>

    <!-- ===== 主横幅 ===== -->
    <section class="hero">
        <div class="container">
            <div class="hero-badge" data-key="hero_badge">✦ 全域资源覆盖 · 数据驱动洞察</div>
            <h1 data-key="hero_title">引领数字<span>效果营销</span></h1>
            <p data-key="hero_sub">精益数字营销，助您精准触达全球高质量流量</p>
            <div class="desc" data-key="hero_desc">
                Zenith 是一家专业从事性能营销的数字广告平台，以深刻的数据驱动洞察和商业专业知识为核心竞争力。
                致力于提供高效的多媒体营销解决方案和流量获取服务，旨在最大化广告主的投资回报率（ROI）。
            </div>
        </div>
    </section>

    <!-- ===== 关于我们 ===== -->
    <section class="about" id="about">
        <div class="container">
            <div class="about-grid">
                <div class="about-text">
                    <h2 data-key="about_title">关于 Zenith</h2>
                    <p data-key="about_p1">
                        我们不仅仅是数字广告平台，更是您成功数字营销策略的战略合作伙伴。我们深知市场变化，致力于不断创新，
                        以确保您的广告投资取得卓越成果。
                    </p>
                    <p data-key="about_p2">
                        让我们携手打造卓越的数字营销之路，为您的业务增长提供坚实支持。
                    </p>
                </div>
                <div class="about-stats">
                    <div class="stat">
                        <div class="number">30+</div>
                        <div class="label" data-key="stat_countries">覆盖国家/地区</div>
                    </div>
                    <div class="stat">
                        <div class="number">$10M+</div>
                        <div class="label" data-key="stat_budget">年管理预算</div>
                    </div>
                    <div class="stat">
                        <div class="number">50+</div>
                        <div class="label" data-key="stat_partners">合作伙伴</div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- ===== 业务/服务 ===== -->
    <section class="services" id="services">
        <div class="container">
            <div class="section-title">
                <h2 data-key="services_title">效果营销平台</h2>
                <p data-key="services_sub">覆盖营销漏斗各环节，精准触达全球高质量流量</p>
            </div>

            <div class="services-grid">
                <div class="service-card">
                    <div class="icon">📱</div>
                    <h4 data-key="svc1_title">联盟营销</h4>
                    <p data-key="svc1_desc">覆盖全球优质Affiliate渠道，按效果付费</p>
                </div>
                <div class="service-card">
                    <div class="icon">🎯</div>
                    <h4 data-key="svc2_title">媒体购买</h4>
                    <p data-key="svc2_desc">程序化采买，精准定向目标受众</p>
                </div>
                <div class="service-card">
                    <div class="icon">⚡</div>
                    <h4 data-key="svc3_title">实时竞价</h4>
                    <p data-key="svc3_desc">RTB技术驱动，高效获取高质量流量</p>
                </div>
                <div class="service-card">
                    <div class="icon">📊</div>
                    <h4 data-key="svc4_title">数据洞察</h4>
                    <p data-key="svc4_desc">深度数据分析，持续优化投放策略</p>
                </div>
            </div>

            <!-- 结算方式 -->
            <div class="pricing-tags">
                <span>CPC</span>
                <span>CPI</span>
                <span>CPA</span>
                <span>CPL</span>
                <span>CPS</span>
            </div>

            <!-- 行业覆盖 -->
            <div class="industry-tags">
                <span data-key="ind_finance">金融</span>
                <span data-key="ind_tools">工具</span>
                <span data-key="ind_social">社交</span>
                <span data-key="ind_games">游戏</span>
                <span data-key="ind_health">健康</span>
                <span data-key="ind_ecommerce">电商</span>
            </div>
        </div>
    </section>

    <!-- ===== 合作伙伴 ===== -->
    <section class="partners" id="partners">
        <div class="container">
            <div class="section-title">
                <h2 data-key="partners_title">合作伙伴</h2>
                <p data-key="partners_sub">与全球顶级媒体平台深度合作</p>
            </div>
            <div class="partners-grid">
                <div class="partner-item"><span class="logo-placeholder">Google</span></div>
                <div class="partner-item"><span class="logo-placeholder">Meta</span></div>
                <div class="partner-item"><span class="logo-placeholder">TikTok</span></div>
                <div class="partner-item"><span class="logo-placeholder">Taboola</span></div>
                <div class="partner-item"><span class="logo-placeholder">Snapchat</span></div>
                <div class="partner-item"><span class="logo-placeholder">Yandex</span></div>
                <div class="partner-item"><span class="logo-placeholder">YouTube</span></div>
                <div class="partner-item"><span class="logo-placeholder">LinkedIn</span></div>
                <div class="partner-item"><span class="logo-placeholder">Pinterest</span></div>
                <div class="partner-item"><span class="logo-placeholder">LINE</span></div>
                <div class="partner-item"><span class="logo-placeholder">Bing</span></div>
                <div class="partner-item"><span class="logo-placeholder">Yahoo</span></div>
            </div>
        </div>
    </section>

    <!-- ===== 联系区 ===== -->
    <section class="contact" id="contact">
        <div class="container">
            <h2 data-key="contact_title">📩 开始合作</h2>
            <p data-key="contact_sub">深入了解您的业务需求，为您量身定制最有效的广告战略</p>
            <div class="email-box">
                Sam@zenithads.net.cn
                <small data-key="contact_hint">回复时间：24 小时内</small>
            </div>
        </div>
    </section>

    <!-- ===== 页脚 ===== -->
    <div class="footer">
        <div class="container">
            &copy; 2026 Zenith. <span data-key="footer_rights">All rights reserved.</span>
        </div>
    </div>

    <!-- ============================================================ -->
    <!-- ===== 双语切换 JavaScript（一体式切换） ===== -->
    <script>
        // ===== 语言包 =====
        const translations = {
            zh: {
                // 导航
                nav_about: '关于',
                nav_services: '业务',
                nav_partners: '合作伙伴',
                nav_cta: '获取方案',

                // 横幅
                hero_badge: '✦ 全域资源覆盖 · 数据驱动洞察',
                hero_title: '引领数字<span>效果营销</span>',
                hero_sub: '精益数字营销，助您精准触达全球高质量流量',
                hero_desc: 'Zenith 是一家专业从事性能营销的数字广告平台，以深刻的数据驱动洞察和商业专业知识为核心竞争力。致力于提供高效的多媒体营销解决方案和流量获取服务，旨在最大化广告主的投资回报率（ROI）。',

                // 关于
                about_title: '关于 Zenith',
                about_p1: '我们不仅仅是数字广告平台，更是您成功数字营销策略的战略合作伙伴。我们深知市场变化，致力于不断创新，以确保您的广告投资取得卓越成果。',
                about_p2: '让我们携手打造卓越的数字营销之路，为您的业务增长提供坚实支持。',
                stat_countries: '覆盖国家/地区',
                stat_budget: '年管理预算',
                stat_partners: '合作伙伴',

                // 业务
                services_title: '效果营销平台',
                services_sub: '覆盖营销漏斗各环节，精准触达全球高质量流量',
                svc1_title: '联盟营销',
                svc1_desc: '覆盖全球优质Affiliate渠道，按效果付费',
                svc2_title: '媒体购买',
                svc2_desc: '程序化采买，精准定向目标受众',
                svc3_title: '实时竞价',
                svc3_desc: 'RTB技术驱动，高效获取高质量流量',
                svc4_title: '数据洞察',
                svc4_desc: '深度数据分析，持续优化投放策略',

                // 行业
                ind_finance: '金融',
                ind_tools: '工具',
                ind_social: '社交',
                ind_games: '游戏',
                ind_health: '健康',
                ind_ecommerce: '电商',

                // 合作伙伴
                partners_title: '合作伙伴',
                partners_sub: '与全球顶级媒体平台深度合作',

                // 联系
                contact_title: '📩 开始合作',
                contact_sub: '深入了解您的业务需求，为您量身定制最有效的广告战略',
                contact_hint: '回复时间：24 小时内',

                // 页脚
                footer_rights: 'All rights reserved.'
            },
            en: {
                // Navigation
                nav_about: 'About',
                nav_services: 'Services',
                nav_partners: 'Partners',
                nav_cta: 'Get Started',

                // Hero
                hero_badge: '✦ Global Coverage · Data-Driven Insights',
                hero_title: 'Leading Digital <span>Performance Marketing</span>',
                hero_sub: 'Precision digital marketing to reach high-quality global traffic',
                hero_desc: 'Zenith is a professional performance marketing digital ad platform, with deep data-driven insights and business expertise as our core competitiveness. We are committed to providing efficient multimedia marketing solutions and traffic acquisition services to maximize advertisers\' ROI.',

                // About
                about_title: 'About Zenith',
                about_p1: 'We are more than just a digital ad platform — we are your strategic partner for successful digital marketing. We understand market dynamics and are dedicated to continuous innovation, ensuring your advertising investments deliver outstanding results.',
                about_p2: 'Let\'s build an exceptional digital marketing journey together, providing solid support for your business growth.',
                stat_countries: 'Countries Covered',
                stat_budget: 'Annual Managed Budget',
                stat_partners: 'Partners',

                // Services
                services_title: 'Performance Marketing Platform',
                services_sub: 'Full-funnel coverage from affiliate marketing to programmatic buying',
                svc1_title: 'Affiliate Marketing',
                svc1_desc: 'Global top affiliate networks, performance-based pricing',
                svc2_title: 'Media Buying',
                svc2_desc: 'Programmatic purchasing with precise audience targeting',
                svc3_title: 'Real-Time Bidding',
                svc3_desc: 'RTB technology for efficient high-quality traffic acquisition',
                svc4_title: 'Data Insights',
                svc4_desc: 'In-depth data analysis for continuous campaign optimization',

                // Industries
                ind_finance: 'Finance',
                ind_tools: 'Tools',
                ind_social: 'Social',
                ind_games: 'Games',
                ind_health: 'Health',
                ind_ecommerce: 'E-Commerce',

                // Partners
                partners_title: 'Partners',
                partners_sub: 'Deep partnerships with global top media platforms',

                // Contact
                contact_title: '📩 Let\'s Partner',
                contact_sub: 'Tell us your business needs and we\'ll tailor the most effective advertising strategy',
                contact_hint: 'Response within 24 hours',

                // Footer
                footer_rights: 'All rights reserved.'
            }
        };

        // ===== 当前语言（从 localStorage 读取，默认中文） =====
        let currentLang = localStorage.getItem('zenith_lang') || 'zh';

        // ===== 切换函数 =====
        function toggleLang() {
            // 切换语言
            currentLang = (currentLang === 'zh') ? 'en' : 'zh';
            localStorage.setItem('zenith_lang', currentLang);
            applyLanguage(currentLang);
        }

        // ===== 应用语言 =====
        function applyLanguage(lang) {
            const dict = translations[lang];
            document.querySelectorAll('[data-key]').forEach(el => {
                const key = el.getAttribute('data-key');
                if (dict[key] !== undefined) {
                    // 如果 key 是 hero_title，需要保留内部的 <span> 标签
                    if (key === 'hero_title') {
                        el.innerHTML = dict[key];
                    } else {
                        el.textContent = dict[key];
                    }
                }
            });
            // 可选：按钮文本保持不变（CN/EN），不需要额外操作
        }

        // ===== 页面加载时恢复语言 =====
        document.addEventListener('DOMContentLoaded', function() {
            applyLanguage(currentLang);
        });
    </script>

</body>
</html>
