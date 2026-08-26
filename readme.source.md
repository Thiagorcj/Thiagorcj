```aura width=800 height=420
<div style={{ position: 'relative', display: 'flex', flexDirection: 'column', alignItems: 'center', justifyContent: 'center', width: '100%', height: '100%', background: '#07070c', borderRadius: 24, overflow: 'hidden', fontFamily: 'Poppins, sans-serif' }}>
  <style>{`
    @keyframes glow-a { 0%, 100% { transform: translate(0,0); opacity: 0.55; } 50% { transform: translate(26px,-18px); opacity: 0.85; } }
    @keyframes glow-b { 0%, 100% { transform: translate(0,0); opacity: 0.45; } 50% { transform: translate(-20px,16px); opacity: 0.7; } }
    @keyframes ring-pulse { 0%, 100% { opacity: 0.05; } 50% { opacity: 0.16; } }
    #g1 { animation: glow-a 9s ease-in-out infinite; }
    #g2 { animation: glow-b 11s ease-in-out infinite 1s; }
    #r1 { animation: ring-pulse 8s ease-in-out infinite; }
    #r2 { animation: ring-pulse 8s ease-in-out infinite 2s; }
  `}</style>

  <svg width="800" height="420" style={{ position: 'absolute', top: 0, left: 0 }}>
    <defs>
      <radialGradient id="pg1" cx="50%" cy="50%" r="50%">
        <stop offset="0%" stopColor="rgba(155,110,255,0.55)" />
        <stop offset="100%" stopColor="rgba(155,110,255,0)" />
      </radialGradient>
      <radialGradient id="pg2" cx="50%" cy="50%" r="50%">
        <stop offset="0%" stopColor="rgba(90,200,220,0.4)" />
        <stop offset="100%" stopColor="rgba(90,200,220,0)" />
      </radialGradient>
    </defs>
    <ellipse id="g1" cx="140" cy="90" rx="280" ry="220" fill="url(#pg1)" />
    <ellipse id="g2" cx="680" cy="120" rx="260" ry="200" fill="url(#pg2)" />
    <circle id="r1" cx="400" cy="150" r="90" fill="none" stroke="rgba(255,255,255,0.9)" strokeWidth="0.6" />
    <circle id="r2" cx="400" cy="150" r="150" fill="none" stroke="rgba(255,255,255,0.9)" strokeWidth="0.6" />
  </svg>

  <div style={{ position: 'relative', display: 'flex', flexDirection: 'column', alignItems: 'center', zIndex: 10, marginTop: 30 }}>
    <span style={{ fontFamily: 'Poppins, sans-serif', fontSize: 58, fontWeight: 700, letterSpacing: 6, color: '#ffffff', textShadow: '0 0 40px rgba(155,110,255,0.6)' }}>
      {'Thiago Rodrigues'.toUpperCase()}
    </span>
    <span style={{ fontFamily: 'Poppins, sans-serif', fontSize: 14, color: 'rgba(220,205,255,0.85)', marginTop: 18, letterSpacing: 6, textTransform: 'uppercase', fontWeight: 600 }}>Data Scientist &amp; AI Engineer</span>
    <span style={{ fontFamily: 'Poppins, sans-serif', fontSize: 12, color: 'rgba(255,255,255,0.4)', marginTop: 10, letterSpacing: 3, textTransform: 'uppercase', fontWeight: 400 }}>Software Engineering</span>
    <span style={{ fontSize: 11, color: 'rgba(124,92,255,0.7)', marginTop: 16, letterSpacing: 1 }}>
      github.com/{(github && github.user && github.user.login) || 'Thiagorcj'}
    </span>

    <div style={{ display: 'flex', gap: 8, marginTop: 30, flexWrap: 'wrap', justifyContent: 'center', maxWidth: 620 }}>
      {['Python', 'TensorFlow', 'PyTorch', 'Pandas', 'Scikit-learn', 'SQL', 'Docker', 'AWS'].map((tag) => (
        <span key={tag} style={{ padding: '7px 16px', background: 'rgba(255,255,255,0.045)', color: 'rgba(255,255,255,0.75)', borderRadius: 100, fontSize: 12, border: '1px solid rgba(255,255,255,0.1)', fontWeight: 500 }}>{tag}</span>
      ))}
    </div>
  </div>
</div>
```

```aura width=800 height=150
<div style={{ display: 'flex', width: '100%', height: '100%', background: '#07070c', borderRadius: 20, borderTop: '1px solid rgba(255,255,255,0.06)', fontFamily: 'Poppins, sans-serif' }}>
  {[
    { label: 'Stars', value: (github && github.stats && github.stats.totalStars) || 0, color: '#f5c451' },
    { label: 'Forks', value: (github && github.stats && github.stats.totalForks) || 0, color: '#ffffff' },
    { label: 'Repos', value: (github && github.stats && github.stats.totalRepos) || 0, color: '#ffffff' },
    { label: 'Commits', value: (github && github.stats && github.stats.totalCommits) || 0, color: '#7c5cff' },
  ].map((s, i) => (
    <div key={s.label} style={{ flex: 1, display: 'flex', flexDirection: 'column', alignItems: 'center', justifyContent: 'center', borderLeft: i === 0 ? 'none' : '1px solid rgba(255,255,255,0.06)' }}>
      <span style={{ fontSize: 34, fontWeight: 800, color: s.color }}>{String(s.value)}</span>
      <span style={{ fontSize: 11, color: 'rgba(255,255,255,0.4)', letterSpacing: 2, marginTop: 6, textTransform: 'uppercase' }}>{s.label}</span>
    </div>
  ))}
</div>
```

```aura width=800 height=230
<div style={{ display: 'flex', flexDirection: 'column', width: '100%', height: '100%', background: '#07070c', borderRadius: 20, padding: 30, fontFamily: 'Poppins, sans-serif' }}>
  <span style={{ fontSize: 12, color: 'rgba(255,255,255,0.4)', letterSpacing: 3, textTransform: 'uppercase', fontWeight: 600, marginBottom: 18 }}>Stack Analytics</span>

  <div style={{ display: 'flex', width: '100%', height: 10, borderRadius: 6, overflow: 'hidden' }}>
    {((github && github.languages) || []).map((l) => (
      <div key={l.name} style={{ width: `${l.percentage}%`, height: '100%', background: l.color || '#7c5cff' }} />
    ))}
  </div>

  <div style={{ display: 'flex', flexWrap: 'wrap', gap: '14px 26px', marginTop: 24 }}>
    {((github && github.languages) || []).map((l) => (
      <div key={l.name} style={{ display: 'flex', alignItems: 'center', gap: 8 }}>
        <div style={{ width: 8, height: 8, borderRadius: 8, background: l.color || '#7c5cff' }} />
        <span style={{ fontSize: 12, color: 'rgba(255,255,255,0.8)', fontWeight: 600 }}>{l.name}</span>
        <span style={{ fontSize: 12, color: 'rgba(255,255,255,0.35)' }}>{l.percentage}%</span>
      </div>
    ))}
  </div>
</div>
```

```aura width=800 height=260
<div style={{ display: 'flex', flexDirection: 'column', width: '100%', height: '100%', background: '#07070c', borderRadius: 20, padding: 30, fontFamily: 'Poppins, sans-serif' }}>
  <div style={{ display: 'flex', justifyContent: 'space-between', alignItems: 'center', marginBottom: 20 }}>
    <span style={{ fontSize: 12, color: 'rgba(255,255,255,0.4)', letterSpacing: 3, textTransform: 'uppercase', fontWeight: 600 }}>Activity Pulse</span>
    <span style={{ fontSize: 11, color: 'rgba(255,255,255,0.3)' }}>updated automatically</span>
  </div>
  <div style={{ display: 'flex', gap: 4 }}>
    {Array.from({ length: 26 }).map((_, col) => (
      <div key={col} style={{ display: 'flex', flexDirection: 'column', gap: 4 }}>
        {Array.from({ length: 7 }).map((_, row) => {
          const seed = (col * 7 + row * 13) % 11;
          const opacity = seed < 3 ? 0.06 : seed < 6 ? 0.22 : seed < 8 ? 0.5 : seed < 10 ? 0.8 : 1;
          return (
            <div key={row} style={{ width: 12, height: 12, borderRadius: 3, background: `rgba(124,92,255,${opacity})` }} />
          );
        })}
      </div>
    ))}
  </div>
</div>
```

```aura width=140 height=48 link="https://github.com/Thiagorcj" inline align=center
<div style={{ display: 'flex', alignItems: 'center', justifyContent: 'center', width: '100%', height: '100%', background: '#0d0d13', borderRadius: 10, border: '1px solid rgba(255,255,255,0.12)', fontFamily: 'Poppins, sans-serif' }}>
  <span style={{ fontSize: 13, color: '#ffffff', fontWeight: 600, letterSpacing: 0.5 }}>GitHub</span>
</div>
```

```aura width=140 height=48 link="https://www.linkedin.com/in/thiago-rodrigues-b8a328249/" inline align=center
<div style={{ display: 'flex', alignItems: 'center', justifyContent: 'center', width: '100%', height: '100%', background: '#0d0d13', borderRadius: 10, border: '1px solid rgba(90,140,255,0.35)', fontFamily: 'Poppins, sans-serif' }}>
  <span style={{ fontSize: 13, color: '#8fb2ff', fontWeight: 600, letterSpacing: 0.5 }}>LinkedIn</span>
</div>
```

```aura width=140 height=48 link="mailto:thiago.rodrigues.cruz.justino@gmail.com" inline align=center
<div style={{ display: 'flex', alignItems: 'center', justifyContent: 'center', width: '100%', height: '100%', background: '#0d0d13', borderRadius: 10, border: '1px solid rgba(124,92,255,0.35)', fontFamily: 'Poppins, sans-serif' }}>
  <span style={{ fontSize: 13, color: '#b9a4ff', fontWeight: 600, letterSpacing: 0.5 }}>Email</span>
</div>
```
