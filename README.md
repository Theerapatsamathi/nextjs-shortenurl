# Answer

## 1. System Design

 - ก่อนอื่นตั้งค่าฟังก์ชัน Serverless โดยใช้ AWS Lambda และ API Gateway ฟังก์ชันนี้จะรับผิดชอบในการสร้าง URL แบบย่อ ตั้งค่าตาราง DynamoDB เพื่อจัดเก็บ URL ดั้งเดิมและ URL แบบสั้นของแต่ละ Record เมื่อ User ส่งคำขอให้ย่อ URL ฟังชั่นจะทำการเก็บ URL ดั้งเดิมและ URL แบบย่อไว้ในตาราง DynamoDB ในเว็บมีแบบฟอร์มที่ผู้ใช้สามารถป้อน URL ดั้งเดิมและ URL ย่อ และส่งคำขอ Serverless เพื่อย่อให้สั้นลงได้ เมื่อ User ไปที่ URL แบบย่อสามารถดึง URL ดั้งเดิมจากตาราง DynamoDB และ redirect user ไปยัง URL ดั้งเดิม



- database - DynamoDB เป็น NoSql เข้าได้ดีกับเว็บแอพแบบ Serverless ที่ถูก request บ่อยๆ  เหมาะกับงาน API ประเภทนี้ กิน ram , cpu น้อยปรับแต่งง่าย รวดเร็ว และฟรี
- back-end && backend - ทั้งคู่จะใช้เป็น NextJs นอกจาก NextJs จะเป็น React framework ที่ใช้ทำ front-end ได้  แล้วยังใช้ทำ API ได้ แถมไม่ต้อง Config อะไรมากมายมีความเบาในการใช้ และเรียนรู้ได้ไม่		         ยาก (เพิ่งเริ่มเรียนรู้และใช้งานสองสามวัน)
- deployment - Vercel ใช้ง่าย deploy ได้ไม่ถึง 5 นาที และที่สำคัญ ฟรี ถ้า app ไม่ใหญ่ถือว่าเหมาะมาก


https://shortenurls.vercel.app/



## 2. Up To You เขียนโปรแกรมเพื่อตรวจสอบสตริงว่าเป็นพาลินโดรมหรือไม่?


- C# ก่อนอื่นต้องค้นหาการย้อนกลับของสตริงโดยใช้ − Array.reverse()
หลังจากนั้นให้ใช้ method equals() เพื่อจับคู่สตริงกับสิ่งที่ตรงกันข้าม หากเป็น true แสดงว่าสตริงนั้นเป็น Palindrome
```bash
using System;
namespace Palindrom {
   class Program {
      static void Main(string[] args) {

         string string1, rev;
         string1 = "Kayak";
         char[] ch = string1.ToCharArray();

         Array.Reverse(ch);
         rev = new string(ch);

         bool b = string1.Equals(rev, StringComparison.OrdinalIgnoreCase);
         if (b == true) {
            Console.WriteLine("" + string1 + " is a Palindrome!");
         } else {
            Console.WriteLine(" " + string1 + " is not a Palindrome!");
         }
         Console.Read();
      }
   }
}
```



