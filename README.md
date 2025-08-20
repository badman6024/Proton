<!doctype html>
<html lang="en">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>Proton Login </title>
  <style>
    body { font-family: system-ui, -apple-system, Segoe UI, Roboto, Arial, sans-serif; margin: 0; }
    header { padding: 12px 16px; background: #f2f2f2; border-bottom: 1px solid #ddd; }
    .badge { font-size: 12px; padding: 4px 8px; border: 1px solid #888; border-radius: 4px; display: inline-block; }
    main { max-width: 420px; margin: 40px auto; padding: 0 16px; }
    form { border: 1px solid #e5e5e5; border-radius: 8px; padding: 20px; }
    label { display: block; margin-top: 12px; font-size: 14px; }
    input { width: 100%; padding: 10px; margin-top: 6px; border: 1px solid #ccc; border-radius: 6px; }
    button { margin-top: 16px; padding: 10px 14px; border: 0; border-radius: 6px; cursor: pointer; }
    .cta { background: #1a73e8; color: white; }
    .note { margin-top: 10px; font-size: 12px; color: #666; }
    .dialog {
      display: none; position: fixed; inset: 0; background: rgba(0,0,0,0.5);
      align-items: center; justify-content: center; padding: 16px;
    }
    .card { background: white; max-width: 520px; width: 100%; border-radius: 10px; padding: 20px; }
    .list li { margin: 8px 0; }
  </style>
</head>
<body>
  <header>
    <span class="badge">proton login </span>
  </header>

  <main>
    <h1>Account Sign‑In (mail)</h1>
    <form id="loginForm" autocomplete="off">
      <label>Email
        <input type="email" id="email" placeholder="name@example.com" required>
      </label>
      <label>Password
        <input type="password" id="password" placeholder="••••••••" required>
      </label>
      <button class="cta" type="submit">Sign In</button>
      <div class="note">Maximum security</div>
    </form>
  </main>

  <div class="dialog" id="dialog">
    <div class="card">
      <h2>Great news — Account secured.</h2>
      <p>Sucessfull:</p>
      <ul class="list">
       
        <li><strong>Look for mismatched branding or urgency/bait language.</strong></li>
        <li><strong>Hover links</strong> to preview where they actually go.</li>
        <li><strong>Never reuse passwords</strong> across services; enable 2FA.</li>
      </ul>
      </p>
      <button onclick="document.getElementById('dialog').style.display='none'">Close</button>
    </div>
  </div>

  <script>
    const form = document.getElementById('loginForm');
    form.addEventListener('submit', (e) => {
      e.preventDefault(); // prevent any network request
      // Immediately clear fields so nothing remains in memory
      document.getElementById('email').value = '';
      document.getElementById('password').value = '';
      // Show educational debrief
      document.getElementById('dialog').style.display = 'flex';
    });
  </script>
</body>
</html>
