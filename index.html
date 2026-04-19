<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Auth Code Generator</title>
  <style>
    body { font-family: Arial, sans-serif; max-width: 400px; margin: 60px auto; padding: 20px; }
    h2 { text-align: center; }
    label { display: block; margin-top: 15px; font-weight: bold; }
    input, select { width: 100%; padding: 8px; margin-top: 5px; box-sizing: border-box; font-size: 15px; }
    button { width: 100%; margin-top: 20px; padding: 10px; background: #2c7be5; color: white; border: none; font-size: 16px; cursor: pointer; border-radius: 4px; }
    button:hover { background: #1a5dc8; }
    #result { margin-top: 20px; text-align: center; font-size: 22px; font-weight: bold; letter-spacing: 3px; color: #2c7be5; }
  </style>
</head>
<body>

<h2>BaolynBMS Auth Code Generator</h2>

<label>Device Code</label>
<input type="text" id="deviceCode" placeholder="e.g. VDWSIT4B3" />

<label>Duration</label>
<input type="number" id="duration" value="1" min="1" disabled/>

<label>Type</label>
<select id="type">
  <option value="1">Simple User</option>
  <option selected value="3">Admin</option>
</select>

<button onclick="generate()">Generate Code</button>

<div id="result"></div>

<script>
// DES implementation (pure JS, no libraries)
const DES = (() => {
  const PC1 = [57,49,41,33,25,17,9,1,58,50,42,34,26,18,10,2,59,51,43,35,27,19,11,3,60,52,44,36,63,55,47,39,31,23,15,7,62,54,46,38,30,22,14,6,61,53,45,37,29,21,13,5,28,20,12,4];
  const PC2 = [14,17,11,24,1,5,3,28,15,6,21,10,23,19,12,4,26,8,16,7,27,20,13,2,41,52,31,37,47,55,30,40,51,45,33,48,44,49,39,56,34,53,46,42,50,36,29,32];
  const SHIFTS = [1,1,2,2,2,2,2,2,1,2,2,2,2,2,2,1];
  const IP = [58,50,42,34,26,18,10,2,60,52,44,36,28,20,12,4,62,54,46,38,30,22,14,6,64,56,48,40,32,24,16,8,57,49,41,33,25,17,9,1,59,51,43,35,27,19,11,3,61,53,45,37,29,21,13,5,63,55,47,39,31,23,15,7];
  const IP2= [40,8,48,16,56,24,64,32,39,7,47,15,55,23,63,31,38,6,46,14,54,22,62,30,37,5,45,13,53,21,61,29,36,4,44,12,52,20,60,28,35,3,43,11,51,19,59,27,34,2,42,10,50,18,58,26,33,1,41,9,49,17,57,25];
  const E =  [32,1,2,3,4,5,4,5,6,7,8,9,8,9,10,11,12,13,12,13,14,15,16,17,16,17,18,19,20,21,20,21,22,23,24,25,24,25,26,27,28,29,28,29,30,31,32,1];
  const P =  [16,7,20,21,29,12,28,17,1,15,23,26,5,18,31,10,2,8,24,14,32,27,3,9,19,13,30,6,22,11,4,25];
  const SBOXES = [
    [14,4,13,1,2,15,11,8,3,10,6,12,5,9,0,7,0,15,7,4,14,2,13,1,10,6,12,11,9,5,3,8,4,1,14,8,13,6,2,11,15,12,9,7,3,10,5,0,15,12,8,2,4,9,1,7,5,11,3,14,10,0,6,13],
    [15,1,8,14,6,11,3,4,9,7,2,13,12,0,5,10,3,13,4,7,15,2,8,14,12,0,1,10,6,9,11,5,0,14,7,11,10,4,13,1,5,8,12,6,9,3,2,15,13,8,10,1,3,15,4,2,11,6,7,12,0,5,14,9],
    [10,0,9,14,6,3,15,5,1,13,12,7,11,4,2,8,13,7,0,9,3,4,6,10,2,8,5,14,12,11,15,1,13,6,4,9,8,15,3,0,11,1,2,12,5,10,14,7,1,10,13,0,6,9,8,7,4,15,14,3,11,5,2,12],
    [7,13,14,3,0,6,9,10,1,2,8,5,11,12,4,15,13,8,11,5,6,15,0,3,4,7,2,12,1,10,14,9,10,6,9,0,12,11,7,13,15,1,3,14,5,2,8,4,3,15,0,6,10,1,13,8,9,4,5,11,12,7,2,14],
    [2,12,4,1,7,10,11,6,8,5,3,15,13,0,14,9,14,11,2,12,4,7,13,1,5,0,15,10,3,9,8,6,4,2,1,11,10,13,7,8,15,9,12,5,6,3,0,14,11,8,12,7,1,14,2,13,6,15,0,9,10,4,5,3],
    [12,1,10,15,9,2,6,8,0,13,3,4,14,7,5,11,10,15,4,2,7,12,9,5,6,1,13,14,0,11,3,8,9,14,15,5,2,8,12,3,7,0,4,10,1,13,11,6,4,3,2,12,9,5,15,10,11,14,1,7,6,0,8,13],
    [4,11,2,14,15,0,8,13,3,12,9,7,5,10,6,1,13,0,11,7,4,9,1,10,14,3,5,12,2,15,8,6,1,4,11,13,12,3,7,14,10,15,6,8,0,5,9,2,6,11,13,8,1,4,10,7,9,5,0,15,14,2,3,12],
    [13,2,8,4,6,15,11,1,10,9,3,14,5,0,12,7,1,15,13,8,10,3,7,4,12,5,6,11,0,14,9,2,7,11,4,1,9,12,14,2,0,6,10,13,15,3,5,8,2,1,14,7,4,10,8,13,15,12,9,0,3,5,6,11]
  ];

  function bytesToBits(bytes) {
    const bits = [];
    for (const b of bytes) for (let i = 7; i >= 0; i--) bits.push((b >> i) & 1);
    return bits;
  }
  function bitsToBytes(bits) {
    const bytes = [];
    for (let i = 0; i < bits.length; i += 8) {
      let b = 0;
      for (let j = 0; j < 8; j++) b = (b << 1) | (bits[i+j] || 0);
      bytes.push(b);
    }
    return bytes;
  }
  function permute(bits, table) { return table.map(i => bits[i-1]); }
  function xor(a, b) { return a.map((v,i) => v ^ b[i]); }

  function generateKeys(keyBytes) {
    const keyBits = permute(bytesToBits(keyBytes), PC1);
    let C = keyBits.slice(0,28), D = keyBits.slice(28);
    const keys = [];
    for (let i = 0; i < 16; i++) {
      for (let s = 0; s < SHIFTS[i]; s++) { C.push(C.shift()); D.push(D.shift()); }
      keys.push(permute([...C,...D], PC2));
    }
    return keys;
  }

  function desBlock(blockBytes, keyBytes, encrypt) {
    const keys = generateKeys(keyBytes);
    if (!encrypt) keys.reverse();
    let bits = permute(bytesToBits(blockBytes), IP);
    let L = bits.slice(0,32), R = bits.slice(32);
    for (let i = 0; i < 16; i++) {
      const expanded = permute(R, E);
      const xored = xor(expanded, keys[i]);
      let sOut = [];
      for (let s = 0; s < 8; s++) {
        const chunk = xored.slice(s*6, s*6+6);
        const row = (chunk[0]<<1)|chunk[5];
        const col = (chunk[1]<<3)|(chunk[2]<<2)|(chunk[3]<<1)|chunk[4];
        const val = SBOXES[s][row*16+col];
        for (let b = 3; b >= 0; b--) sOut.push((val>>b)&1);
      }
      const f = permute(sOut, P);
      const newR = xor(L, f);
      L = R; R = newR;
    }
    return bitsToBytes(permute([...R,...L], IP2));
  }

  function pkcs7Pad(bytes, blockSize) {
    const pad = blockSize - (bytes.length % blockSize);
    return [...bytes, ...Array(pad).fill(pad)];
  }

  function encryptCBC(plaintext, key, iv) {
    const ptBytes = pkcs7Pad([...plaintext].map(c => c.charCodeAt(0)), 8);
    let prev = [...iv].map(c => c.charCodeAt(0));
    const result = [];
    for (let i = 0; i < ptBytes.length; i += 8) {
      const block = xor(ptBytes.slice(i, i+8), prev);
      const enc = desBlock(block, [...key].map(c => c.charCodeAt(0)), true);
      result.push(...enc);
      prev = enc;
    }
    return result;
  }

  return { encryptCBC };
})();

function generateAuthorizationCode(deviceCode, duration, type) {
  const encryptedBytes = DES.encryptCBC(deviceCode, "26582651", "12345678");

  let checksum = 0;
  for (const b of encryptedBytes) checksum += (b & 0xFF);
  checksum += (encryptedBytes[1] & 0xFF) % duration;
  checksum += (encryptedBytes[2] & 0xFF) % type;
  checksum += (encryptedBytes[3] & 0xFF);

  const hex2   = v => (v & 0xFF).toString(16).padStart(2, '0');
  const hexPad = (v, l) => v.toString(16).padStart(l, '0');

  let result = hex2(checksum);
  if (deviceCode.length === 8) {
    result += hexPad(duration + 360, 4);
    result += hexPad(type + 30, 2);
  } else if (deviceCode.length === 9) {
    result += hexPad(duration + 100, 4);
    result += hexPad(type + 6, 2);
  }
  return result.toUpperCase();
}

function generate() {
  const deviceCode = document.getElementById('deviceCode').value.trim().toUpperCase();
  const duration   = parseInt(document.getElementById('duration').value);
  const type       = parseInt(document.getElementById('type').value);

  if (!deviceCode || deviceCode.length < 8) {
    document.getElementById('result').textContent = 'Enter a valid device code';
    return;
  }

  const code = generateAuthorizationCode(deviceCode, duration, type);
  document.getElementById('result').textContent = code;
}
</script>

</body>
</html>
