<script lang="ts">
  const presentationDate = "December 18, 2024";
  const presenterName = "Artem Shelamanov";
  function downloadPresentation() {
    const fileUrl = '/presentations/llm-presentation.pdf';
    
    const link = document.createElement('a');
    link.href = fileUrl;
    link.download = 'llm-presentation.pdf';
    document.body.appendChild(link);
    link.click();
    document.body.removeChild(link);
  }
</script>

<main class="container mx-auto px-6 py-12 max-w-3xl">
  <header class="mb-12 border-b pb-6">
    <h1 class="text-3xl font-extrabold text-gray-800 mb-3">How Do Large Language Models Work?</h1>
    <div class="text-gray-600">
      <p class="text-lg">Presented by {presenterName}</p>
      <p class="text-sm">{presentationDate}</p>
    </div>
  </header>

  <div class="space-y-10">
    <section class="bg-white p-6 rounded-lg shadow-md">
      <h2 class="text-xl font-bold text-gray-700 mb-4">Presentation Summary</h2>
      <ul class="space-y-2 text-gray-600">
        <li>Introduction to ChatGPT and its underlying architecture</li>
        <li>Deep dive into transformer architecture and its components:
          <ul class="ml-6 list-disc space-y-1">
            <li>Encoder/Decoder structure</li>
            <li>Transformer blocks</li>
            <li>Attention mechanisms</li>
            <li>Feedforward neural networks</li>
            <li>Layer normalization</li>
          </ul>
        </li>
        <li>Understanding model inputs and outputs: from text to tokens to embeddings</li>
        <li>Available LLM alternatives (both commercial and open-source)</li>
        <li>Running LLMs locally using Ollama</li>
        <li>Limitations of LLMs (e.g., counting problem explanation)</li>
      </ul>
    </section>

    <section class="bg-white p-6 rounded-lg shadow-md">
      <h2 class="text-xl font-bold text-gray-700 mb-4">Key Takeaways</h2>
      <div class="space-y-3">
        <div class="flex items-start gap-3">
          <span class="text-2xl text-gray-700">🤖</span>
          <p class="text-gray-600">LLMs process text as sequences of numbers (tokens and embeddings)</p>
        </div>
        <div class="flex items-start gap-3">
          <span class="text-2xl text-gray-700">🧠</span>
          <p class="text-gray-600">Transformer architecture is the foundation of modern LLMs</p>
        </div>
        <div class="flex items-start gap-3">
          <span class="text-2xl text-gray-700">💻</span>
          <p class="text-gray-600">Open-source alternatives allow running LLMs locally</p>
        </div>
        <div class="flex items-start gap-3">
          <span class="text-2xl text-gray-700">⚠️</span>
          <p class="text-gray-600">Understanding model limitations is crucial for effective use</p>
        </div>
      </div>
    </section>

    <section class="bg-white p-6 rounded-lg shadow-md">
      <h2 class="text-xl font-bold text-gray-700 mb-4">Resources</h2>
      <div class="space-y-6">
        <div class="bg-gray-50 p-5 rounded-lg border">
          <h3 class="font-semibold text-gray-700 mb-2">Download Materials</h3>
          <button
            on:click={downloadPresentation}
            class="flex items-center gap-2 px-4 py-2 bg-blue-500 text-white rounded-md hover:bg-blue-600 transition"
          >
            <span>📥</span> Download Presentation
          </button>
        </div>

        <div class="space-y-2">
          <h3 class="font-semibold text-gray-700">References</h3>
          <ul class="list-disc pl-5 space-y-1 text-sm text-gray-600">
            <li>1. Vaswani, A., et al. (2017). "Attention is All You Need"</li>
            <li>2. Ollama - <a href="https://ollama.com" class="text-blue-500 hover:underline">https://ollama.com</a></li>
            <li>3. "How do Language Models (LLM) work?" - <a href="https://www.linkedin.com/pulse/how-do-language-modelsllm-work-we-call-chatgpt-mishra-fdqsc/" class="text-blue-500 hover:underline">LinkedIn Article</a></li>
            <li>4. ChatGPT Users - <a href="https://explodingtopics.com/blog/chatgpt-users%C2%A0" class="text-blue-500 hover:underline">Exploding Topics</a></li>
          </ul>
        </div>
      </div>
    </section>
  </div>

  <footer class="mt-12 pt-6 border-t text-sm text-gray-600">
    <h3 class="font-semibold mb-2 text-gray-700">Contact Information</h3>
    <p>CVUT email: shelaart@cvut.cz</p>
    <p>Presentation delivered on {presentationDate}</p>
  </footer>
</main>
<style>
  :global(html) {
    background-color: #1e1e1e;
    font-family: 'Inter', sans-serif;
    color: #e0e0e0;
  }

  .container {
    font-size: 16px;
    line-height: 1.6;
  }

  h1, h2 {
    color: #ffffff;
  }

  ul, li {
    list-style-type: disc;
    margin-left: 1.5rem;
    padding: 0.2rem 0;
  }

  a {
    color: #4aa3ff;
    text-decoration: none;
  }

  a:hover {
    text-decoration: underline;
  }

  button {
    background-color: #4aa3ff;
    color: #fff;
    border: none;
    padding: 0.8rem 1.5rem;
    border-radius: 0.5rem;
    cursor: pointer;
    transition: background-color 0.3s;
  }

  button:hover {
    background-color: #007acc;
  }

  section {
    background-color: #2a2a2a;
    padding: 1.5rem;
    border-radius: 0.75rem;
    margin-bottom: 1.5rem;
    box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2);
    text-align: left; /* Ensures content is left-aligned */
  }

  footer {
    text-align: center;
    margin-top: 2rem;
  }
</style>
