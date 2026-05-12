<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0" />
<title>The Great Gatsby Birthday Soirée — RSVP</title>

<!-- Art Deco typography: Poiret One for headings, Cormorant Garamond for body -->
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Cormorant+Garamond:wght@400;500;600&family=Limelight&family=Poiret+One&display=swap" rel="stylesheet">

<style>
  /* ---------- Base & Theme ---------- */
  :root {
    --gold: #d4af37;
    --gold-light: #f1d97a;
    --gold-deep: #a8841f;
    --black: #0b0b0b;
    --black-soft: #161616;
    --ivory: #f5ecd7;
    --shadow: rgba(212, 175, 55, 0.35);
  }

  * { box-sizing: border-box; }

  html, body {
    margin: 0;
    padding: 0;
    background: var(--black);
    color: var(--ivory);
    font-family: 'Cormorant Garamond', Georgia, serif;
    font-size: 18px;
    line-height: 1.6;
    min-height: 100vh;
    overflow-x: hidden;
  }

  /* Subtle Art Deco radial backdrop */
  body::before {
    content: "";
    position: fixed;
    inset: 0;
    background:
      radial-gradient(ellipse at top, rgba(212,175,55,0.08), transparent 60%),
      radial-gradient(ellipse at bottom, rgba(212,175,55,0.05), transparent 60%),
      repeating-linear-gradient(
        45deg,
        rgba(212,175,55,0.025) 0 2px,
        transparent 2px 12px
      );
    pointer-events: none;
    z-index: 0;
  }

  /* ---------- Layout ---------- */
  .stage {
    position: relative;
    z-index: 1;
    max-width: 760px;
    margin: 0 auto;
    padding: 48px 24px 80px;
  }

  /* ---------- Deco Frame ---------- */
  .frame {
    border: 2px solid var(--gold);
    padding: 48px 36px;
    position: relative;
    background: linear-gradient(180deg, #111 0%, #0a0a0a 100%);
    box-shadow:
      0 0 0 6px var(--black),
      0 0 0 7px var(--gold-deep),
      0 30px 80px rgba(0,0,0,0.6);
  }

  /* Inner thin gold border */
  .frame::before {
    content: "";
    position: absolute;
    inset: 10px;
    border: 1px solid var(--gold-deep);
    pointer-events: none;
  }

  /* Decorative corner fans */
  .corner {
    position: absolute;
    width: 60px;
    height: 60px;
    border: 1px solid var(--gold);
    opacity: 0.9;
  }
  .corner.tl { top: -2px; left: -2px; border-right: none; border-bottom: none; }
  .corner.tr { top: -2px; right: -2px; border-left: none; border-bottom: none; }
  .corner.bl { bottom: -2px; left: -2px; border-right: none; border-top: none; }
  .corner.br { bottom: -2px; right: -2px; border-left: none; border-top: none; }

  /* ---------- Header / Title ---------- */
  .eyebrow {
    text-align: center;
    letter-spacing: 0.5em;
    font-size: 0.75rem;
    color: var(--gold);
    text-transform: uppercase;
    margin-bottom: 18px;
    font-family: 'Poiret One', sans-serif;
  }

  .ornament {
    display: flex;
    align-items: center;
    justify-content: center;
    gap: 14px;
    margin: 14px 0 18px;
    color: var(--gold);
  }
  .ornament .line {
    flex: 1;
    height: 1px;
    max-width: 120px;
    background: linear-gradient(90deg, transparent, var(--gold), transparent);
  }
  .ornament .diamond {
    width: 12px; height: 12px;
    background: var(--gold);
    transform: rotate(45deg);
    box-shadow: 0 0 12px var(--shadow);
  }

  h1.title {
    font-family: 'Limelight', 'Poiret One', serif;
    color: var(--gold);
    text-align: center;
    font-size: clamp(2.2rem, 6vw, 3.6rem);
    letter-spacing: 0.08em;
    margin: 8px 0 6px;
    line-height: 1.1;
    text-shadow: 0 2px 18px rgba(212,175,55,0.25);
  }

  h2.subtitle {
    text-align: center;
    font-family: 'Poiret One', sans-serif;
    font-weight: 400;
    color: var(--ivory);
    letter-spacing: 0.3em;
    text-transform: uppercase;
    font-size: 0.95rem;
    margin: 0 0 8px;
  }

  .date-block {
    text-align: center;
    margin: 26px 0 8px;
  }
  .date-block .date {
    font-family: 'Limelight', serif;
    color: var(--gold-light);
    font-size: clamp(1.4rem, 4vw, 2rem);
    letter-spacing: 0.12em;
  }
  .date-block .meta {
    color: var(--ivory);
    font-style: italic;
    margin-top: 4px;
    opacity: 0.85;
  }

  .invite-copy {
    text-align: center;
    font-style: italic;
    max-width: 520px;
    margin: 22px auto 8px;
    color: var(--ivory);
    opacity: 0.9;
  }

  /* ---------- Form ---------- */
  form {
    margin-top: 32px;
  }

  .field {
    margin-bottom: 20px;
  }

  label {
    display: block;
    font-family: 'Poiret One', sans-serif;
    letter-spacing: 0.25em;
    text-transform: uppercase;
    font-size: 0.78rem;
    color: var(--gold);
    margin-bottom: 8px;
  }

  .req::after {
    content: " *";
    color: var(--gold-light);
  }

  input[type="text"],
  input[type="email"],
  input[type="number"],
  select,
  textarea {
    width: 100%;
    padding: 12px 14px;
    background: rgba(0,0,0,0.55);
    border: 1px solid var(--gold-deep);
    color: var(--ivory);
    font-family: 'Cormorant Garamond', serif;
    font-size: 1.05rem;
    transition: border-color 0.25s, box-shadow 0.25s;
    border-radius: 0;
    outline: none;
  }

  textarea {
    min-height: 100px;
    resize: vertical;
  }

  input:focus, select:focus, textarea:focus {
    border-color: var(--gold);
    box-shadow: 0 0 0 2px rgba(212,175,55,0.25);
  }

  /* RSVP radio-as-pill choices */
  .choices {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 10px;
  }
  .choices input[type="radio"] {
    position: absolute;
    opacity: 0;
    pointer-events: none;
  }
  .choices label.choice {
    display: block;
    text-align: center;
    padding: 14px 8px;
    border: 1px solid var(--gold-deep);
    cursor: pointer;
    letter-spacing: 0.18em;
    font-size: 0.8rem;
    color: var(--ivory);
    transition: all 0.25s ease;
    background: rgba(0,0,0,0.4);
    margin-bottom: 0;
  }
  .choices label.choice:hover {
    border-color: var(--gold);
    color: var(--gold-light);
  }
  .choices input[type="radio"]:checked + label.choice {
    background: linear-gradient(180deg, var(--gold), var(--gold-deep));
    color: var(--black);
    border-color: var(--gold-light);
    box-shadow: 0 0 18px rgba(212,175,55,0.4);
    font-weight: 600;
  }

  /* Guest-count row reveals only when "Attending" is chosen */
  .guests-row {
    max-height: 0;
    overflow: hidden;
    opacity: 0;
    transition: max-height 0.45s ease, opacity 0.4s ease, margin 0.3s ease;
    margin-bottom: 0;
  }
  .guests-row.open {
    max-height: 160px;
    opacity: 1;
    margin-bottom: 20px;
  }

  /* Submit button */
  .submit-row {
    text-align: center;
    margin-top: 8px;
  }

  button.submit {
    background: linear-gradient(180deg, var(--gold-light) 0%, var(--gold) 50%, var(--gold-deep) 100%);
    color: var(--black);
    border: none;
    padding: 14px 42px;
    font-family: 'Poiret One', sans-serif;
    letter-spacing: 0.35em;
    text-transform: uppercase;
    font-size: 0.95rem;
    font-weight: 700;
    cursor: pointer;
    position: relative;
    box-shadow:
      0 0 0 1px var(--black),
      0 0 0 2px var(--gold),
      0 8px 30px rgba(212,175,55,0.3);
    transition: transform 0.2s ease, box-shadow 0.25s ease;
  }
  button.submit:hover {
    transform: translateY(-1px);
    box-shadow:
      0 0 0 1px var(--black),
      0 0 0 2px var(--gold-light),
      0 10px 36px rgba(212,175,55,0.45);
  }
  button.submit:active { transform: translateY(1px); }

  /* Validation error text */
  .error {
    color: #ffb4b4;
    font-size: 0.9rem;
    margin-top: 6px;
    font-style: italic;
    min-height: 1em;
  }

  /* ---------- Confirmation Screen ---------- */
  .confirmation {
    display: none;
    text-align: center;
    padding: 24px 8px;
    animation: fadeIn 0.8s ease both;
  }
  .confirmation.show { display: block; }
  .confirmation h3 {
    font-family: 'Limelight', serif;
    color: var(--gold);
    font-size: clamp(1.8rem, 5vw, 2.6rem);
    letter-spacing: 0.08em;
    margin: 8px 0 4px;
  }
  .confirmation p {
    margin: 6px 0;
  }
  .confirmation .summary {
    margin: 24px auto 0;
    max-width: 460px;
    border-top: 1px solid var(--gold-deep);
    border-bottom: 1px solid var(--gold-deep);
    padding: 18px 12px;
    color: var(--ivory);
    text-align: left;
  }
  .confirmation .summary div { margin: 6px 0; }
  .confirmation .summary span.label {
    color: var(--gold);
    font-family: 'Poiret One', sans-serif;
    letter-spacing: 0.18em;
    text-transform: uppercase;
    font-size: 0.75rem;
    margin-right: 8px;
  }

  /* ---------- Footer ---------- */
  footer.signoff {
    text-align: center;
    margin-top: 28px;
    color: var(--gold);
    font-family: 'Poiret One', sans-serif;
    letter-spacing: 0.4em;
    text-transform: uppercase;
    font-size: 0.7rem;
    opacity: 0.85;
  }

  /* ---------- Animations ---------- */
  @keyframes fadeIn {
    from { opacity: 0; transform: translateY(8px); }
    to   { opacity: 1; transform: translateY(0); }
  }
  @keyframes shimmer {
    0%   { text-shadow: 0 0 6px rgba(212,175,55,0.15); }
    50%  { text-shadow: 0 0 18px rgba(212,175,55,0.55); }
    100% { text-shadow: 0 0 6px rgba(212,175,55,0.15); }
  }
  h1.title { animation: shimmer 4.5s ease-in-out infinite; }

  /* ---------- Responsive ---------- */
  @media (max-width: 560px) {
    .stage { padding: 24px 14px 60px; }
    .frame { padding: 32px 18px; }
    .choices { grid-template-columns: 1fr; }
    .ornament .line { max-width: 60px; }
  }
</style>
</head>
<body>

<!-- Main stage container -->
<main class="stage">
  <section class="frame" aria-labelledby="event-title">
    <!-- Decorative corner accents -->
    <span class="corner tl" aria-hidden="true"></span>
    <span class="corner tr" aria-hidden="true"></span>
    <span class="corner bl" aria-hidden="true"></span>
    <span class="corner br" aria-hidden="true"></span>

    <!-- ===== Header ===== -->
    <p class="eyebrow">You are cordially invited</p>

    <div class="ornament" aria-hidden="true">
      <span class="line"></span>
      <span class="diamond"></span>
      <span class="line"></span>
    </div>

    <h1 class="title" id="event-title">A Gatsby Soirée</h1>
    <h2 class="subtitle">A Birthday Celebration</h2>

    <div class="date-block">
      <div class="date">Friday &middot; May 15, 2026</div>
      <div class="meta">Cocktails at eight &middot; Black-tie &amp; sequins encouraged</div>
    </div>

    <p class="invite-copy">
      “In his blue gardens men and girls came and went like moths
      among the whisperings and the champagne and the stars.”
      Join us for an evening of jazz, gilded glamour, and good company.
    </p>

    <div class="ornament" aria-hidden="true">
      <span class="line"></span>
      <span class="diamond"></span>
      <span class="line"></span>
    </div>

    <!-- ===== RSVP Form ===== -->
    <form id="rsvpForm" novalidate>
      <!-- Guest name -->
      <div class="field">
        <label for="name" class="req">Your Name</label>
        <input type="text" id="name" name="name" autocomplete="name" placeholder="e.g. Jay Gatsby" />
        <div class="error" id="err-name" aria-live="polite"></div>
      </div>

      <!-- Email (optional) -->
      <div class="field">
        <label for="email">Email (optional)</label>
        <input type="email" id="email" name="email" autocomplete="email" placeholder="old.sport@westegg.com" />
        <div class="error" id="err-email" aria-live="polite"></div>
      </div>

      <!-- RSVP status (radio pills) -->
      <div class="field">
        <label class="req">Will you attend?</label>
        <div class="choices" role="radiogroup" aria-label="RSVP status">
          <input type="radio" id="rsvp-yes" name="rsvp" value="Attending" />
          <label for="rsvp-yes" class="choice">Attending</label>

          <input type="radio" id="rsvp-no" name="rsvp" value="Not Attending" />
          <label for="rsvp-no" class="choice">Not Attending</label>

          <input type="radio" id="rsvp-maybe" name="rsvp" value="Maybe" />
          <label for="rsvp-maybe" class="choice">Maybe</label>
        </div>
        <div class="error" id="err-rsvp" aria-live="polite"></div>
      </div>

      <!-- Guest count — only visible when "Attending" is chosen -->
      <div class="guests-row" id="guestsRow">
        <label for="guests">Number of guests (including you)</label>
        <input type="number" id="guests" name="guests" min="1" max="10" value="1" />
        <div class="error" id="err-guests" aria-live="polite"></div>
      </div>

      <!-- Optional message -->
      <div class="field">
        <label for="message">A note to the host (optional)</label>
        <textarea id="message" name="message" placeholder="Leave a kind word, a song request, or a fond memory..."></textarea>
      </div>

      <!-- Submit -->
      <div class="submit-row">
        <button type="submit" class="submit">Send my reply</button>
      </div>
    </form>

    <!-- ===== Confirmation (hidden until submit) ===== -->
    <div class="confirmation" id="confirmation" aria-live="polite">
      <div class="ornament" aria-hidden="true">
        <span class="line"></span>
        <span class="diamond"></span>
        <span class="line"></span>
      </div>
      <h3 id="confirmHeading">Thank you, old sport.</h3>
      <p id="confirmBody">Your reply has been received.</p>
      <div class="summary" id="summary"></div>
      <p style="margin-top:22px;font-style:italic;opacity:0.85;">
        We shall see you among the stars on May 15th.
      </p>
    </div>

    <footer class="signoff">— Black tie &middot; Champagne &middot; Charleston —</footer>
  </section>
</main>

<script>
  /* =========================================================
     RSVP Form — client-side validation + confirmation
     ========================================================= */
  (function () {
    const form     = document.getElementById('rsvpForm');
    const confirmation = document.getElementById('confirmation');
    const guestsRow    = document.getElementById('guestsRow');

    // Show/hide the guests row based on RSVP choice
    document.querySelectorAll('input[name="rsvp"]').forEach((radio) => {
      radio.addEventListener('change', () => {
        if (radio.checked && radio.value === 'Attending') {
          guestsRow.classList.add('open');
        } else {
          guestsRow.classList.remove('open');
        }
      });
    });

    // Simple email pattern (good-enough, not RFC-perfect)
    const emailRe = /^[^\s@]+@[^\s@]+\.[^\s@]+$/;

    // Clear any previous error messages
    function clearErrors() {
      ['name','email','rsvp','guests'].forEach((id) => {
        const el = document.getElementById('err-' + id);
        if (el) el.textContent = '';
      });
    }

    // Run validation and return an object of values, or null if invalid
    function validate() {
      clearErrors();
      let ok = true;

      const name   = document.getElementById('name').value.trim();
      const email  = document.getElementById('email').value.trim();
      const rsvpEl = document.querySelector('input[name="rsvp"]:checked');
      const guests = parseInt(document.getElementById('guests').value, 10);
      const message= document.getElementById('message').value.trim();

      // Name is required
      if (!name) {
        document.getElementById('err-name').textContent = 'Please share your name.';
        ok = false;
      }

      // Email is optional, but if provided must look valid
      if (email && !emailRe.test(email)) {
        document.getElementById('err-email').textContent = 'That email does not look quite right.';
        ok = false;
      }

      // RSVP choice is required
      if (!rsvpEl) {
        document.getElementById('err-rsvp').textContent = 'Kindly choose a reply.';
        ok = false;
      }

      // If attending, guest count must be 1–10
      if (rsvpEl && rsvpEl.value === 'Attending') {
        if (!Number.isFinite(guests) || guests < 1 || guests > 10) {
          document.getElementById('err-guests').textContent = 'Please enter between 1 and 10 guests.';
          ok = false;
        }
      }

      if (!ok) return null;
      return {
        name,
        email,
        rsvp: rsvpEl.value,
        guests: rsvpEl.value === 'Attending' ? guests : null,
        message
      };
    }

    // Build the confirmation summary block
    function renderSummary(data) {
      const heading = document.getElementById('confirmHeading');
      const body    = document.getElementById('confirmBody');

      if (data.rsvp === 'Attending') {
        heading.textContent = `We'll see you there, ${data.name.split(' ')[0]}.`;
        body.textContent    = 'Your seat at the soirée is reserved.';
      } else if (data.rsvp === 'Not Attending') {
        heading.textContent = `Thank you, ${data.name.split(' ')[0]}.`;
        body.textContent    = 'We shall miss you dearly. Raise a glass with us in spirit.';
      } else {
        heading.textContent = `Noted, ${data.name.split(' ')[0]}.`;
        body.textContent    = 'We hope the stars align in your favor.';
      }

      const lines = [
        ['Name',   data.name],
        ['Email',  data.email || '—'],
        ['Reply',  data.rsvp],
      ];
      if (data.guests) lines.push(['Guests', data.guests]);
      if (data.message) lines.push(['Note',  data.message]);

      const summary = document.getElementById('summary');
      summary.innerHTML = lines.map(([k, v]) =>
        `<div><span class="label">${k}</span> ${escapeHTML(String(v))}</div>`
      ).join('');
    }

    // Tiny HTML escaper for the summary
    function escapeHTML(str) {
      return str.replace(/[&<>"']/g, (c) => ({
        '&':'&amp;','<':'&lt;','>':'&gt;','"':'&quot;',"'":'&#39;'
      }[c]));
    }

    // Handle form submission (no backend — purely client-side)
    form.addEventListener('submit', (e) => {
      e.preventDefault();
      const data = validate();
      if (!data) return;

      renderSummary(data);
      form.style.display = 'none';
      confirmation.classList.add('show');
      confirmation.scrollIntoView({ behavior: 'smooth', block: 'start' });
    });
  })();
</script>
</body>
</html>
