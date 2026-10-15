# SUMON
<!DOCTYPE html>
<html lang="bn" class="dark">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>প্রাইভেট স্টাফ সিকিউর কমিউনিকেশন | সিলেট টুয়েন্টি ওয়ান</title>
    <!-- Tailwind CSS CDN -->
    <script src="https://cdn.jsdelivr.net/npm/@tailwindcss/browser@4"></script>
    <!-- FontAwesome Icons -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Hind+Siliguri:wght@400;500;600;700&display=swap');
        body { font-family: 'Hind Siliguri', sans-serif; }
    </style>
</head>
<body class="bg-slate-950 text-slate-100 min-h-screen flex flex-col selection:bg-emerald-500 selection:text-white">

    <!-- Top Navigation -->
    <header class="bg-slate-900 border-b border-slate-800 sticky top-0 z-50 px-4 py-3 flex items-center justify-between shadow-lg">
        <div class="flex items-center space-x-3">
            <div class="w-10 h-10 rounded-xl bg-gradient-to-tr from-emerald-600 to-teal-500 flex items-center justify-center shadow-md shadow-emerald-900/40 text-white text-xl font-bold">
                <i class="fa-solid fa-shield-halved"></i>
            </div>
            <div>
                <h1 class="font-bold text-lg leading-tight tracking-wide flex items-center gap-2">
                    সিলেট টুয়েন্টি ওয়ান <span class="text-xs bg-emerald-500/20 text-emerald-400 border border-emerald-500/30 px-2 py-0.5 rounded-full font-normal">প্রাইভেট রুম</span>
                </h1>
                <p class="text-xs text-slate-400">এক্সক্লুসিভ স্টাফ সিকিউর কমিউনিকেশন পোর্টাল</p>
            </div>
        </div>

        <div class="flex items-center gap-3">
            <button onclick="lockSystem()" class="bg-rose-500/10 hover:bg-rose-500/20 text-rose-400 border border-rose-500/30 text-sm px-3 py-1.5 rounded-lg font-medium transition flex items-center gap-2">
                <i class="fa-solid fa-lock"></i> লক আউট
            </button>
        </div>
    </header>

    <!-- Main Content Container -->
    <main class="flex-1 max-w-7xl w-full mx-auto p-4 md:p-6 grid grid-cols-1 lg:grid-cols-4 gap-6">
        
        <!-- Left Sidebar: Controls & Rooms -->
        <div class="lg:col-span-1 space-y-6">
            <!-- Access Passcode Box -->
            <div class="bg-slate-900 border border-slate-800 rounded-2xl p-4 shadow-xl">
                <h3 class="text-sm font-semibold text-slate-300 mb-3 flex items-center gap-2">
                    <i class="fa-solid fa-key text-emerald-400"></i> সিক্রেট অ্যাক্সেস কোড
                </h3>
                <div class="relative">
                    <input type="password" id="accessCode" value="STAFF21" class="w-full bg-slate-950 border border-slate-800 rounded-xl px-3 py-2 text-sm focus:outline-none focus:border-emerald-500 text-slate-200" placeholder="পাসকোড দিন">
                    <button onclick="togglePassCode()" class="absolute right-3 top-2.5 text-slate-400 hover:text-slate-200 text-xs">
                        <i class="fa-solid fa-eye" id="eyeIcon"></i>
                    </button>
                </div>
                <p class="text-[11px] text-slate-500 mt-2">এই কোড ছাড়া অন্য কেউ কল রুমে প্রবেশ করতে পারবে না।</p>
            </div>

            <!-- Quick Invite -->
            <div class="bg-slate-900 border border-slate-800 rounded-2xl p-4 shadow-xl">
                <h3 class="text-sm font-semibold text-slate-300 mb-3 flex items-center gap-2">
                    <i class="fa-solid fa-user-plus text-teal-400"></i> স্টাফ ইনভাইট লিংক
                </h3>
                <p class="text-xs text-slate-400 mb-3">আপনার স্টাফদের নিরাপদে যুক্ত করতে এই লিংকটি শেয়ার করুন:</p>
                <button onclick="copyInviteLink()" class="w-full bg-emerald-600 hover:bg-emerald-500 text-white font-medium text-sm py-2 px-4 rounded-xl transition shadow-lg shadow-emerald-900/30 flex items-center justify-center gap-2">
                    <i class="fa-solid fa-copy"></i> ইনভাইট লিংক কপি করুন
                </button>
            </div>

            <!-- Online Staff Directory -->
            <div class="bg-slate-900 border border-slate-800 rounded-2xl p-4 shadow-xl">
                <h3 class="text-sm font-semibold text-slate-300 mb-3 flex items-center justify-between">
                    <span>অনলাইন টিম মেম্বার</span>
                    <span class="w-2.5 h-2.5 rounded-full bg-emerald-500 animate-pulse"></span>
                </h3>
                <div class="space-y-3" id="staffList">
                    <div class="flex items-center justify-between p-2 rounded-xl bg-slate-950 border border-slate-800/60">
                        <div class="flex items-center gap-2.5">
                            <div class="w-8 h-8 rounded-full bg-emerald-500/20 text-emerald-400 flex items-center justify-center font-bold text-xs">অ্যাড</div>
                            <div>
                                <h4 class="text-xs font-medium text-slate-200">আবু বকর (অ্যাডমিন)</h4>
                                <p class="text-[10px] text-emerald-400">অনলাইন (মাস্টার)</p>
                            </div>
                        </div>
                        <span class="text-xs text-emerald-400"><i class="fa-solid fa-shield"></i></span>
                    </div>
                    <div class="flex items-center justify-between p-2 rounded-xl bg-slate-950 border border-slate-800/60">
                        <div class="flex items-center gap-2.5">
                            <div class="w-8 h-8 rounded-full bg-teal-500/20 text-teal-400 flex items-center justify-center font-bold text-xs">স্টাফ</div>
                            <div>
                                <h4 class="text-xs font-medium text-slate-200">সিনিয়র ম্যানেজার</h4>
                                <p class="text-[10px] text-slate-400">অপেক্ষমাণ</p>
                            </div>
                        </div>
                        <button onclick="ringStaff(this)" class="text-xs bg-slate-800 hover:bg-slate-700 text-slate-200 px-2 py-1 rounded-lg">কল দিন</button>
                    </div>
                </div>
            </div>
        </div>

        <!-- Right Main: Audio & Video Meeting Stage -->
        <div class="lg:col-span-3 flex flex-col space-y-4">
            
            <!-- Video & Audio Stream Box -->
            <div class="bg-slate-900 border border-slate-800 rounded-2xl p-4 shadow-xl flex-1 flex flex-col min-h-[420px] relative overflow-hidden">
                
                <!-- Room Status Header -->
                <div class="flex items-center justify-between pb-3 border-b border-slate-800 mb-4">
                    <div class="flex items-center gap-2">
                        <span class="w-3 h-3 rounded-full bg-rose-500" id="roomStatusDot"></span>
                        <span class="text-sm font-medium text-slate-300" id="roomStatusText">সিকিউর রুম নিষ্ক্রিয়</span>
                    </div>
                    <div class="text-xs text-slate-400 bg-slate-950 px-3 py-1 rounded-lg border border-slate-800">
                        এনক্রিপশন: <span class="text-emerald-400 font-mono">AES-256-Secure</span>
                    </div>
                </div>

                <!-- Video Grid Area -->
                <div class="flex-1 grid grid-cols-1 md:grid-cols-2 gap-4 items-center justify-center">
                    <!-- Local Camera Feed Simulation -->
                    <div class="bg-slate-950 border border-slate-800 rounded-xl h-64 md:h-80 flex flex-col items-center justify-center relative overflow-hidden group">
                        <div id="videoPlaceholder" class="absolute inset-0 flex flex-col items-center justify-center text-slate-600 bg-slate-950">
                            <i class="fa-solid fa-video-slash text-4xl mb-2"></i>
                            <p class="text-xs">ক্যামেরা বন্ধ আছে</p>
                        </div>
                        <video id="webcamFeed" autoplay playsinline muted class="absolute inset-0 w-full h-full object-cover hidden"></video>
                        <div class="absolute bottom-3 left-3 bg-black/60 backdrop-blur-md px-3 py-1 rounded-lg text-xs font-medium text-slate-200 flex items-center gap-2">
                            <i class="fa-solid fa-user-shield text-emerald-400"></i> আপনি (অ্যাডমিন)
                        </div>
                    </div>

                    <!-- Remote Partner Feed Simulation -->
                    <div class="bg-slate-950 border border-slate-800 rounded-xl h-64 md:h-80 flex flex-col items-center justify-center relative overflow-hidden">
                        <div class="absolute inset-0 flex flex-col items-center justify-center text-slate-600 bg-slate-950">
                            <div class="w-16 h-16 rounded-full bg-slate-900 border border-slate-800 flex items-center justify-center text-slate-500 text-2xl mb-2">
                                <i class="fa-solid fa-user"></i>
                            </div>
                            <p class="text-xs text-slate-400">স্টাফ সংযোগের অপেক্ষায়...</p>
                        </div>
                        <div class="absolute bottom-3 left-3 bg-black/60 backdrop-blur-md px-3 py-1 rounded-lg text-xs font-medium text-slate-200 flex items-center gap-2">
                            <i class="fa-solid fa-user-clock text-yellow-400"></i> স্টাফ মেম্বার
                        </div>
                    </div>
                </div>

                <!-- Control Bar -->
                <div class="flex items-center justify-center gap-3 mt-4 pt-4 border-t border-slate-800">
                    <button onclick="toggleAudio()" id="micBtn" class="w-12 h-12 rounded-2xl bg-slate-800 hover:bg-slate-700 text-slate-200 flex items-center justify-center text-lg transition shadow-lg">
                        <i class="fa-solid fa-microphone" id="micIcon"></i>
                    </button>
                    <button onclick="toggleVideo()" id="camBtn" class="w-12 h-12 rounded-2xl bg-slate-800 hover:bg-slate-700 text-slate-200 flex items-center justify-center text-lg transition shadow-lg">
                        <i class="fa-solid fa-video" id="camIcon"></i>
                    </button>
                    <button onclick="toggleCall()" id="callBtn" class="px-6 h-12 rounded-2xl bg-emerald-600 hover:bg-emerald-500 text-white font-semibold flex items-center gap-2 transition shadow-lg shadow-emerald-900/40">
                        <i class="fa-solid fa-phone" id="callIcon"></i> <span id="callText">সিকিউর কল শুরু করুন</span>
                    </button>
                    <button onclick="shareScreen()" class="w-12 h-12 rounded-2xl bg-slate-800 hover:bg-slate-700 text-slate-200 flex items-center justify-center text-lg transition shadow-lg" title="স্ক্রিন শেয়ার">
                        <i class="fa-solid fa-desktop"></i>
                    </button>
                </div>

            </div>

            <!-- Encrypted Chat Box -->
            <div class="bg-slate-900 border border-slate-800 rounded-2xl p-4 shadow-xl flex flex-col h-48">
                <h3 class="text-xs font-semibold text-slate-400 mb-2 flex items-center gap-2">
                    <i class="fa-solid fa-comments text-emerald-400"></i> স্টাফ এনক্রিপ্টেড চ্যাট
                </h3>
                <div class="flex-1 bg-slate-950 border border-slate-800 rounded-xl p-3 overflow-y-auto space-y-2 text-xs" id="chatMessages">
                    <div class="text-slate-500 text-center italic">কথোপকথন এন্ড-টু-এন্ড এনক্রিপ্টেড। শুধু অনুমোদিত স্টাফরাই দেখতে পাবে।</div>
                </div>
                <div class="flex gap-2 mt-2">
                    <input type="text" id="chatInput" placeholder="মেসেজ লিখুন..." class="flex-1 bg-slate-950 border border-slate-800 rounded-xl px-3 py-2 text-xs focus:outline-none focus:border-emerald-500 text-slate-200" onkeypress="handleChatKey(event)">
                    <button onclick="sendChatMessage()" class="bg-emerald-600 hover:bg-emerald-500 text-white px-4 py-2 rounded-xl text-xs font-medium transition">
                        পাঠান
                    </button>
                </div>
            </div>

        </div>

    </main>

    <!-- JavaScript Interactive Logic -->
    <script>
        let isCallActive = false;
        let isMicMuted = false;
        let isCamOn = false;
        let localStream = null;

        function togglePassCode() {
            const input = document.getElementById('accessCode');
            const icon = document.getElementById('eyeIcon');
            if (input.type === 'password') {
                input.type = 'text';
                icon.classList.replace('fa-eye', 'fa-eye-slash');
            } else {
                input.type = 'password';
                icon.classList.replace('fa-eye-slash', 'fa-eye');
            }
        }

        function copyInviteLink() {
            const code = document.getElementById('accessCode').value;
            const inviteUrl = window.location.href.split('?')[0] + '?pass=' + code;
            navigator.clipboard.writeText(inviteUrl);
            alert('সিক্রেট ইনভাইট লিংক কপি করা হয়েছে! স্টাফদের কাছে পাঠিয়ে দিন।');
        }

        async function toggleCall() {
            const btn = document.getElementById('callBtn');
            const callIcon = document.getElementById('callIcon');
            const callText = document.getElementById('callText');
            const statusDot = document.getElementById('roomStatusDot');
            const statusText = document.getElementById('roomStatusText');

            if (!isCallActive) {
                try {
                    localStream = await navigator.mediaDevices.getUserMedia({ video: true, audio: true });
                    const videoElem = document.getElementById('webcamFeed');
                    videoElem.srcObject = localStream;
                    videoElem.classList.remove('hidden');
                    document.getElementById('videoPlaceholder').classList.add('hidden');
                    isCamOn = true;

                    isCallActive = true;
                    btn.classList.replace('bg-emerald-600', 'bg-rose-600');
                    btn.classList.replace('hover:bg-emerald-500', 'hover:bg-rose-500');
                    callIcon.classList.replace('fa-phone', 'fa-phone-slash');
                    callText.innerText = 'কল শেষ করুন';
                    statusDot.classList.replace('bg-rose-500', 'bg-emerald-500');
                    statusText.innerText = 'সিকিউর রুম সচল ও লাইভ';
                    statusText.className = 'text-sm font-medium text-emerald-400';
                } catch (err) {
                    alert('ক্যামেরা বা মাইক্রোফোন এক্সেস পাওয়া যায়নি। ব্রাউজার পারমিশন চেক করুন।');
                }
            } else {
                if (localStream) {
                    localStream.getTracks().forEach(track => track.stop());
                }
                document.getElementById('webcamFeed').classList.add('hidden');
                document.getElementById('videoPlaceholder').classList.remove('hidden');
                
                isCallActive = false;
                btn.classList.replace('bg-rose-600', 'bg-emerald-600');
                btn.classList.replace('hover:bg-rose-500', 'hover:bg-emerald-500');
                callIcon.classList.replace('fa-phone-slash', 'fa-phone');
                callText.innerText = 'সিকিউর কল শুরু করুন';
                statusDot.classList.replace('bg-emerald-500', 'bg-rose-500');
                statusText.innerText = 'সিকিউর রুম নিষ্ক্রিয়';
                statusText.className = 'text-sm font-medium text-slate-300';
            }
        }

        function toggleAudio() {
            if (!localStream) return;
            const audioTrack = localStream.getAudioTracks()[0];
            isMicMuted = !isMicMuted;
            audioTrack.enabled = !isMicMuted;
            const micBtn = document.getElementById('micBtn');
            const micIcon = document.getElementById('micIcon');
            if (isMicMuted) {
                micBtn.classList.add('bg-rose-500/20', 'text-rose-400', 'border', 'border-rose-500/30');
                micIcon.classList.replace('fa-microphone', 'fa-microphone-slash');
            } else {
                micBtn.classList.remove('bg-rose-500/20', 'text-rose-400', 'border', 'border-rose-500/30');
                micIcon.classList.replace('fa-microphone-slash', 'fa-microphone');
            }
        }

        function toggleVideo() {
            if (!localStream) return;
            const videoTrack = localStream.getVideoTracks()[0];
            isCamOn = !isCamOn;
            videoTrack.enabled = isCamOn;
            const camBtn = document.getElementById('camBtn');
            const camIcon = document.getElementById('camIcon');
            if (!isCamOn) {
                camBtn.classList.add('bg-rose-500/20', 'text-rose-400', 'border', 'border-rose-500/30');
                camIcon.classList.replace('fa-video', 'fa-video-slash');
                document.getElementById('webcamFeed').classList.add('hidden');
                document.getElementById('videoPlaceholder').classList.remove('hidden');
            } else {
                camBtn.classList.remove('bg-rose-500/20', 'text-rose-400', 'border', 'border-rose-500/30');
                camIcon.classList.replace('fa-video-slash', 'fa-video');
                document.getElementById('webcamFeed').classList.remove('hidden');
                document.getElementById('videoPlaceholder').classList.add('hidden');
            }
        }

        async function shareScreen() {
            try {
                const screenStream = await navigator.mediaDevices.getDisplayMedia({ video: true });
                const videoElem = document.getElementById('webcamFeed');
                videoElem.srcObject = screenStream;
                videoElem.classList.remove('hidden');
                document.getElementById('videoPlaceholder').classList.add('hidden');
                alert('স্ক্রিন শেয়ারিং শুরু হয়েছে।');
            } catch (err) {
                console.log('Screen share cancelled or failed.');
            }
        }

        function ringStaff(elem) {
            elem.innerText = 'কলিং...';
            elem.classList.replace('bg-slate-800', 'bg-emerald-600');
            setTimeout(() => {
                elem.innerText = 'যুক্ত আছেন';
                elem.classList.replace('bg-emerald-600', 'bg-teal-600');
            }, 2000);
        }

        function sendChatMessage() {
            const input = document.getElementById('chatInput');
            const text = input.value.trim();
            if(!text) return;
            const chatBox = document.getElementById('chatMessages');
            
            const msgDiv = document.createElement('div');
            msgDiv.className = 'bg-slate-900 p-2 rounded-xl border border-slate-800 text-slate-200';
            msgDiv.innerHTML = `<span class="text-emerald-400 font-bold">আপনি:</span> ${text}`;
            chatBox.appendChild(msgDiv);
            input.value = '';
            chatBox.scrollTop = chatBox.scrollHeight;
        }

        function handleChatKey(e) {
            if(e.key === 'Enter') sendChatMessage();
        }

        function lockSystem() {
            if(confirm('আপনি কি সিকিউর রুমটি লক আউট করতে চান?')) {
                location.reload();
            }
        }
    </script>
</body>
</html>
