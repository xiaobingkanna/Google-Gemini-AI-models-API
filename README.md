# Google-Gemini-AI-models-API
It's just learning and entertainment.
新发布的开源免费模型
搞来玩玩

代码解释


generation_config = {

    "temperature": 0.9,
    
    "top_p": 1,
    
    "top_k": 1,
    
    "max_output_tokens": 2048,
    
    这段代码定义了生成模型的配置参数。

temperature（温度）:

温度可以控制生成模型输出多样性的参数。

范围：(0, 1]

较高的温度值（例如0.9）会导致生成的文本更加随机和多样化，但可能会失去一些逻辑性。

较低的温度值（例如0.1）会使生成的文本更加确定性和保守，更符合模型的预训练数据。


top_p（nucleus采样的概率阈值）:

top_p 是 nucleus sampling（核心采样）的参数。它控制从概率分布中选择概率总和最高的 tokens。

较高的 top_p 值表示更多的 token 可以被考虑在内，可能导致更多的多样性。


top_k（top-k采样）:

范围：(0, 1] 。 表示考虑概率分布中的所有 token，而较小的值表示只考虑累积概率达到某个阈值的 token。

top_k 是 top-k sampling（前k个最高概率的token被保留）的参数。它限制了模型考虑的概率最高的 tokens 的数量。

较小的 top_k 值意味着只有最高概率的 tokens 被考虑在内，可能导致生成的文本更加保守和确定性。


max_output_tokens（最大输出 tokens 数）:

范围：(1, ∞) 。表示保留最高概率的前 k 个 token。

限制生成的文本的最大长度，以避免生成过长的输出。


通过增加 top_p 和 top_k 的值，例如将它们设置为 0.9 和 10，模型将在更多的候选单词中进行随机选择。这样的设置有助于增加生成文本的多样性，使得模型在选择下一个单词时更具有随机性，从而生成更为丰富和多样的内容。

这些参数一起影响了模型生成文本的风格和质量。调整这些参数可以根据你的需求获得更好的生成效果。



而

safety_settings = [

    {"category": "HARM_CATEGORY_HARASSMENT", "threshold": "BLOCK_NONE"},
    
    {"category": "HARM_CATEGORY_HATE_SPEECH", "threshold": "BLOCK_NONE"},
    
    {"category": "HARM_CATEGORY_SEXUALLY_EXPLICIT", "threshold": "BLOCK_NONE"},
    
    {"category": "HARM_CATEGORY_DANGEROUS_CONTENT", "threshold": "BLOCK_NONE"}
    
]


这段代码则是定义了一个名为 safety_settings 的列表，其中包含了用于设置生成模型的安全性设置的一组规则。每个规则都是一个字典，包含两个键值对：

category"：
表示生成文本中可能出现的内容的类别。在这里，有四个类别：

"HARM_CATEGORY_HARASSMENT"（骚扰）

"HARM_CATEGORY_HATE_SPEECH"（仇恨言论）

"HARM_CATEGORY_SEXUALLY_EXPLICIT"（性暗示内容）

"HARM_CATEGORY_DANGEROUS_CONTENT"（危险内容）


"threshold"：

表示对于给定类别的内容，模型设置的阈值。在这里，阈值设置为 "BLOCK_NONE"，这可能表示模型会在不会对任何可能有害内容时进行阻止。

相应的，想要屏蔽什么内容，就将上述代码中BLOCK_NONE改成对应的阈值设置即可，例如{"category": "HARM_CATEGORY_HARASSMENT", "threshold": "HARM_CATEGORY_HARASSMENT"},



其他没啥好说的
