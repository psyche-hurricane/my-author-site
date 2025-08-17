import { useMemo, useState } from "react";
import { motion } from "framer-motion";

// Single-file, production-ready React component using TailwindCSS.
// Drop this into a Vite/Next/CRA project and render <AuthorPlatform />.
// Optional: connect newsletter form to your provider (ConvertKit/Mailchimp) in onSubmit.

const NAV = [
  { id: "home", label: "Home" },
  { id: "about", label: "About" },
  { id: "wip", label: "Works in Progress" },
  { id: "blog", label: "Blog" },
  { id: "contact", label: "Contact" },
];

const palette = {
  bg: "bg-slate-950",
  card: "bg-slate-900/70",
  accent: "from-indigo-400 via-fuchsia-400 to-rose-400",
  text: "text-slate-100",
  subtext: "text-slate-300",
  border: "border-slate-800",
};

const Section = ({ id, children }) => (
  <section id={id} className="scroll-mt-24 py-16 sm:py-24" aria-label={id}>
    <div className="mx-auto max-w-6xl px-4">{children}</div>
  </section>
);

const GradientText = ({ children }) => (
  <span className={`bg-gradient-to-r ${palette.accent} bg-clip-text text-transparent`}>{children}</span>
);

const Card = ({ children, className = "" }) => (
  <div className={`rounded-2xl ${palette.card} border ${palette.border} shadow-xl shadow-black/30 ${className}`}>{children}</div>
);

const Pill = ({ children }) => (
  <span className="rounded-full border border-slate-700 px-3 py-1 text-xs font-medium text-slate-300">
    {children}
  </span>
);

const SocialIcon = ({ href, label, children }) => (
  <a
    href={href}
    target="_blank"
    rel="noreferrer"
    aria-label={label}
    className="inline-flex items-center gap-2 rounded-full border border-slate-700 px-4 py-2 text-sm text-slate-200 hover:bg-slate-800/70 focus:outline-none focus:ring-2 focus:ring-indigo-400/40"
  >
    {children}
  </a>
);

const Hero = () => (
  <Section id="home">
    <div className="grid items-center gap-10 lg:grid-cols-2">
      <motion.div initial={{ opacity: 0, y: 24 }} animate={{ opacity: 1, y: 0 }} transition={{ duration: 0.6 }}>
        <h1 className="text-4xl font-bold leading-tight sm:text-5xl md:text-6xl">
          Kameryn Key
        </h1>
        <p className={`mt-4 max-w-xl text-lg ${palette.subtext}`}>
          <GradientText>Fiction that explores identity, memory, and the shadows between worlds.</GradientText>
        </p>
        <div className="mt-8 flex flex-wrap items-center gap-3">
          <Pill>Speculative · Literary</Pill>
          <Pill>Identity</Pill>
          <Pill>Memory</Pill>
          <Pill>Liminal Spaces</Pill>
        </div>
        <div className="mt-10 flex flex-wrap gap-4">
          <a href="#wip" className="rounded-xl bg-indigo-500/90 px-5 py-3 text-sm font-semibold text-white shadow-lg shadow-indigo-900/50 hover:bg-indigo-500 focus:outline-none focus:ring-2 focus:ring-indigo-400/60">
            Explore the WIP
          </a>
          <a href="#about" className="rounded-xl border border-slate-700 px-5 py-3 text-sm font-semibold text-slate-200 hover:bg-slate-800/70 focus:outline-none focus:ring-2 focus:ring-indigo-400/40">
            About the Author
          </a>
        </div>
      </motion.div>

      <motion.div
        className="relative"
        initial={{ opacity: 0, scale: 0.96 }}
        animate={{ opacity: 1, scale: 1 }}
        transition={{ duration: 0.6, delay: 0.1 }}
      >
        <div className="absolute -inset-4 -z-10 bg-gradient-to-tr from-indigo-500/10 via-fuchsia-500/10 to-rose-500/10 blur-2xl" />
        <Card className="overflow-hidden">
          <div className="aspect-[4/3] w-full bg-gradient-to-br from-slate-800 to-slate-900 p-8">
            <div className="grid h-full grid-rows-6 gap-3">
              <div className="row-span-2 rounded-xl bg-slate-800/80 p-4">
                <p className="text-sm text-slate-300">Current WIP</p>
                <h3 className="mt-1 text-xl font-semibold">Shadowrise Institute</h3>
                <p className="mt-1 text-sm text-slate-400">A locked-classroom mystery where reality bends and memory lies.</p>
              </div>
              <div className="row-span-2 grid grid-cols-3 gap-3">
                <div className="rounded-xl bg-slate-800/80 p-4">
                  <p className="text-3xl font-bold">72k</p>
                  <p className="text-xs text-slate-400">Words</p>
                </div>
                <div className="rounded-xl bg-slate-800/80 p-4">
                  <p className="text-3xl font-bold">Act II</p>
                  <p className="text-xs text-slate-400">Draft stage</p>
                </div>
                <div className="rounded-xl bg-slate-800/80 p-4">
                  <p className="text-3xl font-bold">Q1</p>
                  <p className="text-xs text-slate-400">Revise</p>
                </div>
              </div>
              <div className="row-span-2 rounded-xl bg-slate-800/80 p-4">
                <p className="text-sm text-slate-300">Newsletter</p>
                <p className="mt-1 text-xs text-slate-400">Get monthly updates, snippets, and ARCs.</p>
                <NewsletterInline />
              </div>
            </div>
          </div>
        </Card>
      </motion.div>
    </div>
  </Section>
);

const NewsletterInline = () => {
  const [email, setEmail] = useState("");
  const [sent, setSent] = useState(false);
  return (
    <form
      className="mt-3 flex gap-2"
      onSubmit={(e) => {
        e.preventDefault();
        // TODO: Hook into Mailchimp/ConvertKit. For demo, we just "succeed".
        setSent(true);
      }}
    >
      <input
        type="email"
        required
        aria-label="Email address"
        placeholder="you@example.com"
        value={email}
        onChange={(e) => setEmail(e.target.value)}
        className="w-full rounded-xl border border-slate-700 bg-slate-900/70 px-3 py-2 text-sm text-slate-100 placeholder-slate-500 focus:outline-none focus:ring-2 focus:ring-indigo-400/40"
      />
      <button type="submit" className="rounded-xl bg-indigo-500/90 px-4 text-sm font-semibold text-white hover:bg-indigo-500 focus:outline-none focus:ring-2 focus:ring-indigo-400/60">
        {sent ? "Thanks!" : "Subscribe"}
      </button>
    </form>
  );
};

const About = () => (
  <Section id="about">
    <div className="mx-auto max-w-4xl">
      <div className="mb-8">
        <h2 className="text-3xl font-bold">About the Author</h2>
        <p className={`mt-2 ${palette.subtext}`}>
          Kameryn Key is a fiction writer drawn to the mysteries of identity, memory, and what it means to be human when the world shifts beneath your feet. Her stories blend the surreal with the intimate, weaving speculative and literary elements into narratives that linger long after the last page.
        </p>
      </div>

      <div className="grid gap-6 md:grid-cols-2">
        <Card className="p-6">
          <h3 className="text-xl font-semibold">Stated Brand</h3>
          <p className={`mt-2 text-sm ${palette.subtext}`}>
            Reflective, psychological, and immersive fiction exploring identity, memory, survival, and liminal spaces.
          </p>
          <div className="mt-4 flex flex-wrap gap-2">
            <Pill>Speculative · Literary</Pill>
            <Pill>Character-Driven</Pill>
            <Pill>Atmospheric</Pill>
          </div>
        </Card>

        <Card className="p-6">
          <h3 className="text-xl font-semibold">Professional Credentials</h3>
          <ul className={`mt-2 list-disc pl-5 text-sm ${palette.subtext}`}>
            <li>B.A. in English & Creative Writing (focus: Fiction), Southern New Hampshire University.</li>
            <li>Workshop experience in fiction, literary analysis, and critique.</li>
            <li>Currently seeking representation; active submissions planned to journals such as <em>Tin House</em> and <em>Clarkesworld</em>.</li>
            <li>Working toward a polished debut manuscript: <em>Shadowrise Institute</em>.</li>
          </ul>
        </Card>

        <Card className="p-6 md:col-span-2">
          <h3 className="text-xl font-semibold">Personal Background</h3>
          <p className={`mt-2 text-sm ${palette.subtext}`}>
            Lifelong storyteller motivated by creating worlds to escape into. Interests in psychology, mythology, and the aesthetics of liminal spaces shape characters and settings. Also a photographer, pairing images with prose to offer readers a reflective, immersive experience.
          </p>
        </Card>
      </div>
    </div>
  </Section>
);

const WIP = () => {
  const projects = useMemo(
    () => [
      {
        title: "Shadowrise Institute",
        logline:
          "Victoria wakes in a locked classroom with no memory. To escape the Shadowrise Institute—a place where reality bends—she must piece together who she was and decide who she'll become.",
        highlights: [
          "Psychological mystery",
          "Speculative, atmospheric setting",
          "Character-driven with layered reveals",
        ],
        stats: [
          { k: "Audience", v: "YA/Adult crossover" },
          { k: "Comp Titles", v: "Never Let Me Go · The Secret History · The Maze Runner" },
          { k: "Progress", v: "Act II draft" },
        ],
      },
      {
        title: "Who Are We Really?",
        logline:
          "An essayistic novella on masks, performance, and the hunger to be known—intercut with a sibling duo navigating a city of mirrors.",
        highlights: ["Identity & performance", "Braided structure", "Lyrical, intimate voice"],
        stats: [
          { k: "Form", v: "Novella-in-essays" },
          { k: "Status", v: "Outlining" },
          { k: "Themes", v: "Selfhood · Memory · Perception" },
        ],
      },
    ],
    []
  );

  return (
    <Section id="wip">
      <div className="mb-8 flex items-end justify-between gap-4">
        <div>
          <h2 className="text-3xl font-bold">Works in Progress</h2>
          <p className={`mt-2 ${palette.subtext}`}>Projects aligned with brand, genre, and core themes.</p>
        </div>
        <a
          href="#contact"
          className="hidden rounded-xl bg-rose-500/90 px-4 py-2 text-sm font-semibold text-white shadow-lg shadow-rose-900/40 hover:bg-rose-500 focus:outline-none focus:ring-2 focus:ring-rose-400/60 md:inline-flex"
        >
          Request ARC / Beta
        </a>
      </div>

      <div className="grid gap-6 md:grid-cols-2">
        {projects.map((p) => (
          <Card key={p.title} className="p-6">
            <div className="flex items-start justify-between gap-4">
              <div>
                <h3 className="text-xl font-semibold">{p.title}</h3>
                <p className={`mt-1 text-sm ${palette.subtext}`}>{p.logline}</p>
              </div>
              <Pill>WIP</Pill>
            </div>

            <div className="mt-4 flex flex-wrap gap-2">
              {p.highlights.map((h) => (
                <Pill key={h}>{h}</Pill>
              ))}
            </div>

            <dl className="mt-5 grid grid-cols-1 gap-3 sm:grid-cols-3">
              {p.stats.map(({ k, v }) => (
                <div key={k} className="rounded-xl border border-slate-800 bg-slate-900/60 p-3">
                  <dt className="text-xs uppercase tracking-wide text-slate-400">{k}</dt>
                  <dd className="mt-1 text-sm text-slate-200">{v}</dd>
                </div>
              ))}
            </dl>
          </Card>
        ))}
      </div>

      <SocialPlanner />
    </Section>
  );
};

const SocialPlanner = () => {
  const posts = [
    {
      title: "WIP Wednesday — Shadowrise",
      caption:
        "She wakes with a name she doesn't trust. What would you cling to if your memories vanished? #AmWriting #SpecFic #WIPWednesday",
      cta: "Poll: Which clue should she follow next?",
      type: "Post + Poll",
    },
    {
      title: "Moodboard Monday",
      caption:
        "Liminal halls, locked doors, soft neon. Writing spaces between truth and dream. #Aesthetic #Liminal #WriterLife",
      cta: "Carousel of 5 images (original photography)",
      type: "Carousel",
    },
    {
      title: "Snippet Sunday",
      caption:
        '“The door knows my name, but I don\'t.” — Shadowrise Institute (draft) #SnippetSunday #IndieAuthors',
      cta: "Ask: keep this line?",
      type: "Quote Card",
    },
  ];

  return (
    <Card className="mt-10 p-6">
      <div className="flex flex-wrap items-center justify-between gap-4">
        <h3 className="text-lg font-semibold">Social Media: Instagram (@KamerynKeyWrites)</h3>
        <div className="flex gap-2">
          <Pill>Clear & Consistent</Pill>
          <Pill>Brand-Aligned</Pill>
        </div>
      </div>
      <p className={`mt-2 text-sm ${palette.subtext}`}>
        Content that aligns with the platform brand; designed for engagement (polls, Q&A, carousels) and consistency (3x week cadence).
      </p>

      <div className="mt-4 grid gap-4 md:grid-cols-3">
        {posts.map((p) => (
          <div key={p.title} className="rounded-2xl border border-slate-800 bg-slate-900/50 p-4">
            <p className="text-sm font-semibold">{p.title}</p>
            <p className={`mt-1 text-sm ${palette.subtext}`}>{p.caption}</p>
            <p className="mt-2 text-xs text-slate-400">Format: {p.type}</p>
            <p className="mt-1 text-xs text-slate-400">CTA: {p.cta}</p>
          </div>
        ))}
      </div>

      <div className="mt-6 flex flex-wrap gap-3">
        <SocialIcon href="https://instagram.com/" label="Instagram">
          <svg aria-hidden="true" viewBox="0 0 24 24" className="h-4 w-4 fill-current"><path d="M7 2h10a5 5 0 0 1 5 5v10a5 5 0 0 1-5 5H7a5 5 0 0 1-5-5V7a5 5 0 0 1 5-5zm5 4a6 6 0 1 0 0 12 6 6 0 0 0 0-12zm6.5.9a1.1 1.1 0 1 0 0 2.2 1.1 1.1 0 0 0 0-2.2zM12 9a3 3 0 1 1 0 6 3 3 0 0 1 0-6z"/></svg>
          Instagram
        </SocialIcon>
        <SocialIcon href="#" label="Newsletter">📬 Newsletter</SocialIcon>
        <SocialIcon href="#contact" label="Contact">✉️ Contact</SocialIcon>
      </div>
    </Card>
  );
};

const Blog = () => {
  const posts = [
    {
      title: "Writing Liminal Spaces Without Losing Your Reader",
      date: "Aug 2, 2025",
      tags: ["craft", "worldbuilding"],
      excerpt:
        "How to make eerie, in-between places feel tangible—anchoring with sensory detail and character desire.",
    },
    {
      title: "Character as Compass: Desire-Driven Scenes",
      date: "Jul 18, 2025",
      tags: ["craft", "structure"],
      excerpt:
        "Use unmet desire to decide what happens next—plus a scene checklist I actually use.",
    },
  ];

  return (
    <Section id="blog">
      <div className="mb-8">
        <h2 className="text-3xl font-bold">Blog</h2>
        <p className={`mt-2 ${palette.subtext}`}>Occasional posts on craft, reading, and process.</p>
      </div>

      <div className="grid gap-6 md:grid-cols-2">
        {posts.map((p) => (
          <Card key={p.title} className="p-6">
            <p className="text-xs text-slate-400">{p.date}</p>
            <h3 className="mt-1 text-xl font-semibold">{p.title}</h3>
            <div className="mt-2 flex flex-wrap gap-2">
              {p.tags.map((t) => (
                <Pill key={t}>{t}</Pill>
              ))}
            </div>
            <p className={`mt-3 text-sm ${palette.subtext}`}>{p.excerpt}</p>
            <button className="mt-4 rounded-xl border border-slate-700 px-4 py-2 text-sm text-slate-200 hover:bg-slate-800/70">
              Read (placeholder)
            </button>
          </Card>
        ))}
      </div>
    </Section>
  );
};

const Contact = () => (
  <Section id="contact">
    <div className="grid gap-6 md:grid-cols-2">
      <Card className="p-6">
        <h2 className="text-2xl font-semibold">Get in touch</h2>
        <p className={`mt-2 text-sm ${palette.subtext}`}>
          For rights inquiries, beta reads, interviews, or classroom visits, use the form. For newsletter or ARC requests, mention your handle and reading preferences.
        </p>
        <ContactForm />
      </Card>

      <Card className="p-6">
        <h3 className="text-lg font-semibold">Quick Facts</h3>
        <ul className={`mt-2 list-disc pl-5 text-sm ${palette.subtext}`}>
          <li>Genres: Speculative & Literary</li>
          <li>Themes: Identity, Memory, Perception vs. Reality</li>
          <li>Based in: United States</li>
          <li>Availability: Readings, Workshops, Podcast Guest</li>
        </ul>
        <div className="mt-6">
          <h4 className="text-sm font-semibold">Press-friendly Bio (75 words)</h4>
          <p className={`mt-1 text-sm ${palette.subtext}`}>
            Kameryn Key writes character-driven speculative fiction about identity and memory. A BA candidate in English & Creative Writing (Fiction) at SNHU, she blends surreal and intimate elements to explore what makes us human when the world tilts. Currently seeking representation and preparing submissions to journals, she is drafting her debut, <em>Shadowrise Institute</em>.
          </p>
        </div>
      </Card>
    </div>
  </Section>
);

const ContactForm = () => {
  const [state, setState] = useState({ name: "", email: "", message: "" });
  const [sent, setSent] = useState(false);

  return (
    <form
      className="mt-4 space-y-3"
      onSubmit={(e) => {
        e.preventDefault();
        setSent(true);
      }}
    >
      <div>
        <label className="text-xs text-slate-400">Name</label>
        <input
          className="mt-1 w-full rounded-xl border border-slate-700 bg-slate-900/70 px-3 py-2 text-sm text-slate-100 placeholder-slate-500 focus:outline-none focus:ring-2 focus:ring-indigo-400/40"
          placeholder="Your name"
          value={state.name}
          onChange={(e) => setState({ ...state, name: e.target.value })}
          required
        />
      </div>
      <div>
        <label className="text-xs text-slate-400">Email</label>
        <input
          type="email"
          className="mt-1 w-full rounded-xl border border-slate-700 bg-slate-900/70 px-3 py-2 text-sm text-slate-100 placeholder-slate-500 focus:outline-none focus:ring-2 focus:ring-indigo-400/40"
          placeholder="you@example.com"
          value={state.email}
          onChange={(e) => setState({ ...state, email: e.target.value })}
          required
        />
      </div>
      <div>
        <label className="text-xs text-slate-400">Message</label>
        <textarea
          rows={5}
          className="mt-1 w-full rounded-xl border border-slate-700 bg-slate-900/70 px-3 py-2 text-sm text-slate-100 placeholder-slate-500 focus:outline-none focus:ring-2 focus:ring-indigo-400/40"
          placeholder="Tell me about your project or request."
          value={state.message}
          onChange={(e) => setState({ ...state, message: e.target.value })}
          required
        />
      </div>
      <button type="submit" className="rounded-xl bg-fuchsia-500/90 px-5 py-2 text-sm font-semibold text-white hover:bg-fuchsia-500 focus:outline-none focus:ring-2 focus:ring-fuchsia-400/60">
        {sent ? "Sent!" : "Send Message"}
      </button>
    </form>
  );
};

const Nav = () => {
  const [open, setOpen] = useState(false);
  return (
    <header className="sticky top-0 z-50 border-b border-slate-800/80 backdrop-blur supports-[backdrop-filter]:bg-slate-950/70">
      <div className="mx-auto flex max-w-6xl items-center justify-between px-4 py-3">
        <a href="#home" className="flex items-center gap-2 text-slate-100">
          <span className="inline-block h-2 w-2 rounded-full bg-gradient-to-r from-indigo-400 to-rose-400" />
          <span className="text-sm font-semibold tracking-wide">Kameryn Key</span>
        </a>
        <nav className="hidden gap-6 md:flex">
          {NAV.map((n) => (
            <a key={n.id} href={`#${n.id}`} className="text-sm text-slate-300 hover:text-white">
              {n.label}
            </a>
          ))}
        </nav>
        <button
          className="md:hidden"
          aria-label="Toggle menu"
          onClick={() => setOpen((s) => !s)}
        >
          <svg viewBox="0 0 24 24" className="h-6 w-6 text-slate-200"><path fill="currentColor" d="M3 6h18v2H3V6m0 5h18v2H3v-2m0 5h18v2H3v-2Z"/></svg>
        </button>
      </div>
      {open && (
        <div className="md:hidden">
          <div className="mx-auto max-w-6xl px-4 pb-4">
            <div className="flex flex-col gap-2 rounded-2xl border border-slate-800 bg-slate-900/70 p-3">
              {NAV.map((n) => (
                <a key={n.id} href={`#${n.id}`} className="rounded-xl px-3 py-2 text-sm text-slate-200 hover:bg-slate-800/70" onClick={() => setOpen(false)}>
                  {n.label}
                </a>
              ))}
            </div>
          </div>
        </div>
      )}
    </header>
  );
};

const Footer = () => (
  <footer className="mt-20 border-t border-slate-800/80">
    <div className="mx-auto max-w-6xl px-4 py-10">
      <div className="flex flex-col justify-between gap-4 sm:flex-row sm:items-center">
        <p className="text-xs text-slate-400">© {new Date().getFullYear()} Kameryn Key · All rights reserved.</p>
        <div className="flex flex-wrap gap-3">
          <a href="#" className="text-xs text-slate-400 hover:text-slate-200">Privacy</a>
          <a href="#" className="text-xs text-slate-400 hover:text-slate-200">Terms</a>
          <a href="#contact" className="text-xs text-slate-400 hover:text-slate-200">Contact</a>
        </div>
      </div>
    </div>
  </footer>
);

export default function AuthorPlatform() {
  return (
    <div className={`${palette.bg} ${palette.text} min-h-screen font-sans antialiased`}> 
      <Nav />
      <main>
        <Hero />
        <About />
        <WIP />
        <Blog />
        <Contact />
      </main>
      <Footer />
    </div>
  );
}
