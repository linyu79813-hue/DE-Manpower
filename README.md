# 外送人力盤點 V1
1. 將本資料夾內所有檔案上傳至 GitHub repository 根目錄。
2. Settings > Pages > Deploy from a branch > main / root > Save。
3. 開啟 Pages 網址，先使用示範模式。OP Dashboard 可載入虛構資料，測試 Excel 匯出。示範資料只在同一瀏覽器保存。
4. 如需測試跨裝置，建立 Supabase 專案，在 SQL Editor 執行 schema.sql。在 config.js 填入 Project URL 與 publishable/anon key（絕不可使用 service_role key）。Authentication > Users 建立管理帳號，再依 SQL 最後範例加入 manager_scope，中心欄位填 OP 或中心名稱。重新上傳 config.js。
5. 正式模式管理者依 RLS 權限讀取資料；員工端只能新增，不能讀取其他人的資料。

注意：V1 公開提交尚未驗證員工身分，可能冒填、重複提交或遭濫用；只適合虛構資料測試，不應直接發給真實員工。正式上線前需加入員工驗證、伺服器端區間驗證、限流及可信提交時間，確認公司個資政策及管理權限。V1 以中心＋員工編號取最新提交。尚無員工名冊、實際班表比對及回收率。Excel 依篩選條件匯出四個工作表。外部 CDN 需要網路。未進行實際 Supabase 部署或瀏覽器端完整測試。
