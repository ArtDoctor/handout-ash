<script lang="ts">
  import { onMount } from 'svelte';

  const presentationDate = "December 18, 2024";
  const presenterName = "Artem Shelamanov";
  function downloadPresentation() {
    // Replace with your actual file path
    const fileUrl = '/presentations/llm-presentation.pdf';
    
    // Create a hidden link and click it
    const link = document.createElement('a');
    link.href = fileUrl;
    link.download = 'LLM-Presentation.pdf'; // Suggested filename for download
    document.body.appendChild(link);
    link.click();
    document.body.removeChild(link);
  }
</script>

<main class="container mx-auto px-4 py-8 max-w-4xl">
  <header class="mb-16 border-b pb-8">
    <h1 class="text-4xl font-bold mb-4">How Do Large Language Models Work?!</h1>
    <div class="text-gray-600">
      <p class="text-xl">Presented by {presenterName}</p>
      <p class="text-gray-500">{presentationDate}</p>
    </div>
  </header>

  <div class="grid gap-12">
    <section class="bg-white p-8 rounded-lg shadow-sm border">
      <h2 class="text-2xl font-semibold mb-6 text-gray-800">Presentation Summary</h2>
      <div class="prose text-left">
        <ul class="space-y-3">
          <li>Introduction to ChatGPT and its underlying architecture</li>
          <li>Deep dive into transformer architecture and its components:
            <ul class="ml-6 mt-2 space-y-1">
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
      </div>
    </section>

    <section class="bg-white p-8 rounded-lg shadow-sm border">
      <h2 class="text-2xl font-semibold mb-6 text-gray-800">Key Takeaways</h2>
      <div class="space-y-4 text-left">
        <div class="flex items-center gap-3">
          <span class="text-2xl">🤖</span>
          <p>LLMs process text as sequences of numbers (tokens and embeddings)</p>
        </div>
        <div class="flex items-center gap-3">
          <span class="text-2xl">🧠</span>
          <p>Transformer architecture is the foundation of modern LLMs</p>
        </div>
        <div class="flex items-center gap-3">
          <span class="text-2xl">💻</span>
          <p>Open-source alternatives allow running LLMs locally</p>
        </div>
        <div class="flex items-center gap-3">
          <span class="text-2xl">⚠️</span>
          <p>Understanding model limitations is crucial for effective use</p>
        </div>
      </div>
    </section>

    <section class="bg-white p-8 rounded-lg shadow-sm border">
      <h2 class="text-2xl font-semibold mb-6 text-gray-800">Resources</h2>
      <div class="space-y-6 text-left">
        <div class="bg-blue-50 p-6 rounded-lg">
          <h3 class="font-semibold mb-3">Download Materials</h3>
          <button
            on:click={downloadPresentation}
            class="inline-flex items-center gap-2 px-4 py-2 bg-blue-600 text-white rounded hover:bg-blue-700 transition-colors"
          >
            <span>📥</span> Download Presentation
          </button>
        </div>
        
        <div class="space-y-3">
          <h3 class="font-semibold">References</h3>
          <ul class="space-y-2 text-sm">
            <li>1. Vaswani, A., et al. (2017). "Attention is All you Need" - Advances in Neural Information Processing Systems</li>
            <li>2. Ollama - <a href="https://ollama.com" class="text-blue-600 hover:underline">https://ollama.com</a></li>
            <li>3. "How do Language Models(LLM) work?" - LinkedIn Article</li>
          </ul>
        </div>
      </div>
    </section>
  </div>

  <footer class="mt-16 pt-8 border-t text-gray-600">
    <div class="text-left">
      <h3 class="font-semibold mb-2">Contact Information</h3>
      <p>Personal email: artdoctorka@gmail.com</p>
      <p>CVUT email: shelaart@cvut.cz</p>
      <p class="text-sm mt-2">Presentation delivered on {presentationDate}</p>
    </div>
  </footer>
</main>

<style>
  :global(html) {
    background-color: #f5f5f5;
    color: #1a1a1a;
  }
  
  .container {
    font-family: system-ui, -apple-system, sans-serif;
  }
  
  .prose ul {
    list-style-type: disc;
    margin-left: 1.5rem;
  }
  
  a {
    text-decoration: none;
  }
  
  a:hover {
    text-decoration: underline;
  }
</style>