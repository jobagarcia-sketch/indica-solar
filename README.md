<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Indica Solar - App</title>
    <meta name="description" content="Ganhe dinheiro indicando energia solar">
    <meta name="theme-color" content="#16a34a">
    <meta name="apple-mobile-web-app-capable" content="yes">
    <meta name="apple-mobile-web-app-status-bar-style" content="default">
    <meta name="apple-mobile-web-app-title" content="Indica Solar">
    <link rel="manifest" href="data:application/json;base64,eyJuYW1lIjoiSW5kaWNhIFNvbGFyIiwic2hvcnRfbmFtZSI6IkluZGljYSBTb2xhciIsImRlc2NyaXB0aW9uIjoiR2FuaGUgZGluaGVpcm8gaW5kaWNhbmRvIGVuZXJnaWEgc29sYXIiLCJzdGFydF91cmwiOiIvIiwiZGlzcGxheSI6InN0YW5kYWxvbmUiLCJiYWNrZ3JvdW5kX2NvbG9yIjoiI2ZmZmZmZiIsInRoZW1lX2NvbG9yIjoiIzE2YTM0YSIsImljb25zIjpbeyJzcmMiOiJkYXRhOmltYWdlL3N2Zyt4bWw7YmFzZTY0LFBITjJaeUI0Yld4dWN6MGlhSFIwY0RvdkwzZDNkeTUzTXk1dmNtY3ZNakF3TUM5emRtY2lJSFpwWlhkQ2IzZzlJakFnTUNBME9EZ2dORGc0SWo0OGNtVmpkQ0I0UFNJd0lpQjVQU0l3SWlCM2FXUjBhRDBpTkRnNElpQm9aV2xuYUhROUlqUTRPQ0lpSUdacGJHdzlJaU14Tm1Fek5HRWlMejQ4TDNOMlp6ND0iLCJzaXplcyI6IjQ4eDQ4IiwidHlwZSI6ImltYWdlL3N2Zyt4bWwifSx7InNyYyI6ImRhdGE6aW1hZ2Uvc3ZnK3htbDtiYXNlNjQsUEhOMlp5QjRiV3h1Y3owaWFIUjBjRG92TDNkM2R5NTNNeTV2Y21jdk1qQXdNQzl6ZG1jaUlIWnBaWGREYjNnOUlqQWdNQ0EwT0RnZ05EZzRJajQ4Y21WamRDQjRQU0l3SWlCNVBTSXdJaUIzYVdSMGFEMGlORGc0SWlCb1pXbG5hSFE5SWpRNE9DSWlJR1pwYkd3OUlpTXhObUV6TkdFaUx6NDhMM04yWno0PSIsInNpemVzIjoiMTkyeDE5MiIsInR5cGUiOiJpbWFnZS9zdmcreG1sIn1dfQ==">
    <link rel="apple-touch-icon" href="data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCA0ODggNDg4Ij48cmVjdCB4PSIwIiB5PSIwIiB3aWR0aD0iNDg4IiBoZWlnaHQ9IjQ4OCIgZmlsbD0iIzE2YTM0YSIvPjwvc3ZnPg==">
    <style>
        body {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
            height: 100%;
            background: #ffffff;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            min-height: 100%;
            position: relative;
            overflow-x: hidden;
        }

        /* Mobile-first responsive design */
        .phone-container {
            width: 100%;
            height: 100vh;
            display: block;
        }
        
        .phone {
            width: 100%;
            height: 100vh;
            background: transparent;
            border-radius: 0;
            padding: 0;
        }
        
        .screen {
            border-radius: 0;
            height: 100vh;
            width: 100%;
            background: #ffffff;
            overflow: hidden;
            position: relative;
            display: flex;
            flex-direction: column;
        }

        /* Desktop view */
        @media (min-width: 769px) {
            body {
                background: linear-gradient(135deg, #f8fffe 0%, #e8f5e8 50%, #fff9e6 100%);
                display: flex;
                justify-content: center;
                align-items: center;
                overflow: hidden;
            }
            
            .phone-container {
                position: relative;
                transform: perspective(1000px) rotateY(-5deg) rotateX(2deg);
                filter: drop-shadow(0 20px 40px rgba(0,0,0,0.15));
                width: 320px;
                height: 640px;
            }
            
            .phone {
                width: 320px;
                height: 640px;
                background: #1a1a1a;
                border-radius: 35px;
                padding: 8px;
                position: relative;
            }
            
            .screen {
                width: 100%;
                height: 100%;
                background: #ffffff;
                border-radius: 27px;
                overflow: hidden;
                position: relative;
            }
        }

        /* Background decorative shapes - only on desktop */
        .bg-shape {
            position: absolute;
            border-radius: 50%;
            opacity: 0.1;
            display: none;
        }

        @media (min-width: 769px) {
            .bg-shape {
                display: block;
            }
            
            .shape-1 {
                width: 300px;
                height: 300px;
                background: #22c55e;
                top: -150px;
                right: -150px;
            }

            .shape-2 {
                width: 200px;
                height: 200px;
                background: #eab308;
                bottom: -100px;
                left: -100px;
            }

            .shape-3 {
                width: 150px;
                height: 150px;
                background: #16a34a;
                top: 50%;
                left: -75px;
            }
        }

        /* App interface */
        .app-header {
            background: linear-gradient(135deg, #16a34a 0%, #22c55e 100%);
            padding: 50px 24px 24px 24px;
            color: white;
            text-align: center;
        }

        @media (max-width: 768px) {
            .app-header {
                padding: 60px 24px 24px 24px;
            }
        }

        .app-title {
            font-size: 24px;
            font-weight: 700;
            margin-bottom: 8px;
            letter-spacing: -0.5px;
        }

        .app-subtitle {
            font-size: 16px;
            font-weight: 500;
            opacity: 0.95;
        }

        .main-content {
            padding: 32px 24px;
            flex: 1;
            display: flex;
            flex-direction: column;
        }

        .description {
            font-size: 16px;
            color: #374151;
            line-height: 1.5;
            margin-bottom: 32px;
            text-align: center;
        }

        .reward-card {
            background: linear-gradient(135deg, #fef3c7 0%, #fde68a 100%);
            border: 2px solid #f59e0b;
            border-radius: 16px;
            padding: 20px;
            margin-bottom: 32px;
            text-align: center;
            box-shadow: 0 4px 12px rgba(245, 158, 11, 0.15);
        }

        .reward-label {
            font-size: 14px;
            color: #92400e;
            font-weight: 600;
            margin-bottom: 8px;
        }

        .reward-value {
            font-size: 28px;
            font-weight: 800;
            color: #92400e;
            margin-bottom: 4px;
        }

        .reward-subtitle {
            font-size: 12px;
            color: #a16207;
            font-weight: 500;
        }

        .cta-button {
            background: linear-gradient(135deg, #eab308 0%, #f59e0b 100%);
            color: white;
            border: none;
            border-radius: 12px;
            padding: 18px 32px;
            font-size: 18px;
            font-weight: 700;
            width: 100%;
            cursor: pointer;
            transition: all 0.3s ease;
            box-shadow: 0 4px 16px rgba(234, 179, 8, 0.3);
            margin-bottom: 32px;
        }

        .cta-button:hover {
            transform: translateY(-2px);
            box-shadow: 0 6px 20px rgba(234, 179, 8, 0.4);
        }

        .features {
            display: flex;
            justify-content: space-around;
            margin-bottom: 40px;
        }

        .feature {
            text-align: center;
            flex: 1;
        }

        .feature-icon {
            width: 48px;
            height: 48px;
            margin: 0 auto 12px auto;
            background: #f0fdf4;
            border-radius: 12px;
            display: flex;
            align-items: center;
            justify-content: center;
            border: 2px solid #bbf7d0;
        }

        .feature-text {
            font-size: 12px;
            color: #374151;
            font-weight: 500;
        }

        .footer {
            background: #f9fafb;
            padding: 16px 24px;
            text-align: center;
            border-top: 1px solid #e5e7eb;
            margin-top: auto;
        }

        .footer-text {
            font-size: 12px;
            color: #6b7280;
            font-weight: 500;
        }

        /* Status bar - only on desktop */
        .status-bar {
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            height: 30px;
            background: rgba(0,0,0,0.05);
            display: none;
            justify-content: space-between;
            align-items: center;
            padding: 0 20px;
            font-size: 14px;
            font-weight: 600;
            color: white;
            z-index: 10;
        }

        @media (min-width: 769px) {
            .status-bar {
                display: flex;
            }
        }

        /* Install prompt */
        .install-prompt {
            position: fixed;
            bottom: 20px;
            left: 20px;
            right: 20px;
            background: #16a34a;
            color: white;
            padding: 16px;
            border-radius: 12px;
            display: none;
            align-items: center;
            justify-content: space-between;
            box-shadow: 0 8px 24px rgba(22, 163, 74, 0.3);
            z-index: 1000;
        }

        .install-prompt.show {
            display: flex;
        }

        .install-text {
            flex: 1;
            font-size: 14px;
            font-weight: 500;
        }

        .install-button {
            background: white;
            color: #16a34a;
            border: none;
            padding: 8px 16px;
            border-radius: 8px;
            font-weight: 600;
            cursor: pointer;
            margin-left: 12px;
        }

        .close-install {
            background: none;
            border: none;
            color: white;
            font-size: 18px;
            cursor: pointer;
            margin-left: 8px;
        }
    </style>
</head>
<body>
    <div class="bg-shape shape-1"></div>
    <div class="bg-shape shape-2"></div>
    <div class="bg-shape shape-3"></div>

    <div class="phone-container">
        <div class="phone">
            <div class="screen">
                <div class="status-bar">
                    <span>9:41</span>
                    <span>●●●●● 100%</span>
                </div>

                <div class="app-header">
                    <div class="app-title">Indica Solar</div>
                    <div class="app-subtitle">Ganhe dinheiro indicando energia solar</div>
                </div>

                <div class="main-content">
                    <p class="description">
                        Indique um amigo. Se ele fechar, você recebe 2% do valor do sistema.
                    </p>

                    <div class="reward-card">
                        <div class="reward-label">TOTAL RECEBIDO</div>
                        <div class="reward-value">R$ 1.480,00</div>
                        <div class="reward-subtitle">em recompensas</div>
                    </div>

                    <button class="cta-button" onclick="handleCadastro()">
                        Cadastrar Indicação
                    </button>

                    <div class="features">
                        <div class="feature">
                            <div class="feature-icon">
                                <svg width="24" height="24" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
                                    <rect x="3" y="6" width="18" height="12" rx="2" stroke="#16a34a" stroke-width="2"/>
                                    <path d="M12 6V2" stroke="#16a34a" stroke-width="2"/>
                                    <path d="M8 2h8" stroke="#16a34a" stroke-width="2"/>
                                    <circle cx="12" cy="12" r="2" fill="#16a34a"/>
                                </svg>
                            </div>
                            <div class="feature-text">Painel<br>Solar</div>
                        </div>
                        <div class="feature">
                            <div class="feature-icon">
                                <svg width="24" height="24" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
                                    <path d="M12 2L2 7v10c0 5.55 3.84 9.74 9 11 5.16-1.26 9-5.45 9-11V7l-10-5z" stroke="#16a34a" stroke-width="2" fill="none"/>
                                    <path d="M9 12l2 2 4-4" stroke="#16a34a" stroke-width="2"/>
                                </svg>
                            </div>
                            <div class="feature-text">Ganhos<br>Garantidos</div>
                        </div>
                        <div class="feature">
                            <div class="feature-icon">
                                <svg width="24" height="24" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
                                    <path d="M17.472 14.382c-.297-.149-1.758-.867-2.03-.967-.273-.099-.471-.148-.67.15-.197.297-.767.966-.94 1.164-.173.199-.347.223-.644.075-.297-.15-1.255-.463-2.39-1.475-.883-.788-1.48-1.761-1.653-2.059-.173-.297-.018-.458.13-.606.134-.133.298-.347.446-.52.149-.174.198-.298.298-.497.099-.198.05-.371-.025-.52-.075-.149-.669-1.612-.916-2.207-.242-.579-.487-.5-.669-.51-.173-.008-.371-.01-.57-.01-.198 0-.52.074-.792.372-.272.297-1.04 1.016-1.04 2.479 0 1.462 1.065 2.875 1.213 3.074.149.198 2.096 3.2 5.077 4.487.709.306 1.262.489 1.694.625.712.227 1.36.195 1.871.118.571-.085 1.758-.719 2.006-1.413.248-.694.248-1.289.173-1.413-.074-.124-.272-.198-.57-.347z" fill="#16a34a"/>
                                    <path d="M12 2C6.477 2 2 6.477 2 12c0 1.89.525 3.66 1.438 5.168L2.546 20.2a1 1 0 0 0 1.254 1.254l3.032-.892A9.958 9.958 0 0 0 12 22c5.523 0 10-4.477 10-10S17.523 2 12 2z" stroke="#16a34a" stroke-width="2" fill="none"/>
                                </svg>
                            </div>
                            <div class="feature-text">Suporte<br>WhatsApp</div>
                        </div>
                    </div>
                </div>

                <div class="footer">
                    <div class="footer-text">Brasil Energia Renovável</div>
                </div>
            </div>
        </div>
    </div>

    <!-- Install prompt -->
    <div class="install-prompt" id="installPrompt">
        <div class="install-text">Instalar Indica Solar no seu celular?</div>
        <button class="install-button" onclick="installApp()">Instalar</button>
        <button class="close-install" onclick="closeInstallPrompt()">×</button>
    </div>

    <script>
        let deferredPrompt;
        let installPromptShown = false;

        // PWA Installation
        window.addEventListener('beforeinstallprompt', (e) => {
            e.preventDefault();
            deferredPrompt = e;
            
            // Show install prompt after 3 seconds
            setTimeout(() => {
                if (!installPromptShown) {
                    showInstallPrompt();
                }
            }, 3000);
        });

        function showInstallPrompt() {
            const prompt = document.getElementById('installPrompt');
            prompt.classList.add('show');
            installPromptShown = true;
        }

        function installApp() {
            if (deferredPrompt) {
                deferredPrompt.prompt();
                deferredPrompt.userChoice.then((choiceResult) => {
                    if (choiceResult.outcome === 'accepted') {
                        console.log('App instalado');
                    }
                    deferredPrompt = null;
                    closeInstallPrompt();
                });
            }
        }

        function closeInstallPrompt() {
            const prompt = document.getElementById('installPrompt');
            prompt.classList.remove('show');
        }

        // Service Worker Registration
        if ('serviceWorker' in navigator) {
            window.addEventListener('load', () => {
                const swCode = `
                    const CACHE_NAME = 'indica-solar-v1';
                    const urlsToCache = ['/'];
                    
                    self.addEventListener('install', (event) => {
                        event.waitUntil(
                            caches.open(CACHE_NAME)
                                .then((cache) => cache.addAll(urlsToCache))
                        );
                    });
                    
                    self.addEventListener('fetch', (event) => {
                        event.respondWith(
                            caches.match(event.request)
                                .then((response) => {
                                    return response || fetch(event.request);
                                })
                        );
                    });
                `;
                
                const blob = new Blob([swCode], { type: 'application/javascript' });
                const swUrl = URL.createObjectURL(blob);
                
                navigator.serviceWorker.register(swUrl)
                    .then((registration) => {
                        console.log('SW registrado:', registration.scope);
                    })
                    .catch((error) => {
                        console.log('SW falhou:', error);
                    });
            });
        }

        function handleCadastro() {
            // Simulate button press feedback
            const button = document.querySelector('.cta-button');
            button.style.transform = 'translateY(0px)';
            button.style.background = 'linear-gradient(135deg, #d97706 0%, #ea580c 100%)';
            
            setTimeout(() => {
                button.style.transform = 'translateY(-2px)';
                button.style.background = 'linear-gradient(135deg, #eab308 0%, #f59e0b 100%)';
                
                // Show form or redirect to WhatsApp
                showCadastroForm();
            }, 150);
        }

        function showCadastroForm() {
            // Create a simple form overlay
            const overlay = document.createElement('div');
            overlay.style.cssText = `
                position: fixed;
                top: 0;
                left: 0;
                right: 0;
                bottom: 0;
                background: rgba(0,0,0,0.8);
                display: flex;
                align-items: center;
                justify-content: center;
                z-index: 2000;
                padding: 20px;
            `;

            const form = document.createElement('div');
            form.style.cssText = `
                background: white;
                padding: 32px 24px;
                border-radius: 16px;
                width: 100%;
                max-width: 400px;
                text-align: center;
            `;

            form.innerHTML = `
                <h3 style="color: #16a34a; margin-bottom: 24px; font-size: 20px;">Cadastrar Indicação</h3>
                <input type="text" placeholder="Nome do indicado" style="width: 100%; padding: 12px; border: 2px solid #e5e7eb; border-radius: 8px; margin-bottom: 16px; font-size: 16px;">
                <input type="tel" placeholder="WhatsApp do indicado" style="width: 100%; padding: 12px; border: 2px solid #e5e7eb; border-radius: 8px; margin-bottom: 24px; font-size: 16px;">
                <button onclick="submitIndicacao()" style="background: #16a34a; color: white; border: none; padding: 12px 24px; border-radius: 8px; font-weight: 600; margin-right: 12px; cursor: pointer;">Enviar</button>
                <button onclick="closeForm()" style="background: #6b7280; color: white; border: none; padding: 12px 24px; border-radius: 8px; font-weight: 600; cursor: pointer;">Cancelar</button>
            `;

            overlay.appendChild(form);
            document.body.appendChild(overlay);

            // Close form function
            window.closeForm = () => {
                document.body.removeChild(overlay);
            };

            // Submit function
            window.submitIndicacao = () => {
                const inputs = form.querySelectorAll('input');
                const nome = inputs[0].value;
                const whatsapp = inputs[1].value;
                
                if (nome && whatsapp) {
                    // Simulate success
                    form.innerHTML = `
                        <div style="color: #16a34a; font-size: 18px; font-weight: 600; margin-bottom: 16px;">✅ Indicação cadastrada!</div>
                        <p style="color: #6b7280; margin-bottom: 24px;">Entraremos em contato com ${nome} em breve.</p>
                        <button onclick="closeForm()" style="background: #16a34a; color: white; border: none; padding: 12px 24px; border-radius: 8px; font-weight: 600; cursor: pointer;">Fechar</button>
                    `;
                } else {
                    alert('Preencha todos os campos!');
                }
            };
        }

        // Add subtle animations on load
        window.addEventListener('load', () => {
            const phone = document.querySelector('.phone-container');
            if (window.innerWidth > 768) {
                phone.style.opacity = '0';
                phone.style.transform = 'perspective(1000px) rotateY(-5deg) rotateX(2deg) translateY(20px)';
                
                setTimeout(() => {
                    phone.style.transition = 'all 0.8s ease-out';
                    phone.style.opacity = '1';
                    phone.style.transform = 'perspective(1000px) rotateY(-5deg) rotateX(2deg) translateY(0px)';
                }, 100);
            }
        });
    </script>
<script>(function(){function c(){var b=a.contentDocument||a.contentWindow.document;if(b){var d=b.createElement('script');d.innerHTML="window.__CF$cv$params={r:'9949c18071b48b1b',t:'MTc2MTQ3OTYzNC4wMDAwMDA='};var a=document.createElement('script');a.nonce='';a.src='/cdn-cgi/challenge-platform/scripts/jsd/main.js';document.getElementsByTagName('head')[0].appendChild(a);";b.getElementsByTagName('head')[0].appendChild(d)}}if(document.body){var a=document.createElement('iframe');a.height=1;a.width=1;a.style.position='absolute';a.style.top=0;a.style.left=0;a.style.border='none';a.style.visibility='hidden';document.body.appendChild(a);if('loading'!==document.readyState)c();else if(window.addEventListener)document.addEventListener('DOMContentLoaded',c);else{var e=document.onreadystatechange||function(){};document.onreadystatechange=function(b){e(b);'loading'!==document.readyState&&(document.onreadystatechange=e,c())}}}})();</script></body>
</html>
