\# SPEC.md — VUI HỌC (PWA GAME GIA ĐÌNH)



\*\*Phiên bản\*\*: 1.1

\*\*Ngày cập nhật\*\*: 2026-09-26

\*\*Trạng thái\*\*: Phase 1 đang hoàn thiện



\---



\## 1. MỤC TIÊU

PWA game học tập cho trẻ lớp 4 trong phạm vi gia đình (\~100 user).



\## 2. NGƯỜI DÙNG

\- \*\*Student\*\*: Chơi, xem điểm, đổi quà

\- \*\*Parent\*\*: Duyệt đổi quà

\- \*\*Admin\*\*: Quản lý câu hỏi, user



\## 3. KIẾN TRÚC

\- Frontend: HTML + Vanilla JS + TailwindCSS (CDN)

\- Backend: Google Apps Script (Phase 2)

\- DB: Google Sheets (Phase 2)

\- Deploy: GitHub Pages

\- PWA: manifest.json + Service Worker



\## 4. DATA MODEL (Google Sheets)

\- Users, Subjects, Questions, Results, Rewards, ExchangeRequests, Config



\## 5. GAME FLOW

1\. Đăng nhập (chọn role: Học sinh / Phụ huynh / Admin ngầm)

2\. Học sinh chọn môn → thi 10 câu

3\. \*\*Thời gian: 10 phút / 10 câu\*\*

4\. \*\*Chọn đáp án → hiện kết quả NGAY\*\*:

&#x20;  - Đúng: "ting ting" + confetti + cộng điểm

&#x20;  - Sai: "reeeett" + hiện đáp án đúng

&#x20;  - Khóa đáp án sau khi chọn

&#x20;  - Tự động sang câu tiếp sau 1.5s

5\. \*\*Nút "Nộp bài"\*\* luôn hiển thị + popup xác nhận

6\. Hết giờ → tự động nộp

7\. Sau 5 vòng → vòng quay may mắn



\## 6. QUY TẮC THI

| Quy tắc | Giá trị |

|---|---|

| Số câu/vòng | 10 |

| Thời gian | 10 phút (600s) |

| Format | Trắc nghiệm 4 đáp án |

| Trộn câu hỏi | Có |

| Trộn đáp án | Có |

| Hết giờ | Tự nộp |

| Feedback | Ngay khi chọn |



\## 7. ÂM THANH (Web Audio API)

\- Click: sine 600Hz

\- Đúng: "ting ting" (C6 + E6)

\- Sai: "reeeett" (sawtooth 400→120Hz)

\- Tick: square 1000Hz (10s cuối)

\- Win: 4 nốt tăng dần



\## 8. BẢNG XẾP HẠNG

\- Theo tổng điểm

\- Theo tuần

\- Không reset



\## 9. QUÀ

\- Vòng quay: 1k (50%), 2k (25%), 3k (15%), 5k (10%)

\- Lưu vào kho (Rewards)

\- Yêu cầu đổi → phụ huynh duyệt



\## 10. TECH STACK

| Layer | Công nghệ |

|---|---|

| Frontend | HTML/CSS/Vanilla JS |

| UI | TailwindCSS CDN |

| Font | Baloo 2, Nunito |

| PWA | manifest + SW |

| Local storage | localStorage |

| Backend | Apps Script |

| DB | Google Sheets |



\## 11. LỘ TRÌNH

\- ✅ Phase 1: MVP offline

\- ⏳ Phase 2: Google Sheets

\- ⏳ Phase 3: Vòng quay + kho quà

\- ⏳ Phase 4: Đổi quà + phụ huynh

\- ⏳ Phase 5: Đa môn

\- ⏳ Phase 6: Admin



\## 12. CẤU TRÚC FILE (PHASE 1)

