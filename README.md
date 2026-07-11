<h2>WebUSB DFU Flasher</h2>
<p>Browser-based firmware flashing tool for STM32, AT32 and other DFU-compatible microcontrollers</p>

<h3>🚀 Quick Start</h3>
<h4>Connect</h4>
<ul>
 <li><b>Put your device in DFU mode:</b> Hold button and power on (or short BOOT0=HIGH  on PCB)</li>
 <li><b>Connect Device:</b> click "Connect to Device" and select DFU device from the dialog</li>
</ul>
<h4>Flash / Verify operation</h4>
<ul>
 <li><b>Load Firmware:</b> Select or drag & drop a firmware file (.bin, .dfu, .hex, .srec)</li>
 <li><b>Configure Options:</b>
 <ul>
  <li>For BIN files: specify flash start address (default: 0x08000000)</li>
  <li>Enable/disable erase before flashing (leave enabled in most cases)</li>
  <li>Enable/disable verification after flashing</li>
 </ul>
 <li><b>Flash:</b> Click "Flash" to start the programming process</li>
 <li><b>Verify:</b> Click "Verify Only" to check existing firmware without reprogramming</li>
</ul>
<h4>Upload operation</h4>
<ul>
 <li><b>Open Upload Panel:</b> Click "Upload from Device" button</li>
 <li><b>Select Range:</b>
  <ul>
   <li>Choose start sector from dropdown</li>
   <li>Choose end sector from dropdown</li>
   <li>Verify calculated size</li>
  </ul>
 </li>
 <li><b>Upload:</b> Click "Upload" to read data from device
  <ul>
   <li>Data read sector-by-sector</li>
   <li>Progress bar shows completion</li>
   <li>Data loaded as 'Device Dump' image with format 'bin'</li>
  </ul>
 </li>
 <li><b>Save Dump:</b> Click "Save as BIN" to export firmware
  <ul>
   <li>Choose file name and location</li>
   <li>File saved with device address and size in name</li>
  </ul>
 </li>
</ul>

<h3>📱 Supported Devices</h3>
<ul>
 <li><b>STM32</b> (VID: 0x0483) — Full DfuSe extension support</li>
 <li><b>AT32</b> (VID: 0x2E3C) — Artery microcontrollers</li>
 <li><b>GD32</b> (VID: 0x28E9) — GigaDevice</li>
 <li><b>ESP32-S2/S3</b> (VID: 0x303A) — Espressif</li>
</ul>

<h3>📁 File Formats</h3>
<ul>
 <li><b>.bin</b> — Raw binary (requires manual address)</li>
 <li><b>.dfu</b> — STMicroelectronics DfuSe format with CRC32</li>
 <li><b>.hex</b> — Intel HEX with extended addressing</li>
 <li><b>.srec/.s19/.s28/.s37</b> - Motorola S-Record</li>
</ul>

<h3>⚙️ Core Operations</h3>
<ul>
 <li><b>Flash (Write)</b>
  <ul>
   <li>Intelligent sector-based erasure with automatic size detection</li>
   <li>Progress tracking and multiple memory region support</li>
   <li>Duplicate sector prevention for overlapping blocks</li>
  </ul>
 </li>
 <li><b>Verify (Read & Compare)</b>
  <ul>
   <li>Post-flash byte-by-byte verification</li>
   <li>Detailed mismatch reporting with first error location</li>
  </ul>
 </li>
 <li><b>Upload from Device (Read Back)</b>
  <ul>
   <li>Extract firmware for backup or analysis</li>
   <li>Sector-based range selection from device memory map</li>
   <li>Save as BIN with custom path</li>
  </ul>
 </li>
</ul>

<h3>💻 System Requirements</h3>
<ul>
 <li>🌐 Browser
  <ul>
   <li>Chrome 86+ (recommended)</li>
   <li>Edge 86+</li>
   <li>Opera 72+ (</li>
   <li><i>Not supported: Firefox, Safari, Opera on Android</i></li>
  </ul>
 </li>
 <li>🪟 Operating System
  <ul>
   <li><b>Windows:</b> WinUSB driver required (install via <a href="https://zadig.akeo.ie/" target="_blank">Zadig</a>)</li>
   <li><b>Linux/macOS/Android:</b> No additional drivers needed</li>
  </ul>
 </li>
 <li>🛠️ Hardware
  <ul>
   <li>USB data cable (not charge-only)</li>
   <li>Device in DFU bootloader mode</li>
   <li>USB OTG adapter (for Android devices)</li>
  </ul>
 </li>
</ul>

<h3>🔒 Security & Privacy</h3>
<ul>
 <li>WebUSB requires explicit user permission for each connection</li>
 <li>No persistent storage of device data or firmware</li>
 <li>All operations in browser sandbox</li>
 <li>HTTPS required for production (localhost allowed for development)</li>
</ul>

<h3>⚠️ Important Notes</h3>
<ul>
 <li>Device must be in <b>DFU bootloader mode</b> (not application mode)<br>
     STM32: Set BOOT0=HIGH, then reset/power cycle</li>
 <li><b>Windows</b> users: Install <b>WinUSB</b> driver via <b>Zadig</b> before first use
  <ul>
   <li>Download Zadig from <a href="https://zadig.akeo.ie/" target="_blank">zadig.akeo.ie</a></li>
   <li>Run Zadig as Administrator</li>
   <li>Options → List All Devices</li>
   <li>Select your DFU device (e.g., <b>STM32 or AT32 BOOTLOADER</b>)</li>
   <li>Choose "WinUSB" from dropdown</li>
   <li>Click "Install Driver" or "Replace Driver"</li>
   <li>If you see "Access denied" error — WinUSB driver is not installed</li>
  </ul>
 </li>
</ul>
