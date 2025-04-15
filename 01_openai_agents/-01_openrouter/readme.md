# OpenRouter: 50 Free LLMs ke liye Ek Unified Interface  
| [**Code Example:** Basic aur OpenAI Agents SDK OpenRouter ke saath](https://colab.research.google.com/drive/1LOEOBP52WJpmMWsOS7-SUDQBLtmXZ_1d?usp=sharing)  

OpenRouter naye DeepSeek V3 0324 aur 50 se zyada models ko free mein support karta hai. In mein se zyada tar OpenAI Chat Completion API standard ko support karte hain.  
https://openrouter.ai/deepseek/deepseek-chat-v3-0324:free  

Dekhein [OpenRouter Quickstart Guide](https://openrouter.ai/docs/quickstart) aur [Python se OpenRouter se Connect karna](https://medium.com/%40tedisaacs/from-openai-to-opensource-in-2-lines-of-code-b4b8d2cf2541)  

---

## Rate Limits  
LLMs API ke rate limits ko kuch dimensions mein measure kiya jata hai:  
1. Requests per minute (RPM)  
2. Tokens per minute (TPM)  
3. Requests per day (RPD)  

### OpenRouter ke Free Models ke Rate Limits  
OpenRouter ke free models ke liye global limit hai 200 requests per day (RPD) sab free models ke liye, aur kuch ke liye 20 requests per minute (RPM) bhi hai, jaise ke documentation mein likha hai. Yeh limits un models pe lagte hain jinke IDs ":free" ke saath khatam hote hain.  

### Google Gemini ke Free Tier ke Rate Limits  
https://ai.google.dev/gemini-api/docs/rate-limits  
Gemini 2.0 Flash aur Gemini 2.0 Flash-Lite ke Free Tier mein 1,500 requests per day (RPD) ki limit hai, jabke requests per minute (RPM) ki limit Flash ke liye 15 aur Flash-Lite ke liye 30 hai. Dono models ke liye 1,000,000 Tokens per minute (TPM) ki cap bhi hai.  

Development aur testing ke liye 1,500 requests per day (RPD) kaafi hai, isliye **development aur testing ke liye hum Google Gemini 2.0 Flash aur Gemini 2.0 Flash-Lite models use karenge**. Yeh dono models OpenAI Chat Completion API aur OpenAI Agents SDK ke saath compatible hain. OpenRouter ki 200 requests per day (RPD) ki limit development aur testing ke liye bohat strict hai.  

Google Gemini ab OpenAI Chat Completion API ko bhi support karta hai, toh hum isse OpenAI Agents SDK ke saath use kar sakte hain:  
https://ai.google.dev/gemini-api/docs/openai  
https://github.com/panaversity/learn-agentic-ai/tree/main/01_openai_agents/03_hello_agent  

OpenRouter APIs development ke liye backup ka kaam karenge, aur bohat saare models ko jaldi test karne ke liye.  

---

### OpenRouter Kya Hai?  
OpenRouter ek platform hai jo bohat saare large language models (LLMs) tak ek unified tareeke se access deta hai, jismein OpenAI aur Anthropic jaise commercial options aur Mistral aur LLaMA jaise open-source models shamil hain. Yeh platform ek hi API endpoint dekar models ke beech switch karna asaan karta hai, bina code change kiye. Yeh platform cost, performance, aur availability ke hisaab se requests ko behtareen provider tak route karta hai, jaise ke price, latency, aur uptime ke factors ke basis pe.  

### User Interface aur API  
OpenRouter dono user interface aur API deta hai. User interface mein ek chatroom hai jahan users ek saath multiple LLMs se baat kar sakte hain, aur account manage karne aur usage monitor karne ke tools bhi hain, jaise token usage aur costs dekhna. API developers ke liye hai, jo ek standard tareeka deta hai LLM capabilities ko apps mein integrate karne ka.  

### OpenAI Chat Completion API ke liye Support  
OpenRouter OpenAI Chat Completion API ke saath compatible hai, iska structure, endpoints, aur parameters same hain. Isse developers OpenRouter pe switch kar sakte hain sirf API key aur base URL change karke, jo existing OpenAI SDK code ke saath asaan hai.  

### Function Calling ke liye Support  
OpenRouter function calling (tool calling) ko support karta hai, jismein AI external tools use karne ka suggestion de sakta hai input ke basis pe. Yeh feature compatible models ke liye standard hai, jisse developers weather APIs jaise functions integrate kar sakte hain.  

### Hosting Models: Proxy ya Host?  
OpenRouter ek proxy ke tor pe kaam karta hai, API requests ko third-party providers ke models tak route karta hai, khud models host nahi karta. Is tareeke se yeh 200 se zyada models tak access deta hai bina hosting ke cost ke, aur translations aur authentications handle karta hai.  

---

### Survey Note: OpenRouter pe Comprehensive Details  
OpenRouter ek platform hai jo bohat saare large language models (LLMs) tak access ko asaan banane ke liye banaya gaya hai, aur yeh user interface aur API dono deta hai. Yeh section iske features, compatibility, functionality, aur operational model ki detail mein jaankari deta hai, taake developers, researchers, aur enthusiasts ko ache se samajh aaye.  

#### Platform Overview aur User Interface  
OpenRouter ek unified interface hai jo OpenAI, Anthropic, Google, aur Meta jaise commercial providers aur Mistral aur LLaMA jaise open-source models tak access deta hai. Iska main faida yeh hai ke yeh sab models ko ek jagah pe laata hai, jisse users ko alag-alag API keys aur endpoints manage nahi karne padte.  

User interface bohat user-friendly hai, jismein ek chatroom hai jo ek saath multiple LLMs se baat karne ke liye hai. Yeh chatroom [https://openrouter.ai/chat](https://openrouter.ai/chat) pe hai, jo 1.5 billion tokens support karta hai, aur testing aur casual use ke liye perfect hai. Iske saath account management features bhi hain, jahan users usage monitor kar sakte hain, token counts dekh sakte hain, aur credits manage kar sakte hain, jaise documentation mein likha hai ([Connecting to OpenRouter | Novelcrafter Help Center](https://docs.novelcrafter.com/en/articles/8678022-connecting-to-openrouter)).  

API developers ke liye hai, jo ek standard endpoint deta hai jo OpenAI jaise SDKs ke saath kaam karta hai. Yeh dual offering dono end-users aur technical professionals ke liye kaam karta hai, aur alag-alag use cases ke liye faida deta hai.  

#### OpenAI Chat Completion ke saath API Compatibility  
OpenRouter ka API OpenAI Chat Completion API ke saath compatible hai, jo developers ke liye bohat bada feature hai jo OpenAI ke ecosystem se bahar jaana chahte hain. Yeh compatibility OpenAI ke API structure ko mirror karke kaam karta hai, jismein `/v1/chat/completions` endpoint aur parameters jaise `model`, `messages`, `temperature`, aur `max_tokens` shamil hain. Documentation ke mutabiq, switch karne ke liye sirf API key aur base URL ko [https://openrouter.ai/api/v1](https://openrouter.ai/api/v1) pe update karna hai, jaise [OpenRouter Quickstart Guide](https://openrouter.ai/docs/quickstart) aur [Connecting to OpenRouter from Python](https://medium.com/%40tedisaacs/from-openai-to-opensource-in-2-lines-of-code-b4b8d2cf2541) mein likha hai. Yeh compatibility OpenAI SDKs ke saath bhi kaam karta hai, jisse developers OpenRouter ke zyada models ka faida utha sakte hain bina code change kiye.  

#### Function Calling ke liye Support  
Function calling ya tool calling ek important feature hai jo OpenRouter support karta hai, jisse LLMs user input ke basis pe external tools use karne ka suggestion de sakte hain. Yeh functionality compatible models aur providers ke liye standard hai, aur OpenAI ke tool calling interface ke saath align karta hai. Documentation pe [Tool & Function Calling | Use Tools with OpenRouter](https://openrouter.ai/docs/features/tool-calling) iski detail deta hai, aur Python examples bhi hain jaise weather APIs integrate karne ke. Sab models yeh feature support nahi karte, compatibility provider pe depend karta hai (jaise OpenAI ka GPT-4o aur Anthropic ka Claude aksar support karte hain), lekin OpenRouter ensure karta hai ke `tools` parameter use karne pe sirf supporting providers ko route kiya jaye.  

#### Model Hosting: Proxy ya Host?  
OpenRouter ek proxy ke tor pe kaam karta hai, API requests ko third-party providers ke models tak route karta hai jahan actual model inference hota hai. Yeh Reddit discussion se pata chalta hai jahan users ne isse "proxy" kaha ([r/ChatGPTCoding on Reddit](https://www.reddit.com/r/ChatGPTCoding/comments/1fdwegx/eli5_how_does_openrouter_work/)), aur documentation mein bhi provider routing ki baat hai cost aur performance ke liye ([Provider Routing | Intelligent Multi-Provider Request Routing](https://openrouter.ai/docs/features/provider-routing)). Yeh platform API translations, authentications, aur response formatting handle karta hai, aur providers jaise Together AI, AWS, ya Fireworks models host karte hain. Is proxy model se OpenRouter 200 se zyada models tak access deta hai bina hosting ke cost ke, aur pricing upstream provider costs aur OpenRouter ke operational fee pe based hai.  

#### Additional Features aur Operational Details  
OpenRouter ka platform flexibility aur efficiency ke liye design kiya gaya hai, aur yeh chat applications se lekar AI research tak ke use cases support karta hai. Ismein transparent pay-per-use pricing hai jo tokens pe based hai, aur kuch models free hain, jaise user guides mein likha hai ([Connecting to OpenRouter | Novelcrafter Help Center](https://docs.novelcrafter.com/en/articles/8678022-connecting-to-openrouter)). Features mein models test karne ke liye playground, optional prompt logging (opt-in), aur streaming support shamil hai, jo developer experience ko behtar banata hai. Platform ki routing strategy mein fallbacks aur load balancing hai, jo high availability ensure karta hai, aur advanced configurations bhi support karta hai jaise specific pricing ya parameter requirements ke mutabiq requests restrict karna.  

#### Comparative Analysis aur User Experience  
Users ke liye OpenRouter ki value iski cost-effectiveness aur wide model selection mein hai, jaise documentation aur user feedback mein likha hai ([OpenRouter + LangChain: Leverage OpenSource models without the Ops hassle](https://medium.com/%40gal.peretz/openrouter-langchain-leverage-opensource-models-without-the-ops-hassle-9ffbf0016da7)). Chatroom interface kuch standalone AI chat tools jaisa feature-rich nahi hai, lekin models test karne ka practical tareeka deta hai, aur API ki OpenAI ke saath compatibility se developers ke liye entry asaan hai. Lekin users ko yeh dhyan rakhna chahiye ke kuch models ke liye credits chahiye, aur free tiers jaldi khatam ho sakte hain, jisse premium access ke liye top-ups chahiye hote hain.  

#### Table: OpenRouter Features Summary  

| Feature                  | Description                                                                 |  
|--------------------------|-----------------------------------------------------------------------------|  
| User Interface           | Chatroom hai LLMs se baat karne ke liye, account management tools bhi hain  |  
| API Compatibility        | OpenAI Chat Completion API ke saath compatible, OpenAI SDK support karta hai|  
| Function Calling         | Tool calling support karta hai, compatible models aur providers ke liye     |  
| Model Hosting            | Proxy ke tor pe kaam karta hai, third-party providers ko route karta hai    |  
| Pricing Model            | Tokens pe based pay-per-use, kuch models free, transparent pricing         |  
| Additional Features      | Testing ke liye playground, streaming support, optional prompt logging     |  

Yeh detailed overview ensure karta hai ke users ko OpenRouter ko effectively use karne ke liye sab details mil jayein, jo March 2025 tak AI development mein kaafi famous ho chuka hai.  

---

### Key Citations  
- [OpenRouter Official Website A unified interface for LLMs](https://openrouter.ai/)  
- [OpenRouter Quickstart Guide Get started with OpenRouter's unified API](https://openrouter.ai/docs/quickstart)  
- [OpenRouter Tool Calling Documentation Use tools with OpenRouter](https://openrouter.ai/docs/features/tool-calling)  
- [Reddit Discussion on OpenRouter ELI5 how does OpenRouter work](https://www.reddit.com/r/ChatGPTCoding/comments/1fdwegx/eli5_how_does_openrouter_work/)  
- [Medium Article on OpenRouter and LangChain Leverage OpenSource models](https://medium.com/%40gal.peretz/openrouter-langchain-leverage-opensource-models-without-the-ops-hassle-9ffbf0016da7)  
- [Connecting to OpenRouter Novelcrafter Help Center](https://docs.novelcrafter.com/en/articles/8678022-connecting-to-openrouter)  
- [Provider Routing OpenRouter Documentation Intelligent Multi-Provider](https://openrouter.ai/docs/features/provider-routing)  

---

### OpenRouter pe Free Models Kya Hain?  
OpenRouter ek unified interface ke zariye bohat saare large language models (LLMs) tak access deta hai, aur inmein se kuch models free hain. Yeh free models bina kisi cost ke use kiye ja sakte hain, lekin inke rate limits hote hain, jaise 20 requests per minute aur 200 requests per day, usage manage karne ke liye.  

### Kitne Free Models Hain?  
OpenRouter ke official account ke ek recent X post ke mutabiq, jo March 23, 2025 ko post hua, abhi 50 free models hain. Ismein 6 models aise hain jinke context windows 1 million tokens ya zyada ke hain, jo users ke liye unexpected detail hai jo high-capacity free options chahte hain.  

---

### Survey Note: OpenRouter pe Free Models ke Comprehensive Details  
March 24, 2025 tak, OpenRouter, jo ek unified interface deta hai large language models (LLMs) tak access ke liye, kuch models free mein deta hai. Yeh section free models ki tadaad, unki khasiyat, aur availability ke context ki detail mein jaankari deta hai, taake developers, researchers, aur enthusiasts ko ache se samajh aaye.  

#### OpenRouter aur Free Models ka Overview  
OpenRouter ek proxy ke tor pe kaam karta hai, API requests ko third-party providers ke models tak route karta hai, khud models host nahi karta. Is tareeke se yeh 200 se zyada models tak access deta hai, jismein se kuch free hain, matlab users inhe bina token-based cost ke use kar sakte hain. Lekin free models ke usage limits hote hain, jaise 20 requests per minute aur 200 requests per day, jo API rate limits documentation mein likha hai ([API Rate Limits - Manage Model Usage and Quotas](https://openrouter.ai/docs/api-reference/limits)). Yeh limits fair access aur server load manage karne ke liye hain, khas tor pe free models ke liye, jo aksar ":free" ke saath ID mein end hote hain.  

#### Free Models ki Tadaad  
March 2025 tak, OpenRouter pe 50 free models hain. Yeh number OpenRouter ke official account ke ek X post se aaya hai ([OpenRouterAI X post](https://x.com/OpenRouterAI/status/1903860163888427051)), jismein likha tha, "Ab OpenRouter pe 50 free models hain jismein 6 ke context windows 1M+ ke hain!" Yeh post March 23, 2025 ko subah 10:23 AM PDT pe publish hui thi, aur recent hai, aur @TonyLovesAI ke ek X post se bhi confirm hota hai jo usi din 3:44 PM PDT pe post hua, jismein likha tha, "OpenRouter aapko 50 free AI models deta hai!" ([TonyLovesAI X post](https://x.com/TonyLovesAI/status/1903940942265999615)).  

Yeh number important hai, kyunki ismein 6 models aise hain jo 1 million tokens ya zyada ke context windows dete hain, jo high-capacity models chahte hain un users ke liye kaafi faida hai bina cost ke.  

#### Usage aur Limitations  
OpenRouter pe free models personal projects ya kam usage wale scenarios ke liye perfect hain, jaise @lucifer_x007 ke ek X post mein likha hai jo March 23, 2025 ko subah 10:38 AM PDT pe post hua, jismein suggestion di, "Agar aapko lagta hai ke aap rate limited ho jaoge toh OpenRouter ke free tier models use karo" ([lucifer_x007 X post](https://x.com/lucifer_x007/status/1903864054588014976)). Yeh API rate limits ke saath match karta hai, jo usage manage karne ke liye restrictions lagata hai, taake free access providers pe zyada load na daale.  

Ek aur X post @geekbb ka, jo December 29, 2024 ko raat 9:02 PM PST pe post hua, mention karta hai ke Gemini models OpenRouter pe free the 20 requests per minute aur 200 per day ke limits ke saath, jo trade-offs ko aur clear karta hai ([geekbb X post](https://x.com/geekbb/status/1873595494381019504)). Yeh limitations users ke liye samajhna zaroori hai, kyunki yeh project scalability pe asar daal sakte hain, lekin bohat logon ke liye 50 free models, jismein high-context options bhi hain, ek bada resource hai.  

#### Table: OpenRouter pe Free Models ka Summary  

| Aspect                  | Details                                                                 |  
|-------------------------|-------------------------------------------------------------------------|  
| Number of Free Models   | March 23, 2025 ke recent X posts ke mutabiq 50 hain                     |  
| Context Windows         | 6 models 1M+ context windows ke saath, jo high-capacity ke liye hai     |  
| Usage Limits            | 20 requests per minute, 200 requests per day free models ke liye        |  
| Identification          | Aksar IDs ":free" ke saath end hote hain, jaise OpenChat 3.5 (free)     |  
| Community Feedback      | Users kehte hain free models RP, personal projects ke liye ache hain    |  

#### Comparative Analysis aur User Experience  
Users ke liye 50 free models ki availability ek badi baat hai, khas tor pe high-context models ke saath, jo free tiers mein aksar nahi milta. Community feedback, jaise Make Community post jo June 7, 2024 ko aaya, OpenRouter ko "game-changer" kehta hai multiple free language models ek saath access karne ke liye ([How to Access Multiple Free AI Models at Once - Showcase - Make Community](https://community.make.com/t/how-to-access-multiple-free-ai-models-at-once/40751)), jo cost-conscious developers ke liye iski utility ko mazboot karta hai. Lekin users ko yeh dhyan rakhna chahiye ke kuch models, jaise OpenChat 3.5, free nahi hain kuch contexts mein, jo WordPress.org thread mein mention kiya gaya, jisse status mein changes ya discrepancies ho sakte hain.  

#### Conclusion  
March 2025 tak, OpenRouter pe 50 free models hain, jismein 6 ke context windows 1 million+ ke hain, jo kam ya moderate usage wale users ke liye bohat value dete hain. In models ke rate limits hain, lekin inki availability, jo official account ke recent X posts se confirm hoti hai, OpenRouter ko LLMs tak bina cost ke access ke liye ek acha option banati hai.  

---

### Key Citations  
- [Models | OpenRouter](https://openrouter.ai/models)  
- [OpenRouter Models | Access 300+ AI Models Through One API](https://openrouter.ai/docs/overview/models)  
- [API Rate Limits - Manage Model Usage and Quotas](https://openrouter.ai/docs/api-reference/limits)  
- [Use OpenRouter Models](https://docs.typingmind.com/chat-models-settings/use-openrouter-models)  
- [OpenRouter free models – not free? | WordPress.org](https://wordpress.org/support/topic/openrouter-free-models-not-free/)  
- [r/SillyTavernAI on Reddit: Free RP models on OpenRouter](https://www.reddit.com/r/SillyTavernAI/comments/17uvdmw/free_rp_models_on_openrouter/)  
- [How to Access Multiple Free AI Models at Once - Showcase - Make Community](https://community.make.com/t/how-to-access-multiple-free-ai-models-at-once/40751)  
- [OpenRouterAI X post](https://x.com/OpenRouterAI/status/1903860163888427051)  
- [TonyLovesAI X post](https://x.com/TonyLovesAI/status/1903940942265999615)  
- [lucifer_x007 X post](https://x.com/lucifer_x007/status/1903864054588014976)  
- [geekbb X post](https://x.com/geekbb/status/1873595494381019504)