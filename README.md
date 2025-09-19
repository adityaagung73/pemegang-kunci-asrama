<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Pemegang Kunci Asrama - Andalusia & Hijaz</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700&display=swap');
        body { font-family: 'Inter', sans-serif; }
        .card-hover { transition: all 0.3s ease; }
        .card-hover:hover { transform: translateY(-2px); box-shadow: 0 10px 25px rgba(0,0,0,0.1); }
        .fade-in { animation: fadeIn 0.5s ease-in; }
        @keyframes fadeIn { from { opacity: 0; transform: translateY(20px); } to { opacity: 1; transform: translateY(0); } }
        .status-dipinjam { background: linear-gradient(135deg, #fef3c7, #fbbf24); }
        .status-dikembalikan { background: linear-gradient(135deg, #d1fae5, #10b981); }
        .status-hilang { background: linear-gradient(135deg, #fee2e2, #ef4444); }
        .status-rusak { background: linear-gradient(135deg, #fed7aa, #f97316); }
    </style>
</head>
<body class="bg-gradient-to-br from-blue-50 to-indigo-100 min-h-screen">
    <!-- Welcome Screen -->
    <div id="welcomeScreen" class="min-h-screen flex items-center justify-center p-4">
        <div class="bg-white rounded-2xl shadow-2xl p-8 max-w-md w-full text-center fade-in">
            <div class="mb-6">
                <div class="w-20 h-20 bg-gradient-to-br from-blue-500 to-indigo-600 rounded-full mx-auto mb-4 flex items-center justify-center">
                    <svg class="w-10 h-10 text-white" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                        <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M15 7a2 2 0 012 2m4 0a6 6 0 01-7.743 5.743L11 17H9v2H7v2H4a1 1 0 01-1-1v-3.586l6.879-6.879A6 6 0 0119 9z"></path>
                    </svg>
                </div>
                <h1 class="text-2xl font-bold text-gray-800 mb-2">Pemegang Kunci Asrama</h1>
                <p class="text-lg text-blue-600 font-semibold">Andalusia & Hijaz</p>
            </div>
            <p class="text-gray-600 mb-8 leading-relaxed">Selamat datang di Aplikasi Pemegang Kunci Asrama. Kelola dan pantau penggunaan kunci dengan mudah dan efisien.</p>
            <button onclick="showHome()" class="w-full bg-gradient-to-r from-blue-500 to-indigo-600 text-white py-3 px-6 rounded-xl font-semibold hover:from-blue-600 hover:to-indigo-700 transition-all duration-300 transform hover:scale-105">
                Mulai
            </button>
        </div>
    </div>

    <!-- Main App -->
    <div id="mainApp" class="hidden min-h-screen">
        <!-- Header -->
        <header class="bg-white shadow-lg border-b border-gray-200">
            <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
                <div class="flex justify-between items-center py-4">
                    <div class="flex items-center space-x-3">
                        <div class="w-10 h-10 bg-gradient-to-br from-blue-500 to-indigo-600 rounded-lg flex items-center justify-center">
                            <svg class="w-6 h-6 text-white" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M15 7a2 2 0 012 2m4 0a6 6 0 01-7.743 5.743L11 17H9v2H7v2H4a1 1 0 01-1-1v-3.586l6.879-6.879A6 6 0 0119 9z"></path>
                            </svg>
                        </div>
                        <div>
                            <h1 class="text-xl font-bold text-gray-800">Pemegang Kunci Asrama</h1>
                            <p class="text-sm text-gray-500">Andalusia & Hijaz</p>
                        </div>
                    </div>
                    <button onclick="showHome()" class="text-blue-600 hover:text-blue-800 font-medium">
                        🏠 Home
                    </button>
                </div>
            </div>
        </header>

        <!-- Content Area -->
        <main class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 py-8">
            <!-- Home Menu -->
            <div id="homeMenu" class="fade-in">
                <h2 class="text-3xl font-bold text-gray-800 mb-8 text-center">Menu Utama</h2>
                <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-4 gap-6">
                    <div onclick="showActiveKeys()" class="bg-white rounded-xl shadow-lg p-6 cursor-pointer card-hover">
                        <div class="w-12 h-12 bg-green-100 rounded-lg flex items-center justify-center mb-4">
                            <svg class="w-6 h-6 text-green-600" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9 12l2 2 4-4m6 2a9 9 0 11-18 0 9 9 0 0118 0z"></path>
                            </svg>
                        </div>
                        <h3 class="text-lg font-semibold text-gray-800 mb-2">Daftar Pemegang Kunci</h3>
                        <p class="text-gray-600 text-sm">Lihat kunci yang sedang dipinjam</p>
                    </div>

                    <div onclick="showKeyTransfer()" class="bg-white rounded-xl shadow-lg p-6 cursor-pointer card-hover">
                        <div class="w-12 h-12 bg-blue-100 rounded-lg flex items-center justify-center mb-4">
                            <svg class="w-6 h-6 text-blue-600" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M8 7h12m0 0l-4-4m4 4l-4 4m0 6H4m0 0l4 4m-4-4l4-4"></path>
                            </svg>
                        </div>
                        <h3 class="text-lg font-semibold text-gray-800 mb-2">Serah Terima Kunci</h3>
                        <p class="text-gray-600 text-sm">Input pinjam & kembalikan kunci</p>
                    </div>

                    <div onclick="showKeyLog()" class="bg-white rounded-xl shadow-lg p-6 cursor-pointer card-hover">
                        <div class="w-12 h-12 bg-purple-100 rounded-lg flex items-center justify-center mb-4">
                            <svg class="w-6 h-6 text-purple-600" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9 19v-6a2 2 0 00-2-2H5a2 2 0 00-2 2v6a2 2 0 002 2h2a2 2 0 002-2zm0 0V9a2 2 0 012-2h2a2 2 0 012 2v10m-6 0a2 2 0 002 2h2a2 2 0 002-2m0 0V5a2 2 0 012-2h2a2 2 0 012 2v14a2 2 0 01-2 2h-2a2 2 0 01-2-2z"></path>
                            </svg>
                        </div>
                        <h3 class="text-lg font-semibold text-gray-800 mb-2">Log Kunci</h3>
                        <p class="text-gray-600 text-sm">Rekap semua transaksi kunci</p>
                    </div>

                    <div onclick="showMasterKeys()" class="bg-white rounded-xl shadow-lg p-6 cursor-pointer card-hover">
                        <div class="w-12 h-12 bg-orange-100 rounded-lg flex items-center justify-center mb-4">
                            <svg class="w-6 h-6 text-orange-600" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M19 11H5m14 0a2 2 0 012 2v6a2 2 0 01-2 2H5a2 2 0 01-2-2v-6a2 2 0 012-2m14 0V9a2 2 0 00-2-2M5 11V9a2 2 0 012-2m0 0V5a2 2 0 011-1h1m-1 1v1m0 0h1m-1 0v1"></path>
                            </svg>
                        </div>
                        <h3 class="text-lg font-semibold text-gray-800 mb-2">Master Jenis Kunci</h3>
                        <p class="text-gray-600 text-sm">Daftar referensi jenis kunci</p>
                    </div>
                </div>
            </div>

            <!-- Active Keys Section -->
            <div id="activeKeysSection" class="hidden fade-in">
                <div class="flex justify-between items-center mb-6">
                    <h2 class="text-2xl font-bold text-gray-800">Daftar Pemegang Kunci Aktif</h2>
                    <button onclick="showHome()" class="bg-gray-500 text-white px-4 py-2 rounded-lg hover:bg-gray-600 transition-colors">
                        Kembali
                    </button>
                </div>

                <!-- Filters -->
                <div class="bg-white rounded-xl shadow-lg p-6 mb-6">
                    <h3 class="text-lg font-semibold mb-4">Filter Cepat</h3>
                    <div class="grid grid-cols-1 md:grid-cols-3 gap-4">
                        <select id="filterGedung" onchange="filterActiveKeys()" class="border border-gray-300 rounded-lg px-3 py-2">
                            <option value="">Semua Gedung</option>
                            <option value="Andalusia">Andalusia</option>
                            <option value="Hijaz">Hijaz</option>
                        </select>
                        <select id="filterKategori" onchange="filterActiveKeys()" class="border border-gray-300 rounded-lg px-3 py-2">
                            <option value="">Semua Kategori</option>
                            <option value="Gerbang">Gerbang</option>
                            <option value="Kamar Musyrif">Kamar Musyrif</option>
                        </select>
                        <select id="filterLantai" onchange="filterActiveKeys()" class="border border-gray-300 rounded-lg px-3 py-2">
                            <option value="">Semua Lantai</option>
                            <option value="1">Lantai 1</option>
                            <option value="2">Lantai 2</option>
                            <option value="3">Lantai 3</option>
                            <option value="4">Lantai 4</option>
                        </select>
                    </div>
                </div>

                <!-- Active Keys List -->
                <div id="activeKeysList" class="space-y-4">
                    <!-- Will be populated by JavaScript -->
                </div>
            </div>

            <!-- Key Transfer Section -->
            <div id="keyTransferSection" class="hidden fade-in">
                <div class="flex justify-between items-center mb-6">
                    <h2 class="text-2xl font-bold text-gray-800">Serah Terima Kunci</h2>
                    <button onclick="showHome()" class="bg-gray-500 text-white px-4 py-2 rounded-lg hover:bg-gray-600 transition-colors">
                        Kembali
                    </button>
                </div>

                <div class="grid grid-cols-1 lg:grid-cols-2 gap-8">
                    <!-- Borrow Form -->
                    <div class="bg-white rounded-xl shadow-lg p-6">
                        <h3 class="text-xl font-semibold text-green-600 mb-6">📝 Form Pinjam Kunci</h3>
                        <form id="borrowForm" onsubmit="borrowKey(event)">
                            <div class="space-y-4">
                                <div class="grid grid-cols-2 gap-4">
                                    <div>
                                        <label class="block text-sm font-medium text-gray-700 mb-1">Tanggal</label>
                                        <input type="date" id="borrowDate" class="w-full border border-gray-300 rounded-lg px-3 py-2" readonly>
                                    </div>
                                    <div>
                                        <label class="block text-sm font-medium text-gray-700 mb-1">Jam</label>
                                        <input type="time" id="borrowTime" class="w-full border border-gray-300 rounded-lg px-3 py-2" readonly>
                                    </div>
                                </div>
                                <div>
                                    <label class="block text-sm font-medium text-gray-700 mb-1">Nama Pemegang *</label>
                                    <input type="text" id="borrowName" required class="w-full border border-gray-300 rounded-lg px-3 py-2" placeholder="Masukkan nama pemegang">
                                </div>
                                <div>
                                    <label class="block text-sm font-medium text-gray-700 mb-1">Jabatan/Status *</label>
                                    <select id="borrowPosition" required class="w-full border border-gray-300 rounded-lg px-3 py-2">
                                        <option value="">Pilih Jabatan</option>
                                        <option value="Kabid">Kabid</option>
                                        <option value="Kasie">Kasie</option>
                                        <option value="Staf">Staf</option>
                                        <option value="Musyrif">Musyrif</option>
                                        <option value="Lainnya">Lainnya</option>
                                    </select>
                                </div>
                                <div>
                                    <label class="block text-sm font-medium text-gray-700 mb-1">Jenis Kunci *</label>
                                    <select id="borrowKeyType" required onchange="toggleRoomNumber()" class="w-full border border-gray-300 rounded-lg px-3 py-2">
                                        <option value="">Pilih Jenis Kunci</option>
                                    </select>
                                </div>
                                <div id="roomNumberDiv" class="hidden">
                                    <label class="block text-sm font-medium text-gray-700 mb-1">Nomor Kamar *</label>
                                    <input type="text" id="borrowRoomNumber" class="w-full border border-gray-300 rounded-lg px-3 py-2" placeholder="Contoh: 101, 201A">
                                </div>
                                <div>
                                    <label class="block text-sm font-medium text-gray-700 mb-1">Keperluan *</label>
                                    <input type="text" id="borrowPurpose" required class="w-full border border-gray-300 rounded-lg px-3 py-2" placeholder="Contoh: patroli, perbaikan, inspeksi">
                                </div>
                                <div>
                                    <label class="block text-sm font-medium text-gray-700 mb-1">PIC Penyerahan *</label>
                                    <input type="text" id="borrowPIC" required class="w-full border border-gray-300 rounded-lg px-3 py-2" placeholder="Nama petugas yang menyerahkan">
                                </div>
                                <div>
                                    <label class="block text-sm font-medium text-gray-700 mb-1">Catatan</label>
                                    <textarea id="borrowNotes" class="w-full border border-gray-300 rounded-lg px-3 py-2" rows="2" placeholder="Catatan tambahan (opsional)"></textarea>
                                </div>
                            </div>
                            <button type="submit" class="w-full mt-6 bg-green-500 text-white py-3 rounded-lg font-semibold hover:bg-green-600 transition-colors">
                                📤 Kirim Data Pinjam
                            </button>
                        </form>
                    </div>

                    <!-- Return Form -->
                    <div class="bg-white rounded-xl shadow-lg p-6">
                        <h3 class="text-xl font-semibold text-blue-600 mb-6">🔄 Form Pengembalian Kunci</h3>
                        <form id="returnForm" onsubmit="returnKey(event)">
                            <div class="space-y-4">
                                <div class="grid grid-cols-2 gap-4">
                                    <div>
                                        <label class="block text-sm font-medium text-gray-700 mb-1">Tanggal</label>
                                        <input type="date" id="returnDate" class="w-full border border-gray-300 rounded-lg px-3 py-2" readonly>
                                    </div>
                                    <div>
                                        <label class="block text-sm font-medium text-gray-700 mb-1">Jam</label>
                                        <input type="time" id="returnTime" class="w-full border border-gray-300 rounded-lg px-3 py-2" readonly>
                                    </div>
                                </div>
                                <div>
                                    <label class="block text-sm font-medium text-gray-700 mb-1">Pilih Transaksi Aktif *</label>
                                    <select id="returnTransaction" required onchange="fillReturnDetails()" class="w-full border border-gray-300 rounded-lg px-3 py-2">
                                        <option value="">Pilih transaksi yang akan dikembalikan</option>
                                    </select>
                                </div>
                                <div id="returnDetails" class="hidden bg-gray-50 p-4 rounded-lg">
                                    <h4 class="font-medium text-gray-700 mb-2">Detail Peminjaman:</h4>
                                    <div id="returnDetailsContent"></div>
                                </div>
                                <div>
                                    <label class="block text-sm font-medium text-gray-700 mb-1">Kondisi Saat Kembali *</label>
                                    <select id="returnCondition" required class="w-full border border-gray-300 rounded-lg px-3 py-2">
                                        <option value="">Pilih Kondisi</option>
                                        <option value="Baik">Baik</option>
                                        <option value="Rusak">Rusak</option>
                                        <option value="Hilang">Hilang</option>
                                    </select>
                                </div>
                                <div>
                                    <label class="block text-sm font-medium text-gray-700 mb-1">PIC Penerima *</label>
                                    <input type="text" id="returnPIC" required class="w-full border border-gray-300 rounded-lg px-3 py-2" placeholder="Nama petugas yang menerima">
                                </div>
                                <div>
                                    <label class="block text-sm font-medium text-gray-700 mb-1">Catatan</label>
                                    <textarea id="returnNotes" class="w-full border border-gray-300 rounded-lg px-3 py-2" rows="2" placeholder="Catatan pengembalian (opsional)"></textarea>
                                </div>
                            </div>
                            <button type="submit" class="w-full mt-6 bg-blue-500 text-white py-3 rounded-lg font-semibold hover:bg-blue-600 transition-colors">
                                🔄 Kirim Pengembalian
                            </button>
                        </form>
                    </div>
                </div>
            </div>

            <!-- Key Log Section -->
            <div id="keyLogSection" class="hidden fade-in">
                <div class="flex justify-between items-center mb-6">
                    <h2 class="text-2xl font-bold text-gray-800">Log Kunci (Rekap Transaksi)</h2>
                    <button onclick="showHome()" class="bg-gray-500 text-white px-4 py-2 rounded-lg hover:bg-gray-600 transition-colors">
                        Kembali
                    </button>
                </div>

                <!-- Log Filters -->
                <div class="bg-white rounded-xl shadow-lg p-6 mb-6">
                    <h3 class="text-lg font-semibold mb-4">Filter Log</h3>
                    <div class="grid grid-cols-1 md:grid-cols-4 gap-4">
                        <div>
                            <label class="block text-sm font-medium text-gray-700 mb-1">Dari Tanggal</label>
                            <input type="date" id="logDateFrom" onchange="filterLog()" class="w-full border border-gray-300 rounded-lg px-3 py-2">
                        </div>
                        <div>
                            <label class="block text-sm font-medium text-gray-700 mb-1">Sampai Tanggal</label>
                            <input type="date" id="logDateTo" onchange="filterLog()" class="w-full border border-gray-300 rounded-lg px-3 py-2">
                        </div>
                        <select id="logGedung" onchange="filterLog()" class="border border-gray-300 rounded-lg px-3 py-2">
                            <option value="">Semua Gedung</option>
                            <option value="Andalusia">Andalusia</option>
                            <option value="Hijaz">Hijaz</option>
                        </select>
                        <select id="logStatus" onchange="filterLog()" class="border border-gray-300 rounded-lg px-3 py-2">
                            <option value="">Semua Status</option>
                            <option value="Dipinjam">Dipinjam</option>
                            <option value="Dikembalikan">Dikembalikan</option>
                            <option value="Hilang">Hilang</option>
                            <option value="Rusak">Rusak</option>
                        </select>
                    </div>
                </div>

                <!-- Log Table -->
                <div class="bg-white rounded-xl shadow-lg overflow-hidden">
                    <div class="overflow-x-auto">
                        <table class="w-full">
                            <thead class="bg-gray-50">
                                <tr>
                                    <th class="px-4 py-3 text-left text-xs font-medium text-gray-500 uppercase">Tanggal/Jam</th>
                                    <th class="px-4 py-3 text-left text-xs font-medium text-gray-500 uppercase">Nama</th>
                                    <th class="px-4 py-3 text-left text-xs font-medium text-gray-500 uppercase">Jabatan</th>
                                    <th class="px-4 py-3 text-left text-xs font-medium text-gray-500 uppercase">Jenis Kunci</th>
                                    <th class="px-4 py-3 text-left text-xs font-medium text-gray-500 uppercase">Keperluan</th>
                                    <th class="px-4 py-3 text-left text-xs font-medium text-gray-500 uppercase">Status</th>
                                    <th class="px-4 py-3 text-left text-xs font-medium text-gray-500 uppercase">PIC</th>
                                </tr>
                            </thead>
                            <tbody id="logTableBody" class="divide-y divide-gray-200">
                                <!-- Will be populated by JavaScript -->
                            </tbody>
                        </table>
                    </div>
                </div>
            </div>

            <!-- Master Keys Section -->
            <div id="masterKeysSection" class="hidden fade-in">
                <div class="flex justify-between items-center mb-6">
                    <h2 class="text-2xl font-bold text-gray-800">Master Jenis Kunci</h2>
                    <button onclick="showHome()" class="bg-gray-500 text-white px-4 py-2 rounded-lg hover:bg-gray-600 transition-colors">
                        Kembali
                    </button>
                </div>

                <div class="bg-white rounded-xl shadow-lg overflow-hidden">
                    <div class="overflow-x-auto">
                        <table class="w-full">
                            <thead class="bg-gray-50">
                                <tr>
                                    <th class="px-4 py-3 text-left text-xs font-medium text-gray-500 uppercase">ID</th>
                                    <th class="px-4 py-3 text-left text-xs font-medium text-gray-500 uppercase">Nama Jenis Kunci</th>
                                    <th class="px-4 py-3 text-left text-xs font-medium text-gray-500 uppercase">Gedung</th>
                                    <th class="px-4 py-3 text-left text-xs font-medium text-gray-500 uppercase">Lantai</th>
                                    <th class="px-4 py-3 text-left text-xs font-medium text-gray-500 uppercase">Keterangan</th>
                                </tr>
                            </thead>
                            <tbody id="masterKeysTableBody" class="divide-y divide-gray-200">
                                <!-- Will be populated by JavaScript -->
                            </tbody>
                        </table>
                    </div>
                </div>
            </div>
        </main>
    </div>

    <!-- Notification -->
    <div id="notification" class="fixed top-4 right-4 z-50 hidden">
        <div class="bg-white border-l-4 border-green-500 rounded-lg shadow-lg p-4 max-w-sm">
            <div class="flex items-center">
                <div class="flex-shrink-0">
                    <svg class="w-5 h-5 text-green-500" fill="currentColor" viewBox="0 0 20 20">
                        <path fill-rule="evenodd" d="M10 18a8 8 0 100-16 8 8 0 000 16zm3.707-9.293a1 1 0 00-1.414-1.414L9 10.586 7.707 9.293a1 1 0 00-1.414 1.414l2 2a1 1 0 001.414 0l4-4z" clip-rule="evenodd"></path>
                    </svg>
                </div>
                <div class="ml-3">
                    <p id="notificationText" class="text-sm font-medium text-gray-900"></p>
                </div>
            </div>
        </div>
    </div>

    <script>
        // Data Storage
        let keyTransactions = JSON.parse(localStorage.getItem('keyTransactions')) || [];
        let transactionCounter = parseInt(localStorage.getItem('transactionCounter')) || 1;

        // Master Key Types Data
        const masterKeyTypes = [
            { id: 'GTA', name: 'Gerbang Asrama Andalusia', gedung: 'Andalusia', lantai: '-', keterangan: 'Gerbang utama asrama Andalusia' },
            { id: 'GTH', name: 'Gerbang Asrama Hijaz', gedung: 'Hijaz', lantai: '-', keterangan: 'Gerbang utama asrama Hijaz' },
            { id: 'KMH1', name: 'Kamar Musyrif – Gedung Hijaz Lantai 1', gedung: 'Hijaz', lantai: '1', keterangan: 'Kamar musyrif lantai 1' },
            { id: 'KMH2', name: 'Kamar Musyrif – Gedung Hijaz Lantai 2', gedung: 'Hijaz', lantai: '2', keterangan: 'Kamar musyrif lantai 2' },
            { id: 'KMH3', name: 'Kamar Musyrif – Gedung Hijaz Lantai 3', gedung: 'Hijaz', lantai: '3', keterangan: 'Kamar musyrif lantai 3' },
            { id: 'KMH4', name: 'Kamar Musyrif – Gedung Hijaz Lantai 4', gedung: 'Hijaz', lantai: '4', keterangan: 'Kamar musyrif lantai 4' },
            { id: 'KMA1', name: 'Kamar Musyrif – Gedung Andalusia Lantai 1', gedung: 'Andalusia', lantai: '1', keterangan: 'Kamar musyrif lantai 1' },
            { id: 'KMA2', name: 'Kamar Musyrif – Gedung Andalusia Lantai 2', gedung: 'Andalusia', lantai: '2', keterangan: 'Kamar musyrif lantai 2' },
            { id: 'KMA3', name: 'Kamar Musyrif – Gedung Andalusia Lantai 3', gedung: 'Andalusia', lantai: '3', keterangan: 'Kamar musyrif lantai 3' },
            { id: 'KMA4', name: 'Kamar Musyrif – Gedung Andalusia Lantai 4', gedung: 'Andalusia', lantai: '4', keterangan: 'Kamar musyrif lantai 4' }
        ];

        // Initialize app
        function initApp() {
            setCurrentDateTime();
            populateKeyTypeDropdown();
            populateMasterKeysTable();
            updateActiveKeysList();
            updateKeyLog();
            updateReturnTransactionDropdown();
            
            // Set current date/time every minute
            setInterval(setCurrentDateTime, 60000);
        }

        // Set current date and time
        function setCurrentDateTime() {
            const now = new Date();
            const date = now.toISOString().split('T')[0];
            const time = now.toTimeString().split(' ')[0].substring(0, 5);
            
            document.getElementById('borrowDate').value = date;
            document.getElementById('borrowTime').value = time;
            document.getElementById('returnDate').value = date;
            document.getElementById('returnTime').value = time;
        }

        // Navigation functions
        function showHome() {
            hideAllSections();
            document.getElementById('welcomeScreen').classList.add('hidden');
            document.getElementById('mainApp').classList.remove('hidden');
            document.getElementById('homeMenu').classList.remove('hidden');
        }

        function showActiveKeys() {
            hideAllSections();
            document.getElementById('activeKeysSection').classList.remove('hidden');
            updateActiveKeysList();
        }

        function showKeyTransfer() {
            hideAllSections();
            document.getElementById('keyTransferSection').classList.remove('hidden');
            updateReturnTransactionDropdown();
        }

        function showKeyLog() {
            hideAllSections();
            document.getElementById('keyLogSection').classList.remove('hidden');
            updateKeyLog();
        }

        function showMasterKeys() {
            hideAllSections();
            document.getElementById('masterKeysSection').classList.remove('hidden');
        }

        function hideAllSections() {
            const sections = ['homeMenu', 'activeKeysSection', 'keyTransferSection', 'keyLogSection', 'masterKeysSection'];
            sections.forEach(section => {
                document.getElementById(section).classList.add('hidden');
            });
        }

        // Populate key type dropdown
        function populateKeyTypeDropdown() {
            const dropdown = document.getElementById('borrowKeyType');
            dropdown.innerHTML = '<option value="">Pilih Jenis Kunci</option>';
            
            masterKeyTypes.forEach(keyType => {
                const option = document.createElement('option');
                option.value = keyType.id;
                option.textContent = keyType.name;
                option.dataset.gedung = keyType.gedung;
                option.dataset.lantai = keyType.lantai;
                dropdown.appendChild(option);
            });
        }

        // Toggle room number field
        function toggleRoomNumber() {
            const keyTypeSelect = document.getElementById('borrowKeyType');
            const roomNumberDiv = document.getElementById('roomNumberDiv');
            const roomNumberInput = document.getElementById('borrowRoomNumber');
            
            const selectedOption = keyTypeSelect.options[keyTypeSelect.selectedIndex];
            const isMusyrifRoom = selectedOption.text.includes('Kamar Musyrif');
            
            if (isMusyrifRoom) {
                roomNumberDiv.classList.remove('hidden');
                roomNumberInput.required = true;
            } else {
                roomNumberDiv.classList.add('hidden');
                roomNumberInput.required = false;
                roomNumberInput.value = '';
            }
        }

        // Check if key is available
        function isKeyAvailable(keyTypeId, roomNumber = '') {
            return !keyTransactions.some(transaction => 
                transaction.jenisKunci === keyTypeId && 
                transaction.nomorKamar === roomNumber && 
                transaction.status === 'Dipinjam'
            );
        }

        // Borrow key function
        function borrowKey(event) {
            event.preventDefault();
            
            const keyTypeId = document.getElementById('borrowKeyType').value;
            const roomNumber = document.getElementById('borrowRoomNumber').value;
            
            // Check availability
            if (!isKeyAvailable(keyTypeId, roomNumber)) {
                showNotification('Kunci sedang dipinjam oleh orang lain!', 'error');
                return;
            }
            
            const keyType = masterKeyTypes.find(k => k.id === keyTypeId);
            
            const transaction = {
                id: 'TXN' + String(transactionCounter).padStart(6, '0'),
                tanggal: document.getElementById('borrowDate').value,
                jam: document.getElementById('borrowTime').value,
                namaPemegang: document.getElementById('borrowName').value,
                jabatan: document.getElementById('borrowPosition').value,
                jenisKunci: keyTypeId,
                jenisKunciNama: keyType.name,
                gedung: keyType.gedung,
                lantai: keyType.lantai,
                nomorKamar: roomNumber,
                keperluan: document.getElementById('borrowPurpose').value,
                status: 'Dipinjam',
                picPenyerahan: document.getElementById('borrowPIC').value,
                catatan: document.getElementById('borrowNotes').value,
                type: 'borrow'
            };
            
            // Send to Google Sheets
            sendToGoogleSheets(transaction);
            
            keyTransactions.push(transaction);
            transactionCounter++;
            
            saveData();
            resetBorrowForm();
            updateActiveKeysList();
            updateKeyLog();
            updateReturnTransactionDropdown();
            
            showNotification('Kunci berhasil dipinjamkan dan data terkirim ke spreadsheet!');
        }

        // Send data to Google Sheets
        function sendToGoogleSheets(data) {
            const scriptURL = 'https://script.google.com/macros/s/AKfycbwPsR_rpYSrxoP2eqQ1aCB9StO7bXcNNw4H9aqlLvXuxmRpx--3dYLW399jJZOCVZ5N/exec';
            
            const formData = new FormData();
            formData.append('transactionId', data.id);
            formData.append('tanggal', data.tanggal);
            formData.append('jam', data.jam);
            formData.append('namaPemegang', data.namaPemegang);
            formData.append('jabatan', data.jabatan);
            formData.append('jenisKunci', data.jenisKunci);
            formData.append('jenisKunciNama', data.jenisKunciNama);
            formData.append('gedung', data.gedung);
            formData.append('lantai', data.lantai);
            formData.append('nomorKamar', data.nomorKamar || '');
            formData.append('keperluan', data.keperluan);
            formData.append('status', data.status);
            formData.append('picPenyerahan', data.picPenyerahan);
            formData.append('catatan', data.catatan || '');
            formData.append('type', data.type);
            
            fetch(scriptURL, {
                method: 'POST',
                body: formData
            })
            .then(response => response.text())
            .then(result => {
                console.log('Data berhasil dikirim ke Google Sheets:', result);
            })
            .catch(error => {
                console.error('Error mengirim data ke Google Sheets:', error);
                showNotification('Data tersimpan lokal, tapi gagal kirim ke spreadsheet', 'error');
            });
        }

        // Return key function
        function returnKey(event) {
            event.preventDefault();
            
            const transactionId = document.getElementById('returnTransaction').value;
            const condition = document.getElementById('returnCondition').value;
            
            // Find original transaction
            const originalTransaction = keyTransactions.find(t => t.id === transactionId);
            if (!originalTransaction) {
                showNotification('Transaksi tidak ditemukan!', 'error');
                return;
            }
            
            // Update original transaction status
            let newStatus = 'Dikembalikan';
            if (condition === 'Hilang') newStatus = 'Hilang';
            if (condition === 'Rusak') newStatus = 'Rusak';
            
            originalTransaction.status = newStatus;
            
            // Create return transaction record
            const returnTransaction = {
                id: 'TXN' + String(transactionCounter).padStart(6, '0'),
                tanggal: document.getElementById('returnDate').value,
                jam: document.getElementById('returnTime').value,
                namaPemegang: originalTransaction.namaPemegang,
                jabatan: originalTransaction.jabatan,
                jenisKunci: originalTransaction.jenisKunci,
                jenisKunciNama: originalTransaction.jenisKunciNama,
                gedung: originalTransaction.gedung,
                lantai: originalTransaction.lantai,
                nomorKamar: originalTransaction.nomorKamar,
                keperluan: 'Pengembalian - ' + originalTransaction.keperluan,
                status: newStatus,
                picPenyerahan: document.getElementById('returnPIC').value,
                catatan: document.getElementById('returnNotes').value,
                kondisi: condition,
                originalTransactionId: transactionId,
                type: 'return'
            };
            
            keyTransactions.push(returnTransaction);
            transactionCounter++;
            
            saveData();
            resetReturnForm();
            updateActiveKeysList();
            updateKeyLog();
            updateReturnTransactionDropdown();
            
            showNotification('Kunci berhasil dikembalikan!');
        }

        // Fill return transaction dropdown
        function updateReturnTransactionDropdown() {
            const dropdown = document.getElementById('returnTransaction');
            dropdown.innerHTML = '<option value="">Pilih transaksi yang akan dikembalikan</option>';
            
            const activeTransactions = keyTransactions.filter(t => t.status === 'Dipinjam' && t.type === 'borrow');
            
            activeTransactions.forEach(transaction => {
                const option = document.createElement('option');
                option.value = transaction.id;
                option.textContent = `${transaction.namaPemegang} - ${transaction.jenisKunciNama} ${transaction.nomorKamar ? '(Kamar ' + transaction.nomorKamar + ')' : ''}`;
                dropdown.appendChild(option);
            });
        }

        // Fill return details
        function fillReturnDetails() {
            const transactionId = document.getElementById('returnTransaction').value;
            const detailsDiv = document.getElementById('returnDetails');
            const contentDiv = document.getElementById('returnDetailsContent');
            
            if (!transactionId) {
                detailsDiv.classList.add('hidden');
                return;
            }
            
            const transaction = keyTransactions.find(t => t.id === transactionId);
            if (transaction) {
                contentDiv.innerHTML = `
                    <p><strong>Nama:</strong> ${transaction.namaPemegang}</p>
                    <p><strong>Jabatan:</strong> ${transaction.jabatan}</p>
                    <p><strong>Jenis Kunci:</strong> ${transaction.jenisKunciNama}</p>
                    ${transaction.nomorKamar ? `<p><strong>Nomor Kamar:</strong> ${transaction.nomorKamar}</p>` : ''}
                    <p><strong>Keperluan:</strong> ${transaction.keperluan}</p>
                    <p><strong>Waktu Pinjam:</strong> ${transaction.tanggal} ${transaction.jam}</p>
                    <p><strong>PIC Penyerahan:</strong> ${transaction.picPenyerahan}</p>
                `;
                detailsDiv.classList.remove('hidden');
            }
        }

        // Update active keys list
        function updateActiveKeysList() {
            const container = document.getElementById('activeKeysList');
            const activeTransactions = keyTransactions.filter(t => t.status === 'Dipinjam' && t.type === 'borrow');
            
            if (activeTransactions.length === 0) {
                container.innerHTML = `
                    <div class="bg-white rounded-xl shadow-lg p-8 text-center">
                        <div class="w-16 h-16 bg-gray-100 rounded-full mx-auto mb-4 flex items-center justify-center">
                            <svg class="w-8 h-8 text-gray-400" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M15 7a2 2 0 012 2m4 0a6 6 0 01-7.743 5.743L11 17H9v2H7v2H4a1 1 0 01-1-1v-3.586l6.879-6.879A6 6 0 0119 9z"></path>
                            </svg>
                        </div>
                        <h3 class="text-lg font-medium text-gray-900 mb-2">Tidak Ada Kunci yang Dipinjam</h3>
                        <p class="text-gray-500">Semua kunci sudah dikembalikan</p>
                    </div>
                `;
                return;
            }
            
            container.innerHTML = activeTransactions.map(transaction => `
                <div class="bg-white rounded-xl shadow-lg p-6 card-hover">
                    <div class="flex justify-between items-start mb-4">
                        <div class="flex-1">
                            <h3 class="text-lg font-semibold text-gray-800">${transaction.namaPemegang}</h3>
                            <p class="text-sm text-gray-600">${transaction.jabatan}</p>
                        </div>
                        <span class="status-dipinjam text-xs font-medium px-3 py-1 rounded-full text-yellow-800">
                            ${transaction.status}
                        </span>
                    </div>
                    <div class="grid grid-cols-1 md:grid-cols-2 gap-4 mb-4">
                        <div>
                            <p class="text-sm text-gray-500">Jenis Kunci</p>
                            <p class="font-medium">${transaction.jenisKunciNama}</p>
                            ${transaction.nomorKamar ? `<p class="text-sm text-blue-600">Kamar ${transaction.nomorKamar}</p>` : ''}
                        </div>
                        <div>
                            <p class="text-sm text-gray-500">Waktu Ambil</p>
                            <p class="font-medium">${transaction.tanggal} ${transaction.jam}</p>
                        </div>
                    </div>
                    <div class="mb-4">
                        <p class="text-sm text-gray-500">Keperluan</p>
                        <p class="font-medium">${transaction.keperluan}</p>
                    </div>
                    <div class="flex justify-between items-center">
                        <div>
                            <p class="text-sm text-gray-500">PIC Penyerahan</p>
                            <p class="font-medium">${transaction.picPenyerahan}</p>
                        </div>
                        <button onclick="quickReturn('${transaction.id}')" class="bg-blue-500 text-white px-4 py-2 rounded-lg hover:bg-blue-600 transition-colors text-sm">
                            🔄 Kembalikan
                        </button>
                    </div>
                </div>
            `).join('');
        }

        // Quick return function
        function quickReturn(transactionId) {
            showKeyTransfer();
            document.getElementById('returnTransaction').value = transactionId;
            fillReturnDetails();
        }

        // Filter active keys
        function filterActiveKeys() {
            const gedungFilter = document.getElementById('filterGedung').value;
            const kategoriFilter = document.getElementById('filterKategori').value;
            const lantaiFilter = document.getElementById('filterLantai').value;
            
            const container = document.getElementById('activeKeysList');
            const cards = container.querySelectorAll('.bg-white');
            
            cards.forEach(card => {
                const transaction = keyTransactions.find(t => 
                    card.textContent.includes(t.namaPemegang) && 
                    card.textContent.includes(t.jenisKunciNama)
                );
                
                if (!transaction) return;
                
                let show = true;
                
                if (gedungFilter && transaction.gedung !== gedungFilter) show = false;
                if (kategoriFilter) {
                    const isGerbang = transaction.jenisKunciNama.includes('Gerbang');
                    const isKamarMusyrif = transaction.jenisKunciNama.includes('Kamar Musyrif');
                    
                    if (kategoriFilter === 'Gerbang' && !isGerbang) show = false;
                    if (kategoriFilter === 'Kamar Musyrif' && !isKamarMusyrif) show = false;
                }
                if (lantaiFilter && transaction.lantai !== lantaiFilter) show = false;
                
                card.style.display = show ? 'block' : 'none';
            });
        }

        // Update key log
        function updateKeyLog() {
            const tbody = document.getElementById('logTableBody');
            const sortedTransactions = [...keyTransactions].sort((a, b) => {
                const dateA = new Date(a.tanggal + ' ' + a.jam);
                const dateB = new Date(b.tanggal + ' ' + b.jam);
                return dateB - dateA;
            });
            
            tbody.innerHTML = sortedTransactions.map(transaction => `
                <tr class="hover:bg-gray-50">
                    <td class="px-4 py-3 text-sm">
                        <div>${transaction.tanggal}</div>
                        <div class="text-gray-500">${transaction.jam}</div>
                    </td>
                    <td class="px-4 py-3 text-sm font-medium">${transaction.namaPemegang}</td>
                    <td class="px-4 py-3 text-sm">${transaction.jabatan}</td>
                    <td class="px-4 py-3 text-sm">
                        <div>${transaction.jenisKunciNama}</div>
                        ${transaction.nomorKamar ? `<div class="text-blue-600 text-xs">Kamar ${transaction.nomorKamar}</div>` : ''}
                    </td>
                    <td class="px-4 py-3 text-sm">${transaction.keperluan}</td>
                    <td class="px-4 py-3">
                        <span class="status-${transaction.status.toLowerCase()} text-xs font-medium px-2 py-1 rounded-full">
                            ${transaction.status}
                        </span>
                    </td>
                    <td class="px-4 py-3 text-sm">${transaction.picPenyerahan}</td>
                </tr>
            `).join('');
        }

        // Filter log
        function filterLog() {
            const dateFrom = document.getElementById('logDateFrom').value;
            const dateTo = document.getElementById('logDateTo').value;
            const gedungFilter = document.getElementById('logGedung').value;
            const statusFilter = document.getElementById('logStatus').value;
            
            const tbody = document.getElementById('logTableBody');
            const rows = tbody.querySelectorAll('tr');
            
            rows.forEach(row => {
                const transaction = keyTransactions.find(t => 
                    row.textContent.includes(t.namaPemegang) && 
                    row.textContent.includes(t.jenisKunciNama)
                );
                
                if (!transaction) return;
                
                let show = true;
                
                if (dateFrom && transaction.tanggal < dateFrom) show = false;
                if (dateTo && transaction.tanggal > dateTo) show = false;
                if (gedungFilter && transaction.gedung !== gedungFilter) show = false;
                if (statusFilter && transaction.status !== statusFilter) show = false;
                
                row.style.display = show ? '' : 'none';
            });
        }

        // Populate master keys table
        function populateMasterKeysTable() {
            const tbody = document.getElementById('masterKeysTableBody');
            tbody.innerHTML = masterKeyTypes.map(keyType => `
                <tr class="hover:bg-gray-50">
                    <td class="px-4 py-3 text-sm font-medium">${keyType.id}</td>
                    <td class="px-4 py-3 text-sm">${keyType.name}</td>
                    <td class="px-4 py-3 text-sm">
                        <span class="inline-flex items-center px-2.5 py-0.5 rounded-full text-xs font-medium ${keyType.gedung === 'Andalusia' ? 'bg-blue-100 text-blue-800' : 'bg-green-100 text-green-800'}">
                            ${keyType.gedung}
                        </span>
                    </td>
                    <td class="px-4 py-3 text-sm">${keyType.lantai}</td>
                    <td class="px-4 py-3 text-sm text-gray-600">${keyType.keterangan}</td>
                </tr>
            `).join('');
        }

        // Reset forms
        function resetBorrowForm() {
            document.getElementById('borrowForm').reset();
            document.getElementById('roomNumberDiv').classList.add('hidden');
            setCurrentDateTime();
        }

        function resetReturnForm() {
            document.getElementById('returnForm').reset();
            document.getElementById('returnDetails').classList.add('hidden');
            setCurrentDateTime();
        }

        // Save data to localStorage
        function saveData() {
            localStorage.setItem('keyTransactions', JSON.stringify(keyTransactions));
            localStorage.setItem('transactionCounter', transactionCounter.toString());
        }

        // Show notification
        function showNotification(message, type = 'success') {
            const notification = document.getElementById('notification');
            const text = document.getElementById('notificationText');
            
            text.textContent = message;
            
            if (type === 'error') {
                notification.querySelector('.border-green-500').classList.remove('border-green-500');
                notification.querySelector('.border-green-500, .border-red-500').classList.add('border-red-500');
                notification.querySelector('.text-green-500').classList.remove('text-green-500');
                notification.querySelector('.text-green-500, .text-red-500').classList.add('text-red-500');
            }
            
            notification.classList.remove('hidden');
            
            setTimeout(() => {
                notification.classList.add('hidden');
            }, 3000);
        }

        // Initialize app when page loads
        document.addEventListener('DOMContentLoaded', initApp);
    </script>
<script>(function(){function c(){var b=a.contentDocument||a.contentWindow.document;if(b){var d=b.createElement('script');d.innerHTML="window.__CF$cv$params={r:'97ad499cd58fce19',t:'MTc1NzE1NDU5MC4wMDAwMDA='};var a=document.createElement('script');a.nonce='';a.src='/cdn-cgi/challenge-platform/scripts/jsd/main.js';document.getElementsByTagName('head')[0].appendChild(a);";b.getElementsByTagName('head')[0].appendChild(d)}}if(document.body){var a=document.createElement('iframe');a.height=1;a.width=1;a.style.position='absolute';a.style.top=0;a.style.left=0;a.style.border='none';a.style.visibility='hidden';document.body.appendChild(a);if('loading'!==document.readyState)c();else if(window.addEventListener)document.addEventListener('DOMContentLoaded',c);else{var e=document.onreadystatechange||function(){};document.onreadystatechange=function(b){e(b);'loading'!==document.readyState&&(document.onreadystatechange=e,c())}}}})();</script></body>
</html>
