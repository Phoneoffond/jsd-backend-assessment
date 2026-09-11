# My Understanding

Answer each question in your own words. There are no trick questions.

The goal is not a perfect answer — it is an honest one. Write as if you are explaining to a friend who has never used Express or React. There is no video for this assessment, so this document is where your understanding is actually assessed — take it seriously.

Do not copy from documentation, your code comments, or AI output. If you are unsure about something, write what you do understand and note where the gap is.

---

## AI Code Contribution

Rate yourself honestly using the scale below. This rating is not scored on its own — there is no "best" number to pick. What matters is that it's honest and matches what your code and your answers actually show.

| Rating | Description |
|---|---|
| 0 | **No AI use.** I did not use AI to generate code, explain concepts, debug, or teach me. |
| 1 | **AI used only for learning.** I did not use AI to generate code, but I used AI to explain concepts, clarify errors, or guide my understanding. |
| 2 | **Mixed coding with AI support.** I wrote some code myself and used some AI-generated code. I also used AI to help me understand, debug, or improve my solution. |
| 3 | **Learned from AI-generated code, then coded myself.** AI generated example code or guidance, but I used that understanding to write or adapt the final code myself. |
| 4 | **AI generated the code, but I fully understand it.** AI generated most or all of the code, but I can explain how it works, why it works, and how the main parts connect. |
| 5 | **AI generated the code with limited understanding.** AI generated most or all of the code, and I cannot confidently explain how or why everything works. |

**My rating:** _5_

> If you rated **2 or higher**, also complete the "AI Process" section at the end of this document.

1. คัดลอกโจทย์ไปถาม AI ว่าต้องใช้เครื่องมืออะไรบ้าง
2. สร้างข้อมูล Database แล้วส่งให้ AI ทำงาน
3. เขียนคำสั่ง
4. คัดลอกโค้ดมาแปะใน VS Code แล้วลอง Run ดู
5. แก้ Error
6. ตรวจสอบวงเล็บและชื่อไฟล์ว่ามีวงเล็บขาด/เกิน หรือชือไฟล์มี s ต่อท้ายครบหรือไม่
7. ลองยิงข้อมูลดู
8. แก้ Bug
9. ลอง Run ใหม่
10. เชค Port ว่าถูกต้อไงไหม
11. Run ใหม่
---

## Backend

**1. What does each HTTP method in your API mean — GET, POST, PUT or PATCH, and DELETE? Why do we use different methods instead of just using POST for everything?**

*Your answer:*

GET คือ การดึงข้อมูล

POST คือ การสร้างข้อมูล

PUT คือ การอัพเดตข้อมูล

DELETE คือ การลบข่้อมูล

ที่ต้องแยกเพราะมีหน้าที่ต่างกัน ถ้าสร้างข้อมูลใหม่ไปเรื่อยๆ อาจจะซ้ำหรือซ้อนทับกับข้อมูลเดิมได้ หรือบางข้อมูลที่มีความผิดพลาด ก็ควรลบออก ไม่ใช่ใส่แก้ทับชื่อเดิม เวลาดึงข้อมูลจะสับสน เช่น อีเมลเดียวกันที่มีหลาย ID และมี password หลายเวอร์ชั่น

---

**2. What is `express.json()` and what would happen if you left it out?**

*Your answer:*

มันคือการแปลงข้อมูลให้เป็น JSON ทำให้เครื่องอ่านค่าได้ ถ้าไม่แปลงจัอ่านค่าไม่ได้

---

**3. What is the difference between `req.body`, `req.params`, and `req.query`? Give a real example from your API for each one.**

*Your answer:*

`req.body` คือ การดึงข้อมูลทั้งหมดออกมา
`req.params` คือ การดึงข้อมูลเฉาพบางพารามิเตอร์ เช่น ดึงเฉพาะอีเมล  
`req.query` คือ การดึงข้อมูลแบบดึงข้อมูลที่มีเนื้อหาหรือ keyword นั้นๆ ที่ถูกเก็บไว้ในฐานข้อมูล

---

**4. What are HTTP status codes? List every status code you used in your API and explain why you chose it for that situation.**

*Your answer:*

มันคือช่องสัญญาณที่จะบอกได้ว่า ข้อมูลที่เรียกไปมีอยู่ในฐานข้อมูลรึเปล่า เรียกเจอหรือไม่ ไม่มีข้อมูลนั้นๆ ถ้าไม่มีจะขึ้น not found แต่ถ้าหาไม่เจอขะขึ้น error

---

**5. What is middleware? Describe what it does in your own words and give one example from your code.**

*Your answer:*

GET คือ การดึงข้อมูล

POST คือ การสร้างข้อมูล

PUT คือ การอัพเดตข้อมูล

DELETE คือ การลบข่้อมูล

---

**6. Why does the order of middleware matter in Express? What could go wrong if it were in the wrong order?**

*Your answer:*

ที่ต้องเรียงลำดับ เพราะบางคำสั่งไม่สามารถทำงานได้ ถ้าไม่มีข้อมูลเริ่มต้น เช่น DELETE จะลบไม่ได้ ถ้ายังไม่ดึงข้อมูลผ่านการ GET ก่อน

---

**7. Walk through what happens on the server, step by step, when a POST request is sent to `/products`.**

*Your answer:*

ในเซิร์ฟเวอร์จะสร้างข้อมูลสินค้าชุดใหม่ขึ้นมาในฐานข้อมูล

---

**8. What is CRUD? Map each operation to the HTTP method and route you used in your API.**

*Your answer:*

ใข้ตามหลังฟังก์ชั้น เช่น app.get() 

---

**9. How does your API respond when something goes wrong — for example, when a product with a given ID does not exist?**

*Your answer:*

ถ้าหาไม่เจอขึ้น Not found ถ้าไม่มีในคำสั่งขึ้น Error

---

## Frontend & Integration

**10. What is CORS, and what problem does it solve? What would you see in your browser if it wasn't configured on your server?**

*Your answer:*

---

**11. Where does your React app fetch data from your API? Walk through what `useEffect` is doing in that code, and why the fetch isn't just called directly in the component body.**

*Your answer:*

---

**12. Where is your API's base URL defined, and why did you put it there instead of hardcoding it in every fetch call?**

*Your answer:*

---

**13. Pick one action in your app — for example, deleting a product. Walk through the full round trip: what happens from the moment the user clicks the button, to the request reaching your server, to the screen updating with the new list.**

*Your answer:*

---

**14. What does your app show the user while data is loading, and what does it show if the fetch fails (e.g. the server isn't running)? Why does that matter?**

*Your answer:*

---

**15. After you add, edit, or delete a product, your on-screen list updates without a page refresh. Explain how — what actually causes React to re-render with the new data?**

*Your answer:*

---

**16. What was the hardest part of connecting your React app to your Express API, and what did you do to get past it?**

*Your answer:*

---

## AI Process

Only complete this section if you rated yourself **2 or higher** on the AI Code Contribution Scale above. If you rated 0 or 1, write "N/A" under each question.

**17. If you used AI to generate any code, how did you break the work into steps or prompts? Give one example of a specific prompt you used, rather than a single "build the whole app" request.**

*Your answer:*

---

**18. Describe one specific thing an AI tool generated that you changed, corrected, or rejected — and why.**

*Your answer:*

---

**19. Describe one real bug or error you ran into while building this. How did you actually figure out what was wrong, beyond pasting the error back into the chat?**

*Your answer:*

---

**20. Pick one route (backend) or one component (frontend) that AI helped generate. Without looking back at your AI chat history, explain what it does and why it works, in your own words.**

*Your answer:*
