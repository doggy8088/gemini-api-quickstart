# Gemini API 快速入門 - Python

此存放庫包含一個簡易的 Python Flask 應用程式，使用 Google AI Gemini API 執行，旨在讓您開始使用 Gemini 的多模態功能進行建置。此應用程式附帶基本的 UI 和 Flask 後端。

<img width="1271" alt="2024-05-07 上午 7:42:28 的螢幕截圖" src="https://github.com/logankilpatrick/gemini-api-quickstart/assets/35577566/156ae3e0-cffa-47a3-8a71-1bded78c4632">

## 基本要求

若要透過 [Gemini API Python SDK](https://github.com/google-gemini/generative-ai-python) 傳送您第一個 API 要求，請確定您已安裝正確的相依性 (請參閱下方的安裝步驟)，然後執行下列程式碼：

```python
import google.generativeai as genai
genai.configure(api_key=GOOGLE_API_KEY)
model = genai.GenerativeModel('gemini-pro')

chat = model.start_chat(history=[])
response = chat.send_message("In one sentence, explain how AI works to a child.")
# Note that the chat object is temporarily stateful, as you send messages and get responses, you can 
# see the history changing by doing `chat.history`.

print(response.text)
```

## 設定

1. 如果你尚未安裝 Python，請 [從 Python.org 安裝](https://www.python.org/downloads/)。

2. [複製](https://docs.github.com/en/repositories/creating-and-managing-repositories/cloning-a-repository) 這個存放庫。

3. 建立新的虛擬環境：

   - macOS：

     ```bash
     $ python -m venv venv
     $ . venv/bin/activate
     ```

   - Windows：
     ```cmd
     > python -m venv venv
     > .\venv\Scripts\activate
     ```

4. 安裝需求：

   ```bash
   $ pip install -r requirements.txt
   ```

5. 複製範例環境變數檔案：

   ```bash
   $ cp .env.example .env
   ```

6. 將你的 [API 金鑰](https://ai.google.dev/gemini-api/docs/api-key) 新增到新建立的 `.env` 檔案。

7. 執行應用程式：

```bash
$ flask run
```

你現在應該能透過下列 URL 從瀏覽器存取應用程式： [http://localhost:5000](http://localhost:5000)！

#### 說明

此存放庫包含一個從 [我建立的其他存放庫](https://github.com/openai/openai-quickstart-python) 分岔出來的程式碼，其遵循 MIT 授權。



