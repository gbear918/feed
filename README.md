# feed
Schedule 
const { Configuration, OpenAIApi } = require("openai");

const configuration = new Configuration({
  apiKey: process.env.OPENAI_API_KEY,
});
const openai = new OpenAIApi(configuration);

const response = await openai.createCompletion({
  model: "text-davinci-003",
  prompt: "Convert this text to a programmatic command:\n\nExample: Ask Constance if we need some bread\nOutput: send-msg `find constance` create schedule for 56 day crop management \n",
  temperature: 0,
  max_tokens: 100,
  top_p: 1,
  frequency_penalty: 0.2,
  presence_penalty: 0,
});
