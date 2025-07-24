# Kimi K2 Chatbot

Một ứng dụng chatbot AI sử dụng mô hình Kimi K2 của Moonshot AI, được xây dựng với Next.js, TypeScript, React và Tailwind CSS.

## Tính năng

- 🤖 Tích hợp với Kimi K2 (Moonshot AI) qua Together AI API
- 💬 Giao diện chat thời gian thực với auto-scroll
- 📱 Responsive design, hoạt động tốt trên mobile và desktop
- ⚡ Loading spinner và xử lý lỗi
- 🧹 Chức năng xóa lịch sử chat
- 🔒 TypeScript nghiêm ngặt cho type safety
- 🎨 UI đẹp với Tailwind CSS

## Yêu cầu hệ thống

- Node.js 18+ 
- npm hoặc yarn
- API key từ Together AI

## Cài đặt và chạy local

### 1. Clone repository

\`\`\`bash
git clone <repository-url>
cd kimi-k2-chatbot
\`\`\`

### 2. Cài đặt dependencies

\`\`\`bash
npm install
# hoặc
yarn install
\`\`\`

### 3. Cấu hình environment variables

Tạo file \`.env.local\` trong thư mục root:

\`\`\`env
KIMI_API_KEY=your_kimi_k2_api_key_here
\`\`\`

**Lấy API key:**
1. Truy cập [Together AI](https://api.together.xyz/)
2. Đăng ký tài khoản
3. Tạo API key mới
4. Copy và paste vào file \`.env.local\`

### 4. Chạy ứng dụng

\`\`\`bash
npm run dev
# hoặc
yarn dev
\`\`\`

Mở trình duyệt và truy cập [http://localhost:3000](http://localhost:3000)

## Cấu trúc thư mục

\`\`\`
kimi-k2-chatbot/
├── app/
│   ├── api/
│   │   └── chat/
│   │       └── route.ts          # API endpoint cho chat
│   ├── components/
│   │   ├── ChatInput.tsx         # Component input chat
│   │   ├── ChatMessage.tsx       # Component hiển thị tin nhắn
│   │   └── LoadingSpinner.tsx    # Component loading
│   ├── types/
│   │   └── chat.ts              # TypeScript interfaces
│   ├── globals.css              # Global styles
│   ├── layout.tsx               # Root layout
│   └── page.tsx                 # Main chat page
├── .env.local                   # Environment variables
├── package.json
├── tailwind.config.js
├── tsconfig.json
└── README.md
\`\`\`

## Deploy lên Vercel

### 1. Chuẩn bị

\`\`\`bash
npm run build
\`\`\`

### 2. Deploy với Vercel CLI

\`\`\`bash
npm i -g vercel
vercel
\`\`\`

### 3. Cấu hình environment variables trên Vercel

1. Vào Vercel Dashboard
2. Chọn project
3. Vào Settings → Environment Variables
4. Thêm \`KIMI_API_KEY\` với giá trị API key của bạn

### 4. Deploy với GitHub (khuyến nghị)

1. Push code lên GitHub repository
2. Import project từ GitHub vào Vercel
3. Cấu hình environment variables
4. Deploy tự động

## API Documentation

### POST /api/chat

Gửi tin nhắn đến Kimi K2 và nhận phản hồi.

**Request Body:**
\`\`\`json
{
  "messages": [
    {
      "role": "user",
      "content": "Xin chào!"
    }
  ]
}
\`\`\`

**Response:**
\`\`\`json
{
  "message": "Xin chào! Tôi có thể giúp gì cho bạn?",
  "usage": {
    "prompt_tokens": 10,
    "completion_tokens": 15,
    "total_tokens": 25
  }
}
\`\`\`

## Xử lý lỗi

Ứng dụng xử lý các lỗi phổ biến:

- ❌ API key không hợp lệ
- ❌ Hết quota API
- ❌ Lỗi kết nối mạng
- ❌ Lỗi server

## Tính năng nâng cao (TODO)

- [ ] Streaming response (real-time typing)
- [ ] Lưu lịch sử chat vào localStorage
- [ ] Dark mode
- [ ] Export chat history
- [ ] Multiple conversation threads
- [ ] File upload support

## Troubleshooting

### Lỗi "API key not configured"
- Kiểm tra file \`.env.local\` có tồn tại
- Đảm bảo \`KIMI_API_KEY\` được set đúng
- Restart development server

### Lỗi "Invalid API key"
- Kiểm tra API key có đúng không
- Đảm bảo API key còn hoạt động

### Lỗi build
- Chạy \`npm run type-check\` để kiểm tra TypeScript errors
- Chạy \`npm run lint\` để kiểm tra ESLint errors

## Đóng góp

1. Fork repository
2. Tạo feature branch (\`git checkout -b feature/amazing-feature\`)
3. Commit changes (\`git commit -m 'Add amazing feature'\`)
4. Push to branch (\`git push origin feature/amazing-feature\`)
5. Tạo Pull Request

## License

MIT License - xem file [LICENSE](LICENSE) để biết thêm chi tiết.
\`\`\`
