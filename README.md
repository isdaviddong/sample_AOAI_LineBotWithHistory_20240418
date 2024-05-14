### 檔案說明
以下是這個系統的主要程式碼檔案：

| 檔案名稱                          | 說明                                                         |
|----------------------------------|--------------------------------------------------------------|
| LineBotChatGPTWebHookController.cs | 處理來自 Line 的 Webhook 事件的控制器，負責接收並處理用戶訊息 |
| ChatHistoryManager.cs             | 管理與用戶的聊天紀錄的類別，提供獲取、保存和刪除聊天紀錄的方法 |
| ChatGPT.cs                        | 與 OpenAI GPT-3 進行交互的類別，負責發送用戶訊息並獲取回應     |

### 專案說明
這個系統是一個基於 Line Bot 的聊天機器人，主要功能如下：

接收並處理來自 Line 的 Webhook 事件：當用戶在 Line 上發送訊息時，Line 會將這些訊息作為事件發送到設定的 Webhook URL。在 LineBotChatGPTWebHookController.cs 中，POST 方法就是用來接收並處理這些事件的。它會根據事件的類型和內容來決定如何回應用戶。

管理聊天紀錄：在 ChatHistoryManager.cs 中，提供了一些方法來管理與用戶的聊天紀錄，包括從隔離存儲中獲取聊天紀錄、保存聊天紀錄到隔離存儲，以及刪除所有聊天紀錄。

與 OpenAI GPT-3 進行交互：在 ChatGPT.cs 中，getResponseFromGPT 方法會將用戶的訊息和聊天紀錄一起發送到 OpenAI GPT-3，並獲取 GPT-3 的回應。然後，這個回應會被發送回 Line，作為對用戶的回應。

總的來說，這個系統的主要功能是接收並處理用戶的訊息，並利用 OpenAI GPT-3 來生成回應。同時，它也會保存和管理與用戶的聊天紀錄。