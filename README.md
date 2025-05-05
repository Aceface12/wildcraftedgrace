<!DOCTYPE html><html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Wildcrafted Grace</title>
  <!-- Brand Fonts -->
  <link href="https://fonts.googleapis.com/css2?family=Great+Vibes&family=Playlist+Script&family=Playfair+Display:wght@400;700&family=Libre+Baskerville:wght@400;700&display=swap" rel="stylesheet">
  <style>
    :root {
      --sage: #7A8D74;
      --lavender: #8E7D9A;
      --cream: #F9F7F3;
      --text: #333333;
      --bg: var(--cream);
      --accent: var(--sage);
    }
    * { box-sizing: border-box; margin: 0; padding: 0; }
    body { font-family: 'Libre Baskerville', serif; background: var(--bg); color: var(--text); }
    header { text-align: center; padding: 3rem 1rem; }
    .logo { font-family: 'Great Vibes', 'Playlist Script', cursive; font-size: 3rem; color: var(--sage); position: relative; display: inline-block; }
    .logo::before { content: '✝'; position: absolute; top: -1.5rem; left: 50%; transform: translateX(-50%); font-size: 1.5rem; opacity: 0.5; }
    .logo::after { content: '✦'; position: absolute; top: -1.5rem; right: -1rem; font-size: 1rem; opacity: 0.7; }
    .tagline { font-family: 'Playfair Display', serif; font-size: 1.25rem; color: var(--lavender); margin-top: 0.5rem; }
    nav { margin: 2rem 0; text-align: center; }
    nav a { margin: 0 0.5rem; padding: 0.5rem 1rem; background: var(--accent); color: #fff; text-decoration: none; border-radius: 6px; font-family: 'Playfair Display', serif; transition: background 0.3s; }
    nav a:hover { background: var(--lavender); }
    main { max-width: 1200px; margin: 0 auto; padding: 0 1rem; display: grid; gap: 3rem; }
    section { background: #fff; padding: 2rem; border-radius: 12px; box-shadow: 0 2px 12px rgba(0,0,0,0.1); }
    h2 { font-family: 'Playfair Display', serif; color: var(--sage); margin-bottom: 1rem; }
    p { margin-bottom: 1rem; line-height: 1.6; }
    .btn { display: inline-block; margin-top: 1rem; padding: 0.75rem 1.5rem; font-family: 'Playfair Display', serif; background: var(--accent); color: #fff; text-decoration: none; border-radius: 8px; transition: background 0.3s ease; }
    .btn:hover { background: var(--lavender); }
    .grid-2 { display: grid; grid-template-columns: 1fr; gap: 1rem; }
    @media(min-width:768px) { .grid-2 { grid-template-columns: 1fr 1fr; } }
    .gallery { display: grid; grid-template-columns: repeat(auto-fit, minmax(150px, 1fr)); gap: 1rem; }
    .gallery img { width: 100%; border-radius: 8px; transition: transform 0.3s ease; cursor: pointer; }
    .gallery img:hover { transform: scale(1.05); }
    .signup input[type="email"] { width: 100%; padding: 0.75rem; border: 1px solid #ccc; border-radius: 6px; }
    .signup form { display: flex; flex-direction: column; align-items: center; }
    /* Chatbot Styles */
    #chatbot-container { position: fixed; bottom: 1.5rem; right: 1.5rem; z-index: 1000; }
    #chatbot-toggle { background: var(--accent); color: #fff; border: none; padding: 0.75rem 1rem; border-radius: 50px; cursor: pointer; box-shadow: 0 2px 6px rgba(0,0,0,0.2); transition: background .3s; }
    #chatbot-toggle:hover { background: var(--lavender); }
    #chatbot-widget { display: none; width: 300px; max-height: 400px; background: #fff; border-radius: 12px; box-shadow: 0 2px 12px rgba(0,0,0,0.2); overflow: hidden; margin-top: 0.5rem; }
    #chatbot-header { background: var(--sage); color: #fff; padding: 0.75rem; font-weight: bold; }
    #chatbot-messages { padding: 1rem; height: 280px; overflow-y: auto; }
    #chatbot-input { display: flex; border-top: 1px solid #ddd; }
    #chatbot-input input { flex: 1; padding: 0.75rem; border: none; }
    #chatbot-input button { background: var(--accent); color: #fff; border: none; padding: 0 1rem; cursor: pointer; }
  </style>
</head>
<body>
  <header>
    <div class="logo">Wildcrafted Grace</div>
    <div class="tagline">Faithfully Made. Wildly Rooted.</div>
    <nav>
      <a href="#devotional">Devotional</a>
      <a href="#ebook">eBook</a>
      <a href="#recipe">Recipe</a>
      <a href="#gallery">Gallery</a>
      <a href="#signup">Subscribe</a>
    </nav>
  </header>
  <main>
    <section id="devotional">
      <h2>✝ Daily Devotional</h2>
      <p><!-- {{ devotional_text }} --></p>
      <a href="#" class="btn">Read Today’s Devotional</a>
    </section>
    <section id="ebook" class="grid-2">
      <div>
        <h2>✦ Featured eBook</h2>
        <img src="ebook-placeholder.jpg" alt="eBook Cover" />
      </div>
      <div>
        <p><!-- {{ ebook_description }} --></p>
        <a href="#" class="btn">Download eBook</a>
      </div>
    </section>
    <section id="recipe">
      <h2>🍲 Recipe of the Day</h2>
      <div class="grid-2">
        <div><img src="recipe-placeholder.jpg" alt="Recipe Image" /></div>
        <div>
          <p><!-- {{ recipe_description }} --></p>
          <a href="#" class="btn">View Full Recipe</a>
        </div>
      </div>
    </section>
    <section id="gallery" class="gallery">
      <h2>🌿 Image Gallery</h2>
      <img src="gallery1.jpg" alt="Gallery Image" />
      <img src="gallery2.jpg" alt="Gallery Image" />
      <img src="gallery3.jpg" alt="Gallery Image" />
      <img src="gallery4.jpg" alt="Gallery Image" />
    </section>
    <section id="signup" class="signup">
      <h2>Stay Connected</h2>
      <form action="#" method="post">
        <input type="email" name="email" placeholder="Enter your email" required />
        <button type="submit" class="btn">Subscribe</button>
      </form>
    </section>
  </main>  <!-- Chatbot Toggle Widget -->  <div id="chatbot-container">
    <button id="chatbot-toggle">Chat With Us</button>
    <div id="chatbot-widget">
      <div id="chatbot-header">How can we help?</div>
      <div id="chatbot-messages"><!-- Messages appear here --></div>
      <div id="chatbot-input">
        <input type="text" placeholder="Type a message..." />
        <button>Send</button>
      </div>
    </div>
  </div>  <!-- Placeholder for automation script -->  <script>
    // Automation placeholder: fetch and insert dynamic content
    // Example:
    // fetch('/api/devotional/today').then(r=>r.json()).then(data=>{
    //   document.querySelector('#devotional p').innerText = data.text;
    // });
  </script>  <!-- Chatbot toggle logic -->  <script>
    const toggleBtn = document.getElementById('chatbot-toggle');
    const chatWidget = document.getElementById('chatbot-widget');
    toggleBtn.addEventListener('click', () => {
      chatWidget.style.display = chatWidget.style.display === 'block' ? 'none' : 'block';
    });
  </script></body>
</html>
