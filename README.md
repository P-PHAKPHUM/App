# Link ปิดแถบแจ้งเตือน Google Apps Script
1) สร้าง new repository ของ github และสร้างไฟล์ index.html ใน repository
2) Build and deployment pages me ให้เพจทำงานได้
3) เรียกใช้ URL และใส่ ?apps= ต่อท้าย
4) นำ URL ที่ได้มาใช้งาน ตามด้วยลิ้งค์ของ Web App จาก Google Apps Script
5) ตัวอย่าง https://p-phakphum.github.io/app/?apps=[URL ของ Web App จาก Google Apps Script]

# Code ไฟล์ index.html (ให้เข้าไปก็อปที่ไฟล์ index.html หรือใน code แต่ไม่เอา <pre> บรรทัดบนสุดกับล่างสุด
<pre>
<!DOCTYPE html>
<html>
<head>
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>My App</title>
  <style>
    .responsive-iframe {
      position: absolute;
      top: 0;
      left: 0;
      bottom: 0;
      right: 0;
      width: 100vw;
      height: 100vh;
      border: none;
    }
  </style>
</head>
<body>
  <div> 
    <iframe id="myframe" class="responsive-iframe" src="" allowFullScreen></iframe>
  </div>
  <script>
    const apps = new URL(window.location);
    const formUrl = apps.searchParams.get('apps');
    const url = decodeURIComponent(formUrl)
          document.getElementById('myframe').src = url
  </script>
</body>
</html>
<pre>
