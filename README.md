Lesson 1: Building Code Agents with Hugging Face smolagents

🧠 什麼是 AI 代理人（AI Agent）？

AI 代理人是一種可以感知環境、進行推理決策，並採取行動來達成特定目標的智慧系統。

AI agents are intelligent systems that can perceive, reason, and act toward specific goals.

🔍 DeepLearning.AI 定義：

An AI agent is a program where an AI model’s output impacts the execution flow of the program.

這代表 AI 不只是用來做預測，而是成為決策中樞，主動控制邏輯、流程與後續行動。

⸻

📦 AI 代理人的主要組成要素 (Key Components)

組成要素	說明	English Annotation
感知	接收外部環境資訊，如 API 或感測器資料	Collects input from sensors or data.
推理	根據資訊做出判斷與決策	Makes decisions based on logic or models.
行動	對環境反應，如執行任務或控制設備	Takes action like replying or executing commands.
自主性	不需人為干預，自主完成任務與調整策略	Operates independently with minimal human input.
模型驅動	AI 輸出會影響控制流程與分支選擇	The AI model output determines control flow.


⸻

🔢 AI 代理人主控等級（A Range of Agency Levels）

等級	描述	名稱（英文）	程式範例
☆☆☆	LLM 輸出不影響流程	Simple Processor	process_llm_output(llm_response)
★☆☆	LLM 決定執行哪個分支	Router	if llm_decision(): path_a() else: path_b()
★★☆	LLM 選擇呼叫的工具與參數	Tool-calling	run_function(llm_tool, llm_args)
★★★	控制是否繼續執行多步任務	Multi-step Agent	while llm_continue(): next_step()
★★★	控制觸發其他代理流程	Multi-Agent	if llm_trigger(): execute_agent()


⸻

🚀 AI 主控能力進化路徑（The Road Towards Increased Agency）

1. Router
	•	LLM 控制 if/else 流程。

if llm_decision():
    path_a()
else:
    path_b()

	•	「Language Models that Seek for Knowledge」 (Mar 2022)

2. Tool-calling
	•	LLM 呼叫具體函式與參數。

run_function(llm_chosen_tool, llm_chosen_args)

	•	「WebGPT」 (Jun 2022)

3. Multi-step Agent
	•	控制多輪推理與反覆行動。

while post_process(llm_output):
    # do something

	•	「ReAct」 (Mar 2023)

4. Code Agent
	•	能動態產生與執行程式碼。

exec(llm_output_code)

	•	「Executable Code Actions Elicit Better LLM Agents」 (Jun 2024)

⸻

🛠 如何訓練更強的 AI 代理人？

✅ 重點摘要：
	•	2024 前訓練方法：多用 SFT，著重模仿格式（form），不一定具備規劃能力。
	•	更有效方法：改用 DPO（Direct Preference Optimization），讓模型學「更好」的策略。
	•	錯誤恢復能力是關鍵：真實世界 agent 應能從錯誤中調整，而非一錯就終止。
	•	RL 強化學習：適合讓 agent 學習長期規劃與錯誤調整。

