<script setup lang="ts">
import { ref } from 'vue';

const menuOpen = ref(false);
const activeFilter = ref('Semua');
const filters = ['Semua'];
const nav = [
	{ label: 'Beranda', href: '#beranda' }, { label: 'Tentang Saya', href: '#tentang' },
	{ label: 'Portfolio', href: '#portfolio' }, { label: 'Pendidikan', href: '#pendidikan' },
	{ label: 'Pengalaman', href: '#pengalaman' }, { label: 'Kontak', href: '#kontak' },
];
const projects = [
	{ title: 'IIF Development — AMIKOM', type: 'Web App', desc: 'Aplikasi web IIF AMIKOM dengan backend Laravel, frontend Vue, Redis sebagai cache, dan MinIO sebagai storage.', stack: 'Laravel · Vue · Redis · MinIO', tone: 'blue', icon: '↗', url: 'https://iif-dev.amikom.ac.id/' },
];
const visibleProjects = () => activeFilter.value === 'Semua' ? projects : projects.filter((project) => project.type === activeFilter.value);
</script>

<template>
	<header class="topbar">
		<nav class="nav wrap" aria-label="Navigasi utama">
			<a class="brand" href="#beranda" aria-label="Beranda"><span class="brand-mark">a.</span><span>Ariel<span
						class="brand-dot">.</span></span></a>
			<button class="menu-toggle" type="button" :aria-expanded="menuOpen" aria-label="Buka navigasi"
				@click="menuOpen = !menuOpen"><span></span><span></span></button>
			<div class="nav-links" :class="{ open: menuOpen }">
				<a v-for="item in nav" :key="item.href" :href="item.href" @click="menuOpen = false">{{ item.label }}</a>
				<a class="nav-cta" href="#kontak" @click="menuOpen = false">Kontak Saya <span>↗</span></a>
			</div>
		</nav>
	</header>

	<main>
		<section id="beranda" class="hero wrap">
			<div class="hero-copy">
				<p class="eyebrow"><span class="status-dot"></span> TERBUKA UNTUK KOLABORASI</p>
				<h1>Membangun solusi digital<br />yang <span class="gradient-text">berarti.</span></h1>
				<p class="hero-lead">Halo, saya <strong>Muhammad Ariel EkaPutra</strong> — mahasiswa Informatika dan
					pengembang web yang senang mengubah ide dan proses rumit menjadi pengalaman digital sederhana.</p>
				<div class="hero-actions"><a class="button button-dark" href="#portfolio">Lihat karya saya
						<span>↓</span></a><a class="text-link" href="#kontak">Hubungi saya <span>↗</span></a></div>
				<div class="hero-meta"><span><i class="pin">⌖</i> Yogyakarta, Indonesia</span><span
						class="meta-divider"></span><span>React Native · Laravel · Vue</span></div>
			</div>
			<div class="hero-art" aria-label="Ilustrasi abstrak profil pengembang">
				<div class="art-orbit orbit-one"></div>
				<div class="art-orbit orbit-two"></div>
				<div class="art-glow"></div>
				<div class="art-card code-card">
					<div class="window-dots"><i></i><i></i><i></i><span>developer.php</span></div>
					<div class="code-lines">
						<p><b>&lt;?php</b></p>
						<p><span class="code-purple">$developer</span> = [</p>
						<p class="indent">'name' <em>=&gt;</em> <span class="code-green">'Ariel'</span>,</p>
						<p class="indent">'role' <em>=&gt;</em> <span class="code-green">'Full Stack'</span>,</p>
						<p class="indent">'focus' <em>=&gt;</em> <span class="code-green">'Web apps'</span>,</p>
						<p>];</p>
						<p><span class="code-purple">build</span>(<span class="code-green">'something great'</span>);<i
								class="cursor"></i></p>
					</div>
				</div>
				<div class="floating-chip chip-top"><span class="chip-icon purple">⌘</span><span><b>Clean
							code</b><small>dibuat dengan teliti</small></span></div>
				<div class="floating-chip chip-bottom"><span class="chip-icon mint">✳</span><span><b>Problem
							solver</b><small>selalu belajar hal baru</small></span></div>
				<div class="art-label">IDEA <span>→</span> IMPACT</div>
			</div>
			<a href="#tentang" class="scroll-cue"><span></span> GULIR UNTUK MENJELAJAH</a>
		</section>

		<section id="tentang" class="about section-pad">
			<div class="wrap about-grid">
				<div class="section-kicker"><span>01</span><span class="kicker-line"></span><span>TENTANG SAYA</span>
				</div>
				<div class="about-main">
					<p class="section-overline">SEDIKIT TENTANG SAYA</p>
					<h2>Teknologi yang baik<br />terasa <span class="serif-accent">sederhana.</span></h2>
					<p class="about-text">Saya adalah mahasiswa semester 6 Program Studi Informatika di AMIKOM. Saya
						tertarik pada pengembangan web, khususnya membangun solusi backend yang membantu pengguna
						menyelesaikan kebutuhan mereka.</p>
					<p class="about-text">Saya pernah menjalani magang selama 3 bulan sebagai backend developer untuk
						aplikasi pencarian kerja yang menghubungkan pencari kerja dengan perusahaan. Saya menikmati
						proses memahami kebutuhan, merancang alur, dan membangun fitur yang stabil serta mudah digunakan.</p><a
						class="text-link underlined" href="mailto:arilputra813@gmail.com">arilputra813@gmail.com
						<span>↗</span></a>
				</div>
				<div class="about-side">
					<div class="stat-card"><strong>6</strong><span>Semester<br />Informatika</span></div>
					<div class="stat-card"><strong>3</strong><span>Bulan pengalaman<br />magang backend</span></div>
					<div class="stack-block">
						<p class="section-overline">TOOLS YANG SAYA GUNAKAN</p>
						<div class="tags">
							<span>Docker</span><span>Laravel</span><span>Vue</span><span>React
								Native</span><span>Nest.JS</span>
						</div>
					</div>
				</div>
			</div>
		</section>

		<section id="portfolio" class="portfolio section-pad">
			<div class="wrap">
				<div class="section-head">
					<div>
						<div class="section-kicker"><span>02</span><span
								class="kicker-line"></span><span>PORTFOLIO</span></div>
						<p class="section-overline">KARYA PILIHAN</p>
						<h2>Beberapa hal yang<br />pernah saya <span class="serif-accent">bangun.</span></h2>
					</div>
					<p class="section-summary">Dari sistem operasional hingga pengalaman digital untuk pelanggan —
						setiap proyek dimulai dari kebutuhan nyata.</p>
				</div>
				<div class="filter-row"><button v-for="filter in filters" :key="filter" type="button"
						:class="{ selected: activeFilter === filter }" @click="activeFilter = filter">{{ filter }}<span
							v-if="filter === 'Semua'"> ({{ projects.length }})</span></button></div>
				<div class="project-grid">
					<article v-for="(project, index) in visibleProjects()" :key="project.title" class="project-card">
						<div class="project-visual" :class="project.tone">
							<div class="mock-window">
								<div class="mock-top"><span></span><span></span><span></span><i>{{ project.type ===
									'Website' ? 'website' : 'dashboard' }}.app</i></div>
								<div class="mock-layout">
									<div class="mock-sidebar"><b></b><i></i><i></i><i></i><i></i></div>
									<div class="mock-content">
										<div class="mock-title"></div>
										<div class="mock-stat-row"><i></i><i></i><i></i></div>
										<div class="mock-chart">
											<span></span><span></span><span></span><span></span><span></span><span></span><span></span>
										</div>
										<div class="mock-table"><i></i><i></i><i></i></div>
									</div>
								</div>
							</div><span class="visual-number">0{{ index + 1 }}</span>
						</div>
						<div class="project-info">
							<div><span class="project-type">{{ project.type }}</span>
								<h3>{{ project.title }}</h3>
							</div><span class="project-arrow">{{ project.icon }}</span>
							<p>{{ project.desc }}</p>
							<div class="project-footer"><span>{{ project.stack }}</span><a :href="project.url"
									target="_blank" rel="noreferrer">BUKA PROYEK ↗</a>
							</div>
						</div>
					</article>
				</div>
				<div class="all-projects"><span>Ingin melihat karya lainnya?</span><a class="text-link underlined"
						href="mailto:arielputra813@gmail.com">Tanyakan kepada saya <span>↗</span></a></div>
			</div>
		</section>

		<section id="pendidikan" class="journey section-pad">
			<div class="wrap journey-grid">
				<div>
					<div class="section-kicker"><span>03</span><span class="kicker-line"></span><span>PERJALANAN</span>
					</div>
					<p class="section-overline">BELAJAR &amp; BERTUMBUH</p>
					<h2>Perjalanan<br />yang membentuk<br /><span class="serif-accent">saya.</span></h2>
					<p class="journey-intro">Fondasi yang kuat datang dari rasa ingin tahu dan kemauan untuk terus
						berkembang.</p>
				</div>
				<div class="timeline-column">
					<div class="timeline-heading" id="pendidikan"><span class="timeline-icon">✳</span>
						<div>
							<p>PENDIDIKAN</p>
							<h3>Belajar dengan rasa ingin tahu.</h3>
						</div>
					</div>
					<article class="timeline-item"><span class="timeline-year">SEKARANG · SEMESTER 6</span>
						<h4>AMIKOM</h4>
						<p>S1 Informatika</p><span class="timeline-detail">Mempelajari ilmu informatika dan
							mengembangkan keterampilan melalui perkuliahan serta proyek.</span>
					</article>
					<article class="timeline-item"><span class="timeline-year">SEKARANG</span>
						<h4>Belajar mandiri</h4>
						<p>Web Development &amp; Software Engineering</p><span class="timeline-detail">Terus mengasah
							kemampuan lewat proyek, eksplorasi teknologi, dan praktik menulis kode yang lebih baik.</span>
					</article>
					<div class="timeline-heading exp-heading" id="pengalaman"><span class="timeline-icon">↗</span>
						<div>
							<p>PENGALAMAN</p>
							<h3>Berkarya lewat kolaborasi.</h3>
						</div>
					</div>
					<article class="timeline-item"><span class="timeline-year">MAGANG · 3 BULAN</span>
						<h4>Backend Developer · Aplikasi pencarian kerja</h4>
						<p>Magang</p><span class="timeline-detail">Berkontribusi pada backend aplikasi pencarian kerja
							yang mempertemukan pencari kerja dan perusahaan, dengan konsep serupa Jobstreet atau LinkedIn.</span>
					</article>
					<article class="timeline-item"><span class="timeline-year">SAAT INI</span>
						<h4>Mahasiswa &amp; pengembang web</h4>
						<p>Fokus pada pembelajaran dan proyek</p><span class="timeline-detail">Mengembangkan kemampuan
							web melalui kegiatan akademik, eksplorasi teknologi, dan proyek mandiri.</span>
					</article>
				</div>
			</div>
		</section>

		<section id="kontak" class="contact section-pad">
			<div class="wrap contact-wrap">
				<div class="section-kicker light-kicker"><span>05</span><span class="kicker-line"></span><span>HUBUNGI
						SAYA</span></div>
				<p class="section-overline">ADA IDE MENARIK?</p>
				<h2>Mari buat sesuatu<br /><span class="serif-accent">yang berdampak.</span></h2>
				<p class="contact-copy">Terbuka untuk obrolan, kolaborasi, maupun peluang baru. Ceritakan apa yang
					sedang Anda pikirkan.</p><a class="contact-email"
					href="mailto:arielputra813@gmail.com">arielputra813@gmail.com <span>↗</span></a>
				<div class="contact-bottom"><span>YOGYAKARTA, INDONESIA</span>
					<div class="social-links"><a href="https://www.linkedin.com/in/m-ariel-e-814167353/" target="_blank"
							rel="noreferrer">LINKEDIN ↗</a><a href="https://github.com/FranticReas" target="_blank"
							rel="noreferrer">GITHUB ↗</a></div>
				</div>
			</div>
		</section>
	</main>
	<footer class="footer">
		<div class="wrap footer-inner"><a class="brand" href="#beranda"><span
					class="brand-mark">a.</span><span>Ariel<span class="brand-dot">.</span></span></a><span>© {{ new
						Date().getFullYear() }} Muhammad Ariel EkaPutra</span><a href="#beranda">KEMBALI KE ATAS ↑</a></div>
	</footer>
</template>

<style>
@import url('https://fonts.googleapis.com/css2?family=DM+Mono:wght@400;500&family=DM+Sans:wght@400;500;600;700&family=Playfair+Display:ital,wght@1,500&display=swap');

:root {
	--ink: #17212b;
	--muted: #66727e;
	--paper: #f8fafb;
	--line: #e4e9ed;
	--blue: #5566dc;
	--mint: #a9d7c6;
	--mono: 'DM Mono', monospace;
	--sans: 'DM Sans', sans-serif
}

* {
	box-sizing: border-box
}

html {
	scroll-behavior: smooth;
	scroll-padding-top: 85px
}

body {
	background: var(--paper);
	color: var(--ink);
	font-family: var(--sans);
	-webkit-font-smoothing: antialiased
}

.wrap {
	width: min(1160px, calc(100% - 64px));
	margin-inline: auto
}

.topbar {
	height: 78px;
	background: rgba(248, 250, 251, .91);
	backdrop-filter: blur(16px);
	border-bottom: 1px solid rgba(228, 233, 237, .7);
	position: sticky;
	top: 0;
	z-index: 10
}

.nav {
	height: 100%;
	display: flex;
	align-items: center;
	justify-content: space-between
}

.brand {
	display: inline-flex;
	align-items: center;
	gap: 9px;
	color: var(--ink);
	text-decoration: none;
	font-weight: 700;
	font-size: 18px;
	letter-spacing: -.7px
}

.brand-mark {
	height: 30px;
	width: 30px;
	background: var(--ink);
	color: white;
	border-radius: 9px;
	display: grid;
	place-items: center;
	font-size: 18px;
	letter-spacing: -2px
}

.brand-dot {
	color: var(--blue)
}

.nav-links {
	display: flex;
	align-items: center;
	gap: 28px
}

.nav-links>a {
	font-size: 12px;
	text-decoration: none;
	color: #65717b;
	transition: color .2s
}

.nav-links>a:hover {
	color: var(--blue)
}

.nav-links .nav-cta {
	border: 1px solid #dce2e7;
	padding: 10px 14px;
	border-radius: 7px;
	color: var(--ink);
	font-weight: 600
}

.nav-cta span {
	color: var(--blue);
	margin-left: 7px
}

.menu-toggle {
	display: none
}

.hero {
	min-height: 625px;
	display: grid;
	grid-template-columns: 1.05fr .95fr;
	align-items: center;
	position: relative;
	padding-top: 28px;
	padding-bottom: 100px
}

.hero-copy {
	padding-top: 12px;
	z-index: 1
}

.eyebrow,
.section-overline,
.section-kicker,
.project-type,
.project-footer,
.timeline-year,
.timeline-heading p,
.contact-bottom,
.scroll-cue,
.art-label {
	font-family: var(--mono);
	letter-spacing: 1.1px
}

.eyebrow {
	font-size: 10px;
	color: #77838c;
	display: flex;
	align-items: center;
	gap: 10px;
	margin: 0 0 26px
}

.status-dot {
	height: 7px;
	width: 7px;
	border-radius: 50%;
	background: #65b995;
	box-shadow: 0 0 0 4px #e0f2e9
}

.hero h1 {
	font-size: clamp(48px, 6vw, 76px);
	line-height: 1.08;
	letter-spacing: -4.5px;
	margin: 0 0 23px;
	font-weight: 600
}

.gradient-text {
	background: linear-gradient(100deg, #596cdd, #8b65ca);
	-webkit-background-clip: text;
	background-clip: text;
	color: transparent
}

.hero-lead {
	max-width: 470px;
	color: var(--muted);
	font-size: 15px;
	line-height: 1.9;
	margin: 0
}

.hero-lead strong {
	color: #29343e;
	font-weight: 600
}

.hero-actions {
	display: flex;
	align-items: center;
	gap: 27px;
	margin-top: 32px
}

.button {
	display: inline-flex;
	align-items: center;
	gap: 22px;
	padding: 14px 18px;
	text-decoration: none;
	border-radius: 6px;
	font-size: 12px;
	font-weight: 600
}

.button-dark {
	background: var(--ink);
	color: #fff;
	box-shadow: 0 7px 20px #14202b1c
}

.button-dark span {
	font-size: 16px;
	color: #aec7ff
}

.text-link {
	font-size: 12px;
	font-weight: 600;
	color: var(--ink);
	text-decoration: none
}

.text-link span {
	color: var(--blue);
	padding-left: 5px
}

.hero-meta {
	margin-top: 42px;
	display: flex;
	align-items: center;
	gap: 17px;
	color: #87919a;
	font: 10px var(--mono);
	letter-spacing: .4px
}

.pin {
	font-size: 15px;
	color: var(--blue);
	font-style: normal;
	margin-right: 5px
}

.meta-divider {
	height: 17px;
	width: 1px;
	background: #dce1e4
}

.hero-art {
	height: 430px;
	position: relative;
	display: grid;
	place-items: center;
	isolation: isolate
}

.art-glow {
	position: absolute;
	width: 345px;
	height: 345px;
	border-radius: 50%;
	background: radial-gradient(circle, #e5e9ff 0%, #e8eff5 54%, transparent 72%);
	z-index: -2
}

.art-orbit {
	position: absolute;
	border: 1px solid #d5dce8;
	border-radius: 50%;
	transform: rotate(-24deg);
	width: 465px;
	height: 200px;
	z-index: -1
}

.orbit-two {
	transform: rotate(57deg);
	width: 420px;
	height: 190px;
	border-color: #e3dced
}

.code-card {
	width: 340px;
	background: #202938;
	border-radius: 12px;
	box-shadow: 0 30px 70px #24374d2e;
	overflow: hidden;
	transform: rotate(-4deg);
	z-index: 1
}

.window-dots {
	height: 43px;
	border-bottom: 1px solid #ffffff12;
	display: flex;
	align-items: center;
	gap: 5px;
	padding: 0 15px
}

.window-dots i {
	width: 7px;
	height: 7px;
	border-radius: 50%;
	background: #f47c78
}

.window-dots i:nth-child(2) {
	background: #eabc68
}

.window-dots i:nth-child(3) {
	background: #76c39e
}

.window-dots span {
	margin-left: auto;
	font: 9px var(--mono);
	color: #8a98a9
}

.code-lines {
	padding: 17px 22px 20px;
	font: 11px/1.9 var(--mono);
	color: #d6dfeb
}

.code-lines p {
	margin: 0
}

.code-lines b {
	color: #dc82cf;
	font-weight: 400
}

.code-purple {
	color: #a89afa
}

.code-green {
	color: #a4d59c
}

.code-lines em {
	font-style: normal;
	color: #e4a96d
}

.indent {
	padding-left: 18px
}

.cursor {
	display: inline-block;
	height: 13px;
	width: 1px;
	background: #8e9df9;
	vertical-align: middle;
	margin-left: 4px
}

.floating-chip {
	position: absolute;
	z-index: 2;
	background: #fff;
	padding: 11px 14px;
	border: 1px solid #edf0f3;
	border-radius: 8px;
	box-shadow: 0 10px 28px #1b2c3a12;
	display: flex;
	align-items: center;
	gap: 10px
}

.floating-chip b {
	display: block;
	font-size: 10px
}

.floating-chip small {
	display: block;
	font-size: 9px;
	color: #8a949c;
	margin-top: 3px
}

.chip-top {
	top: 65px;
	right: 5px
}

.chip-bottom {
	bottom: 65px;
	left: 5px
}

.chip-icon {
	width: 28px;
	height: 28px;
	border-radius: 7px;
	display: grid;
	place-items: center;
	font-size: 15px
}

.chip-icon.purple {
	color: #7062c8;
	background: #f0edff
}

.chip-icon.mint {
	color: #318969;
	background: #e5f6ec
}

.art-label {
	position: absolute;
	bottom: 17px;
	right: 38px;
	font-size: 9px;
	color: #a3acb2
}

.art-label span {
	color: #6475de
}

.scroll-cue {
	position: absolute;
	bottom: 35px;
	left: 0;
	display: flex;
	align-items: center;
	gap: 12px;
	font-size: 8px;
	color: #9ba4aa
}

.scroll-cue span {
	height: 30px;
	width: 18px;
	border: 1px solid #cbd3d8;
	border-radius: 10px;
	position: relative
}

.scroll-cue span:after {
	content: '';
	position: absolute;
	width: 2px;
	height: 5px;
	background: #6777da;
	left: 7px;
	top: 6px;
	border-radius: 2px
}

.section-pad {
	padding: 104px 0
}

.about {
	background: #f0f3f5;
	border-block: 1px solid #e8ecef
}

.about-grid {
	display: grid;
	grid-template-columns: 160px 1.45fr .8fr;
	gap: 56px
}

.section-kicker {
	display: flex;
	align-items: center;
	gap: 10px;
	color: #9aa4aa;
	font-size: 9px;
	white-space: nowrap
}

.section-kicker>span:first-child {
	color: var(--blue)
}

.kicker-line {
	height: 1px;
	width: 27px;
	background: #cbd2d8
}

.section-overline {
	font-size: 9px;
	color: #88949c;
	margin: 0 0 17px
}

.about-main h2,
.section-head h2,
.journey h2,
.contact h2 {
	font-weight: 500;
	font-size: clamp(37px, 4.4vw, 54px);
	line-height: 1.17;
	letter-spacing: -2.4px;
	margin: 0 0 22px
}

.serif-accent {
	font-family: 'Playfair Display', serif;
	font-weight: 500;
	font-style: italic;
	color: #6979d6;
	letter-spacing: -1.7px
}

.about-text {
	font-size: 13px;
	color: #6d7880;
	line-height: 1.9;
	margin: 0 0 13px;
	max-width: 590px
}

.underlined {
	display: inline-block;
	border-bottom: 1px solid #bec6cb;
	padding: 0 0 7px;
	margin-top: 14px
}

.about-side {
	padding-top: 15px
}

.stat-card {
	padding: 15px 0;
	border-bottom: 1px solid #dce2e5;
	display: flex;
	align-items: center;
	gap: 17px
}

.stat-card strong {
	font-size: 38px;
	letter-spacing: -2px;
	font-weight: 500
}

.stat-card strong span {
	color: var(--blue)
}

.stat-card>span {
	font-size: 10px;
	color: #73808a;
	line-height: 1.6
}

.stack-block {
	margin-top: 25px
}

.stack-block .section-overline {
	font-size: 8px
}

.tags {
	display: flex;
	flex-wrap: wrap;
	gap: 7px
}

.tags span {
	font-size: 9px;
	color: #65717b;
	padding: 7px 9px;
	background: #fff;
	border: 1px solid #e7ecef;
	border-radius: 4px
}

.portfolio {
	background: #fbfcfd
}

.section-head {
	display: flex;
	align-items: end;
	justify-content: space-between;
	margin-bottom: 34px
}

.section-head .section-overline {
	margin: 27px 0 12px
}

.section-head h2 {
	margin-bottom: 0
}

.section-summary {
	font-size: 12px;
	line-height: 1.8;
	color: #818c94;
	max-width: 280px;
	margin: 0 0 5px
}

.filter-row {
	display: flex;
	gap: 8px;
	margin-bottom: 24px
}

.filter-row button {
	background: transparent;
	border: 1px solid #e3e8eb;
	color: #7b868e;
	border-radius: 4px;
	padding: 8px 12px;
	font: 10px var(--mono);
	cursor: pointer;
	transition: .2s
}

.filter-row button.selected,
.filter-row button:hover {
	background: var(--ink);
	border-color: var(--ink);
	color: white
}

.filter-row button span {
	opacity: .65
}

.project-grid {
	display: grid;
	grid-template-columns: repeat(3, 1fr);
	gap: 17px
}

.project-card {
	background: white;
	border: 1px solid #e8ecef;
	border-radius: 7px;
	overflow: hidden;
	transition: transform .25s, box-shadow .25s
}

.project-card:hover {
	transform: translateY(-4px);
	box-shadow: 0 15px 35px #1e2b3810
}

.project-visual {
	height: 194px;
	display: grid;
	place-items: center;
	position: relative;
	overflow: hidden;
	background: #e9edff
}

.project-visual:before,
.project-visual:after {
	content: '';
	position: absolute;
	width: 230px;
	height: 230px;
	border: 1px solid #ffffff8a;
	border-radius: 50%;
	transform: translate(85px, -96px)
}

.project-visual:after {
	width: 280px;
	height: 280px;
	transform: translate(-140px, 118px)
}

.project-visual.violet {
	background: #eee9fc
}

.project-visual.orange {
	background: #fcf0e4
}

.project-visual.green {
	background: #e8f3ed
}

.project-visual.pink {
	background: #f8eaf0
}

.project-visual.cyan {
	background: #e5f2f3
}

.mock-window {
	width: 75%;
	height: 137px;
	background: #fff;
	border-radius: 5px;
	box-shadow: 0 12px 28px #283c5520;
	overflow: hidden;
	transform: translateY(8px);
	z-index: 1
}

.mock-top {
	height: 20px;
	background: #fafbfc;
	border-bottom: 1px solid #eff1f3;
	display: flex;
	gap: 3px;
	align-items: center;
	padding: 0 7px
}

.mock-top span {
	width: 4px;
	height: 4px;
	background: #d7dce2;
	border-radius: 50%
}

.mock-top i {
	font: 5px var(--mono);
	color: #9da6ad;
	margin: auto;
	font-style: normal
}

.mock-layout {
	display: flex;
	height: calc(100% - 20px)
}

.mock-sidebar {
	width: 22%;
	background: #252f3d;
	display: flex;
	align-items: center;
	flex-direction: column;
	gap: 8px;
	padding-top: 12px
}

.mock-sidebar b {
	width: 18px;
	height: 5px;
	background: #7883d3;
	border-radius: 2px;
	margin-bottom: 4px
}

.mock-sidebar i {
	width: 24px;
	height: 3px;
	background: #586270;
	border-radius: 2px
}

.mock-content {
	padding: 11px 10px;
	flex: 1
}

.mock-title {
	width: 45px;
	height: 6px;
	background: #4958a4;
	border-radius: 2px;
	margin-bottom: 8px
}

.mock-stat-row {
	display: flex;
	gap: 5px
}

.mock-stat-row i {
	height: 17px;
	flex: 1;
	border: 1px solid #ebedf0;
	border-radius: 2px;
	background: linear-gradient(90deg, #fff, #f8f9fa)
}

.mock-chart {
	height: 36px;
	border-bottom: 1px solid #e9edf0;
	display: flex;
	align-items: end;
	gap: 7px;
	padding: 0 7px;
	margin-top: 8px
}

.mock-chart span {
	flex: 1;
	background: #a4abec;
	border-radius: 2px 2px 0 0;
	height: 35%
}

.mock-chart span:nth-child(2) {
	height: 65%
}

.mock-chart span:nth-child(3) {
	height: 48%
}

.mock-chart span:nth-child(4) {
	height: 82%
}

.mock-chart span:nth-child(5) {
	height: 57%
}

.mock-chart span:nth-child(6) {
	height: 92%
}

.mock-chart span:nth-child(7) {
	height: 70%
}

.mock-table {
	display: flex;
	gap: 5px;
	margin-top: 7px
}

.mock-table i {
	height: 3px;
	background: #e5e9ec;
	flex: 1
}

.visual-number {
	position: absolute;
	bottom: 11px;
	right: 13px;
	font: 8px var(--mono);
	color: #647079;
	z-index: 2
}

.project-info {
	padding: 17px 16px 14px;
	position: relative
}

.project-type {
	font-size: 8px;
	color: #8e99a1
}

.project-info h3 {
	font-size: 15px;
	font-weight: 600;
	letter-spacing: -.3px;
	margin: 5px 0 0
}

.project-arrow {
	position: absolute;
	right: 16px;
	top: 29px;
	width: 28px;
	height: 28px;
	border: 1px solid #e8ecef;
	border-radius: 50%;
	display: grid;
	place-items: center;
	color: #6d7ddd;
	font-size: 12px
}

.project-info p {
	font-size: 10px;
	line-height: 1.7;
	color: #828c93;
	min-height: 34px;
	margin: 11px 0 17px
}

.project-footer {
	border-top: 1px solid #edf0f2;
	padding-top: 11px;
	display: flex;
	justify-content: space-between;
	font-size: 7px;
	color: #9aa3a9;
	letter-spacing: .4px
}

.project-footer a {
	color: #6978d0;
	text-decoration: none
}

.all-projects {
	display: flex;
	justify-content: center;
	align-items: center;
	gap: 10px;
	color: #818c94;
	font-size: 11px;
	margin-top: 31px
}

.all-projects .underlined {
	margin-top: 0
}

.journey {
	background: #f0f3f5;
	border-block: 1px solid #e8ecef
}

.journey-grid {
	display: grid;
	grid-template-columns: .8fr 1.2fr;
	gap: 100px
}

.journey .section-overline {
	margin-top: 34px
}

.journey h2 {
	font-size: 50px
}

.journey-intro {
	font-size: 12px;
	line-height: 1.8;
	color: #7e8991;
	max-width: 240px;
	margin-top: 24px
}

.timeline-column {
	position: relative;
	padding-left: 23px;
	border-left: 1px solid #d6dde1
}

.timeline-heading {
	display: flex;
	align-items: center;
	gap: 13px;
	margin: 2px 0 24px;
	position: relative
}

.timeline-icon {
	width: 30px;
	height: 30px;
	border-radius: 8px;
	background: white;
	color: #6879d7;
	display: grid;
	place-items: center;
	font-size: 15px
}

.timeline-heading p {
	color: #929ca3;
	font-size: 8px;
	margin: 0 0 5px
}

.timeline-heading h3 {
	font-size: 13px;
	font-weight: 600;
	margin: 0
}

.timeline-item {
	padding: 0 0 21px 43px;
	position: relative
}

.timeline-item:before {
	content: '';
	position: absolute;
	width: 7px;
	height: 7px;
	border: 2px solid #7a87df;
	background: #f0f3f5;
	border-radius: 50%;
	left: -28px;
	top: 2px
}

.timeline-year {
	font-size: 8px;
	color: #8d98a0
}

.timeline-item h4 {
	font-size: 12px;
	margin: 7px 0 3px;
	font-weight: 600
}

.timeline-item>p {
	font-size: 10px;
	color: #7b8790;
	margin: 0 0 7px
}

.timeline-detail {
	display: block;
	font-size: 10px;
	color: #909aa1;
	line-height: 1.65;
	max-width: 430px
}

.exp-heading {
	margin-top: 17px
}

.contact {
	background: #1d2935;
	color: white;
	padding-bottom: 51px
}

.contact-wrap {
	position: relative
}

.light-kicker {
	color: #aab4bc
}

.light-kicker .kicker-line {
	background: #47535d
}

.contact .section-overline {
	color: #98a7b2;
	margin-top: 57px
}

.contact h2 {
	font-size: clamp(47px, 6vw, 72px);
	margin-bottom: 16px
}

.contact .serif-accent {
	color: #aeb9ff
}

.contact-copy {
	font-size: 12px;
	line-height: 1.8;
	color: #a8b1b8;
	max-width: 420px;
	margin: 0 0 25px
}

.contact-email {
	font-size: 17px;
	color: white;
	text-decoration: none;
	border-bottom: 1px solid #66737f;
	padding-bottom: 9px;
	display: inline-flex;
	gap: 30px;
	align-items: center
}

.contact-email span {
	color: #aeb9ff
}

.contact-bottom {
	display: flex;
	justify-content: space-between;
	align-items: center;
	border-top: 1px solid #38444e;
	margin-top: 75px;
	padding-top: 18px;
	color: #87939c;
	font-size: 8px;
	letter-spacing: .7px
}

.social-links {
	display: flex;
	gap: 23px
}

.social-links a {
	color: #c2c9ce;
	text-decoration: none;
	font: 8px var(--mono);
	letter-spacing: .5px
}

.footer {
	background: #17212b;
	color: #8e999f;
	padding: 16px 0
}

.footer-inner {
	display: flex;
	justify-content: space-between;
	align-items: center
}

.footer .brand {
	color: white;
	font-size: 14px
}

.footer .brand-mark {
	height: 25px;
	width: 25px;
	font-size: 15px;
	border: 1px solid #58616a;
	background: transparent
}

.footer-inner>span,
.footer-inner>a:last-child {
	font: 8px var(--mono);
	color: #84919a;
	text-decoration: none;
	letter-spacing: .5px
}

@media(max-width:950px) {
	.nav-links {
		gap: 16px
	}

	.nav-links>a {
		font-size: 10px
	}

	.nav-links .nav-cta {
		padding: 9px
	}

	.hero {
		min-height: 590px
	}

	.hero-art {
		transform: scale(.88)
	}

	.about-grid {
		grid-template-columns: 115px 1.4fr .8fr;
		gap: 28px
	}

	.journey-grid {
		gap: 50px
	}

	.project-grid {
		grid-template-columns: repeat(2, 1fr)
	}
}

@media(max-width:700px) {
	.wrap {
		width: min(100% - 40px, 520px)
	}

	.topbar {
		height: 67px
	}

	.menu-toggle {
		display: flex;
		width: 38px;
		height: 38px;
		border: 1px solid #e3e8eb;
		border-radius: 7px;
		background: white;
		align-items: center;
		justify-content: center;
		flex-direction: column;
		gap: 5px
	}

	.menu-toggle span {
		height: 1px;
		width: 15px;
		background: #2b3741
	}

	.nav-links {
		display: none;
		position: absolute;
		top: 66px;
		left: 0;
		right: 0;
		padding: 17px 20px 22px;
		background: #fbfcfd;
		border-bottom: 1px solid var(--line);
		box-shadow: 0 15px 25px #20304010;
		align-items: stretch;
		flex-direction: column;
		gap: 0
	}

	.nav-links.open {
		display: flex
	}

	.nav-links>a {
		font-size: 13px;
		padding: 12px 4px;
		border-bottom: 1px solid #edf0f2
	}

	.nav-links .nav-cta {
		margin-top: 12px;
		text-align: center;
		border: 1px solid #dce2e7
	}

	.hero {
		display: flex;
		flex-direction: column;
		align-items: flex-start;
		padding-top: 75px;
		padding-bottom: 72px;
		min-height: 0
	}

	.hero h1 {
		font-size: 52px;
		letter-spacing: -3.4px
	}

	.hero-lead {
		font-size: 13px
	}

	.hero-art {
		width: 100%;
		height: 325px;
		transform: scale(.86);
		transform-origin: center;
		margin: -2px 0 -6px
	}

	.code-card {
		width: 315px
	}

	.art-glow {
		width: 300px;
		height: 300px
	}

	.art-orbit {
		width: 370px
	}

	.chip-top {
		right: -7px;
		top: 35px
	}

	.chip-bottom {
		left: -9px;
		bottom: 35px
	}

	.scroll-cue {
		bottom: 22px
	}

	.hero-meta {
		margin-top: 31px;
		font-size: 8px;
		gap: 10px
	}

	.section-pad {
		padding: 75px 0
	}

	.about-grid {
		grid-template-columns: 1fr;
		gap: 27px
	}

	.about-grid>.section-kicker {
		order: 0
	}

	.about-main {
		order: 1
	}

	.about-side {
		order: 2;
		display: grid;
		grid-template-columns: 1fr 1fr;
		gap: 0 16px;
		padding-top: 0
	}

	.stack-block {
		grid-column: 1/-1
	}

	.about-main h2,
	.section-head h2,
	.journey h2 {
		font-size: 40px
	}

	.about-text {
		font-size: 12px
	}

	.stat-card {
		gap: 9px
	}

	.stat-card strong {
		font-size: 32px
	}

	.stat-card>span {
		font-size: 9px
	}

	.section-head {
		display: block
	}

	.section-head .section-overline {
		margin-top: 27px
	}

	.section-summary {
		margin-top: 18px;
		max-width: 390px
	}

	.project-grid {
		grid-template-columns: 1fr;
		gap: 13px
	}

	.project-visual {
		height: 200px
	}

	.project-info p {
		min-height: 0
	}

	.filter-row {
		overflow: auto
	}

	.filter-row button {
		white-space: nowrap
	}

	.all-projects {
		flex-wrap: wrap
	}

	.journey-grid {
		grid-template-columns: 1fr;
		gap: 35px
	}

	.journey .section-overline {
		margin-top: 27px
	}

	.journey h2 {
		font-size: 43px
	}

	.journey-intro {
		margin-top: 16px
	}

	.timeline-column {
		margin-left: 4px
	}

	.contact .section-overline {
		margin-top: 43px
	}

	.contact h2 {
		font-size: 49px
	}

	.contact-email {
		font-size: 14px;
		gap: 18px
	}

	.contact-bottom {
		align-items: flex-start;
		gap: 18px;
		flex-direction: column;
		margin-top: 54px
	}

	.social-links {
		gap: 14px
	}

	.footer-inner {
		flex-wrap: wrap;
		gap: 15px
	}

	.footer-inner>span {
		order: 3;
		width: 100%
	}
}

@media(prefers-reduced-motion:reduce) {
	html {
		scroll-behavior: auto
	}

	*,
	*:before,
	*:after {
		transition: none !important
	}
}
</style>
