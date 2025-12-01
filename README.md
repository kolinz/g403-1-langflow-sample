# g403-1-langflow-sample

## RAGシステムのワークフローサンプル
RAGシステムでは、生成回答のなかに、回答と検索コンテキストの２種類が含まれるので、この２つを分離し、回答のみを出力するように調整したワークフロー

ファイル名：[RAG-Multi-LLM-RAGAS-Check-Workflow.json](https://github.com/kolinz/g403-1-langflow-sample/blob/main/RAG-NO-RAGAS%E3%83%BCWorkflow.json)

## RAGシステムおよびハルシネーションリスク評価のワークフローサンプル
RAGの生成回答内容を評価するフレームワークであるRAGASを、プロンプトを用いて自動評価し、ハルシネーションリスクについて分析する処理を行うワークフロー。

ファイル名：[RAG-Multi-LLM-RAGAS-Check-Workflow.json](https://github.com/kolinz/g403-1-langflow-sample/blob/main/RAG-Multi-LLM-RAGAS-Check-Workflow.json)

RAGASの主要４指標のうち、ハルシネーションリスクを重点的に検出・評価するため、「Faithfulness」「Context Precision」「Answer Relevance」、この３つとした。
RAGで使う、ベクトルデータベース情報が正確であれば、この３つの指標でハルシネーションリスクを判定することができる。
もう１つの指標である「Context Recall」は、ベクトルデータベースとは別に、Ground Truth と呼ばれる正解文のデータベースを別途用意する必要があるため、今後の課題。「Context Recall」では、Ground Truthと検索コンテキストを比較するため、検索コンテキストまでは抽出する機能を実装済みである。

## RAGシステムおよびハルシネーションリスク評価について、複数のLLM/SLMによる合議制システム
「RAGシステムおよびハルシネーションリスク評価のワークフローサンプル」をもとに、３つのLLM/SLMにより、ハルシネーションリスクについて、承認 / 否決を判定する 仕組みの実装例。

ファイル名：[RAG-Multi-LLM-RAGAS-Check-Workflow-JSON-output.json](https://github.com/kolinz/g403-1-langflow-sample/blob/main/RAG-Multi-LLM-RAGAS-Check-Workflow-JSON-output.json)

## Langflowの拡張システム : 音声認識・音声合成・IoT連携
[AI Staff Connector Langflow対応版](https://github.com/kolinz/ai-staff-connector/tree/dev-langflow)：メタバースと現実世界を橋渡しするハイブリッド型デジタル職員システム。
- 音声認識 : Watson Speech To Text , OpenAI Whisper（ローカル実行）の選択式
- 音声合成 : Watson Text To Speech , VoiceVoxの選択式
- IoT連携：Incoming/Outgoing Webhook機能があり、Node-REDとの連携が前提。Node-RED用のサンプルフローあり。
- AIエージェントツール連携：DifyおよびLangflowに対応。Langflow経由で、watsonx.aiと連携。

