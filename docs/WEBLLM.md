# WebLLM

The app loads WebLLM only after user activation. It uses a dedicated module worker (`workers/webllm-worker.mjs`) and `CreateWebWorkerMLCEngine`. The model list is read from WebLLM's current prebuilt registry rather than hard-coding a stale model.

Local AI output is a draft. It cannot silently commit shared project state.
