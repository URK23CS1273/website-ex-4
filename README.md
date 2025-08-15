/* ========= THEME ========= */
:root{
  --brand: #00e5c1;
  --brand-dark: #00b294;
  --ink: #0f1115;
  --ink-2: #1b1f2a;
  --paper: #ffffff;
  --muted: rgba(255,255,255,0.7);
  --glass: rgba(0,0,0,0.55);
  --glass-2: rgba(0,0,0,0.75);
  --shadow: 0 10px 30px rgba(0,0,0,0.45);
  --radius: 16px;
  --radius-sm: 10px;
  --transition: 220ms ease;
}

/* ========= RESET ========= */
*{ box-sizing: border-box; margin:0; padding:0; }
img{ max-width:100%; display:block; }
a{ text-decoration:none; }

/* ========= BASE ========= */
body{
  font-family: system-ui, -apple-system, Segoe UI, Roboto, Arial, sans-serif;
  color: #eaf6f4;
  background-image: url('headset-bg.jpg'); /* <- replace with your image */
  background-size: cover;
  background-position: center;
  background-attachment: fixed;
  min-height: 100vh;
}

/* Subtle vignette overlay for readability */
body::before{
  content:"";
  position: fixed; inset:0;
  background: radial-gradient(1200px 600px at 20% 10%, transparent 0 60%, rgba(0,0,0,0.55) 100%),
              linear-gradient(to bottom, rgba(0,0,0,0.35), rgba(0,0,0,0.65));
  pointer-events:none;
}

/* ========= NAVBAR ========= */
.navbar{
  position: fixed; top:0; left:0; right:0;
  background: rgba(10,14,18,0.85);
  backdrop-filter: blur(6px);
  display:flex; align-items:center; justify-content:space-between;
  padding: 10px 28px;
  z-index: 1000;
  border-bottom: 1px solid rgba(255,255,255,0.06);
}
.navbar img{ height:42px; filter: drop-shadow(0 2px 6px rgba(0,0,0,0.6)); }
.navbar .title{
  margin-left:10px; font-weight:800; font-size: 22px; letter-spacing: .3px;
  color: var(--brand);
}
.nav-links{ list-style:none; display:flex; gap:18px; }
.nav-links a{
  color:#e9fffb; padding:8px 14px; border-radius: 10px; transition: background var(--transition), color var(--transition), transform var(--transition);
}
.nav-links a:hover{ background: var(--brand); color:#06221d; transform: translateY(-1px); }
.nav-links a:focus{ outline: 2px solid var(--brand); outline-offset: 2px; }

/* ========= LANDING TEXT ========= */
.landing-text{
  margin-top: 120px; margin-left: 56px; max-width: 640px;
  background: var(--glass);
  padding: 36px; border-radius: var(--radius);
  box-shadow: var(--shadow);
}
.landing-text h1{
  font-size: 40px; line-height: 1.1; margin-bottom: 12px; color:#b8fff3;
}
.landing-text p{ color: var(--muted); font-size: 16px; }

/* ========= LOGIN FORM ========= */
.login-form{
  position: absolute; top: 150px; right: 56px; width: 340px;
  background: var(--glass-2);
  padding: 26px; border-radius: var(--radius);
  box-shadow: var(--shadow);
  border: 1px solid rgba(255,255,255,0.08);
}
.login-form h2{ text-align:center; margin-bottom:16px; color:#b8fff3; }

.login-form input[type="text"],
.login-form input[type="password"],
.login-form input[type="email"]{
  width:100%; padding: 12px 14px; margin-bottom: 14px;
  border: 1px solid rgba(255,255,255,0.15);
  border-radius: var(--radius-sm);
  background: rgba(255,255,255,0.08);
  color:#f7fffd; transition: border var(--transition), box-shadow var(--transition), background var(--transition);
}
.login-form input::placeholder{ color: rgba(255,255,255,0.6); }
.login-form input:focus{
  outline:none;
  border-color: var(--brand);
  background: rgba(255,255,255,0.12);
  box-shadow: 0 0 0 4px rgba(0,229,193,0.15);
}

.login-form .actions{
  display:flex; gap:10px; align-items:center; justify-content:space-between;
  margin-top: 6px;
}

.btn{
  display:inline-block; width:100%;
  padding: 12px 14px; border:none; border-radius: var(--radius-sm);
  background: var(--brand); color:#05221c; font-weight:700; cursor:pointer;
  transition: transform var(--transition), box-shadow var(--transition), background var(--transition);
}
.btn:hover{ background: var(--brand-dark); transform: translateY(-1px); box-shadow: 0 8px 18px rgba(0,0,0,0.35); }
.btn:active{ transform: translateY(0); box-shadow: none; }
.link{
  display:block; text-align:center; margin-top:10px; color: var(--brand);
}
.link:hover{ text-decoration: underline; }

/* ========= MODALS ========= */
.modal{ display:none; position: fixed; inset:0; background: rgba(0,0,0,0.7); z-index:1100; }
.modal-content{
  width: 380px; max-width: 92%;
  margin: 8% auto; background: #161a22; color:#eaf6f4;
  border-radius: var(--radius); padding: 22px; box-shadow: var(--shadow);
  border: 1px solid rgba(255,255,255,0.08);
}
.modal-content h3{ color:#b8fff3; text-align:center; margin-bottom: 12px; }
.modal-content input, .modal-content select, .modal-content button{
  width:100%; padding: 10px 12px; margin: 8px 0;
  border-radius: var(--radius-sm); border: 1px solid rgba(255,255,255,0.15);
  background: rgba(255,255,255,0.06); color:#f7fffd;
}
.modal-content input:focus, .modal-content select:focus{
  outline:none; border-color: var(--brand); box-shadow: 0 0 0 4px rgba(0,229,193,0.15);
}
.modal-content button{ background: var(--brand); color:#06221d; border:none; cursor:pointer; }
.modal-content button:hover{ background: var(--brand-dark); }

/* ========= PRODUCT CARDS (optional section) ========= */
.products{
  margin: 32px 56px 120px; display:grid; gap:18px;
  grid-template-columns: repeat(auto-fit, minmax(220px, 1fr));
}
.product-card{
  background: rgba(0,0,0,0.55); border:1px solid rgba(255,255,255,0.08);
  border-radius: var(--radius); overflow:hidden; box-shadow: var(--shadow);
  transition: transform var(--transition), box-shadow var(--transition), border-color var(--transition);
}
.product-card:hover{ transform: translateY(-4px); box-shadow: 0 16px 36px rgba(0,0,0,0.5); border-color: rgba(255,255,255,0.18); }
.product-card .thumb{ aspect-ratio: 4/3; object-fit: cover; width:100%; }
.product-card .meta{ padding: 14px; }
.product-card .meta h4{ margin-bottom:6px; color:#eafffb; font-size:18px; }
.price{ font-weight:800; color: var(--brand); }

/* ========= FOOTER ========= */
footer{
  position: fixed; left:0; right:0; bottom:0;
  background: rgba(10,14,18,0.9);
  color: var(--brand);
  text-align:center; padding:10px 16px;
  border-top: 1px solid rgba(255,255,255,0.06);
}

/* ========= RESPONSIVE ========= */
@media (max-width: 900px){
  .landing-text{ margin: 110px 16px 0; }
  .login-form{ position: static; width: auto; margin: 16px; }
  .products{ margin: 24px 16px 100px; }
}
