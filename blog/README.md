 <h1>📖 Blog Application - Node.js + Express + Passport + EJS</h1>

  <p>This is a <strong>Blog Web Application</strong> built with <code>Node.js</code>, <code>Express.js</code>, <code>EJS</code> for templating, <code>Passport.js</code> for authentication, and <code>express-session</code> for session management. The application allows users to register, login, and manage blog posts with secure authentication.</p>

  <h2>🚀 Features</h2>
  <ul>
    <li>User authentication with <strong>Passport.js</strong> (Login, Logout, Register).</li>
    <li><strong>Session management</strong> using <code>express-session</code>.</li>
    <li>Blog CRUD operations (Create, Read, Update, Delete).</li>
    <li><strong>Dynamic EJS templates</strong> for rendering views.</li>
    <li><strong>Flash messages</strong> for better UX.</li>
    <li>Secure routes with <code>requireAuth</code> middleware.</li>
    <li>Static files served from <code>public</code> directory.</li>
    <li>File uploads stored in <code>uploads</code> directory.</li>
    <li>Centralized error handling middleware.</li>
  </ul>

  <h2>ScreenShots</h2>

<img width="1893" height="918" alt="Screenshot 2025-08-30 165206" src="https://github.com/user-attachments/assets/0395f70d-e956-40d0-9b42-0434030b9ef6" />
<img width="1884" height="913" alt="Screenshot 2025-08-30 165222" src="https://github.com/user-attachments/assets/07b5532a-6756-4833-919d-db166cd8e274" />
<img width="1900" height="918" alt="Screenshot 2025-08-30 170400" src="https://github.com/user-attachments/assets/e07c3f5a-e514-4ffd-a645-fa3996a70408" />
<img width="1897" height="1079" alt="Screenshot 2025-08-30 170419" src="https://github.com/user-attachments/assets/626376cc-5b73-4274-90b5-0995c8f026bf" />
  <img width="1882" height="907" alt="Screenshot 2025-08-30 170902" src="https://github.com/user-attachments/assets/3ae96440-2234-40bc-8fb7-45179793f12a" />


  <h2>📂 Project Structure</h2>
  <pre>
  blog-Nodejs-main/
  ├── config/
  │   ├── database.js
  │   └── passport.js
  ├── middleware/
  │   └── auth.js
  ├── routes/
  │   ├── authRoutes.js
  │   └── blogRoutes.js
  ├── uploads/        # uploaded files
  ├── public/         # static assets (css, js, images)
  ├── views/          # EJS templates
  ├── server.js       # main entry point
  ├── package.json
  </pre>

  <h2>⚙️ Installation & Setup</h2>
  <ol>
    <li>Clone this repository:
      <pre>git clone https://github.com/your-username/blog-Nodejs-main.git</pre>
    </li>
    <li>Navigate into the project folder:
      <pre>cd blog-Nodejs-main</pre>
    </li>
    <li>Install dependencies:
      <pre>npm install</pre>
    </li>
    <li>Set up your database configuration inside <code>config/database.js</code>.</li>
    <li>Run the application:
      <pre>npm start</pre>
    </li>
    <li>Visit:
      <pre>http://localhost:9000</pre>
    </li>
  </ol>

  <h2>🔑 Authentication</h2>
  <p>Authentication is handled using <code>Passport.js</code> with session support. Middleware functions are used:</p>
  <ul>
    <li><code>isAuthenticated</code> → checks if user is logged in.</li>
    <li><code>requireAuth</code> → protects private routes.</li>
    <li><code>setLocals</code> → passes authentication status and username to views.</li>
  </ul>

  <h2>🌐 Routes Overview</h2>
  <ul>
    <li><code>GET /</code> → Redirects user based on login status.</li>
    <li><code>GET /login</code> → Login page.</li>
    <li><code>POST /login</code> → Handle login form submission.</li>
    <li><code>GET /register</code> → Register page.</li>
    <li><code>POST /register</code> → Handle user registration.</li>
    <li><code>GET /blogs</code> → View all blogs (requires login).</li>
    <li><code>GET /blogs/:id</code> → View a single blog.</li>
    <li><code>POST /blogs</code> → Create a new blog post.</li>
    <li><code>PUT /blogs/:id</code> → Update blog post.</li>
    <li><code>DELETE /blogs/:id</code> → Delete blog post.</li>
    <li><code>GET /test-auth</code> → Test route for authentication & session check.</li>
  </ul>

  <h2>🛡️ Middleware Functions</h2>
  <pre>
  function isAuthenticated(req, res, next) {
      if (req.isAuthenticated()) return next();
      res.redirect('/login');
  }

  function requireAuth(req, res, next) {
      if (req.isAuthenticated()) return next();
      res.redirect('/login');
  }

  function setLocals(req, res, next) {
      res.locals.isAuthenticated = req.isAuthenticated();
      res.locals.username = req.user ? req.user.username : null;
      next();
  }
  </pre>

  <h2>📸 Screenshots (Optional)</h2>
  <p>You can add screenshots of your app UI inside the <code>public</code> folder and display them here.</p>

  <h2>⚡ Technologies Used</h2>
  <ul>
    <li><strong>Node.js</strong> - Backend runtime.</li>
    <li><strong>Express.js</strong> - Web framework.</li>
    <li><strong>EJS</strong> - Templating engine.</li>
    <li><strong>Passport.js</strong> - Authentication.</li>
    <li><strong>express-session</strong> - Session management.</li>
    <li><strong>MongoDB/MySQL</strong> - Database (depending on your setup).</li>
  </ul>

  <h2>📜 Error Handling</h2>
  <p>A centralized error handler ensures that any unexpected errors are caught and a 500 status is returned:</p>
  <pre>
  app.use((err, req, res, next) => {
    console.error(err.stack);
    res.status(500).send("Something went wrong");
  });
  </pre>

  <h2>🙌 Contribution</h2>
  <p>If you would like to contribute:</p>
  <ol>
    <li>Fork the repository</li>
    <li>Create a new branch (<code>git checkout -b feature-name</code>)</li>
    <li>Commit your changes (<code>git commit -m "Added new feature"</code>)</li>
    <li>Push to the branch (<code>git push origin feature-name</code>)</li>
    <li>Open a Pull Request</li>
  </ol>



  <hr>
  <p class="highlight">✅ Server will start on <a href="http://localhost:9000">http://localhost:9000</a> once you run <code>npm start</code>.</p>

