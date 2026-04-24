---
permalink: /scratch-attack/
title: "Course Project: Optical Adversarial Attacks on Vision Systems"
excerpt: "A course project report on scratch-induced optical artifacts and their impact on depth-related vision tasks."
author_profile: true
---

<style>
.project-post {
  --ink: #20262e;
  --muted: #5b6573;
  --line: #dce1e8;
  --paper: #ffffff;
  --soft: #f4f7fb;
  --accent: #0b5cab;
  --accent-2: #0f8a70;
}
.project-post .hero {
  background: linear-gradient(135deg, #f8fbff 0%, #eef5ff 45%, #eef9f7 100%);
  border: 1px solid var(--line);
  border-radius: 16px;
  padding: 1.5rem;
  margin-bottom: 1rem;
}
.project-post .eyebrow {
  color: var(--accent);
  letter-spacing: 0.08em;
  font-size: 0.78rem;
  text-transform: uppercase;
  font-weight: 700;
  margin: 0 0 0.6rem 0;
}
.project-post .hero h1 {
  margin: 0 0 0.8rem 0;
  font-size: 1.9rem;
  line-height: 1.2;
}
.project-post .lede {
  color: var(--muted);
  font-size: 1.02rem;
  margin: 0;
}
.project-post .meta {
  display: flex;
  flex-wrap: wrap;
  gap: 0.5rem;
  margin-top: 1rem;
}
.project-post .meta span {
  border: 1px solid #cfe0f3;
  background: rgba(255, 255, 255, 0.8);
  border-radius: 999px;
  padding: 0.25rem 0.7rem;
  font-size: 0.84rem;
  color: #2d3a4a;
}
.project-post .jump-nav {
  display: flex;
  flex-wrap: wrap;
  gap: 0.45rem;
  margin: 0 0 1rem 0;
}
.project-post .jump-nav a {
  display: inline-block;
  text-decoration: none;
  color: var(--accent);
  border: 1px solid #c7daef;
  border-radius: 8px;
  padding: 0.24rem 0.6rem;
  font-size: 0.84rem;
  background: #fafcff;
}
.project-post .block {
  background: var(--paper);
  border: 1px solid var(--line);
  border-radius: 14px;
  padding: 1.1rem;
  margin: 0 0 1rem 0;
}
.project-post h2 {
  margin-top: 0;
  border-left: 4px solid var(--accent);
  padding-left: 0.6rem;
}
.project-post .summary-grid {
  display: grid;
  grid-template-columns: repeat(3, minmax(0, 1fr));
  gap: 0.7rem;
  margin-top: 0.8rem;
}
.project-post .summary-card {
  border: 1px solid #dde6f1;
  border-radius: 10px;
  padding: 0.8rem;
  background: var(--soft);
}
.project-post .summary-card h4 {
  margin: 0 0 0.35rem 0;
  color: #243142;
  font-size: 0.93rem;
}
.project-post .summary-card p {
  margin: 0;
  color: var(--muted);
  font-size: 0.86rem;
}
.project-post .fig-grid {
  display: grid;
  grid-template-columns: repeat(2, minmax(0, 1fr));
  gap: 0.8rem;
}
.project-post figure {
  margin: 0;
  border: 1px solid var(--line);
  border-radius: 12px;
  overflow: hidden;
  background: #fff;
}
.project-post figure img {
  width: 100%;
  display: block;
}
.project-post figcaption {
  padding: 0.6rem 0.7rem;
  font-size: 0.82rem;
  color: var(--muted);
  border-top: 1px solid #ebeff5;
}
.project-post .metric-box {
  border: 1px solid #d5e5dc;
  background: #f4fbf8;
  border-radius: 10px;
  padding: 0.8rem;
  margin: 0.8rem 0 1rem 0;
}
.project-post table {
  width: 100%;
  border-collapse: collapse;
  font-size: 0.9rem;
}
.project-post th, .project-post td {
  border: 1px solid #d9dfe8;
  padding: 0.5rem;
  text-align: left;
}
.project-post th {
  background: #f3f7fd;
}
.project-post .cols-2 {
  display: grid;
  grid-template-columns: repeat(2, minmax(0, 1fr));
  gap: 0.8rem;
}
.project-post .note {
  border-left: 4px solid var(--accent-2);
  background: #f2fbf8;
  border-radius: 8px;
  padding: 0.8rem 0.9rem;
  color: #2d4a43;
  margin-top: 0.7rem;
}
@media (max-width: 900px) {
  .project-post .summary-grid,
  .project-post .fig-grid,
  .project-post .cols-2 {
    grid-template-columns: 1fr;
  }
  .project-post .hero h1 {
    font-size: 1.55rem;
  }
}
</style>

<div class="project-post">

<section class="hero">
  <p class="eyebrow">Course Project Report · Spring 2026</p>
  <h1>Optical Adversarial Attacks on Vision Systems</h1>
  <p class="lede">This project investigates scratch-induced optical artifacts as a camera-side attack surface and evaluates their influence on depth estimation and monocular 3D detection.</p>
  <div class="meta">
    <span><strong>Authors:</strong> Qinlin He, Zeming Zhuang</span>
    <span><strong>Scope:</strong> Camera-side physical and digital evaluation</span>
    <span><strong>Type:</strong> Course Project</span>
  </div>
</section>

<nav class="jump-nav">
  <a href="#abstract">Abstract</a>
  <a href="#problem-setup">Problem Setup</a>
  <a href="#optical-mechanism">Optical Mechanism</a>
  <a href="#experiment-setup">Experiment Setup</a>
  <a href="#results">Results</a>
  <a href="#limitations">Limitations</a>
  <a href="#takeaways">Takeaways</a>
</nav>

<section id="abstract" class="block">
  <h2>Abstract</h2>
  <p>This course project studies a practical attack surface where small lens scratches scatter light and form structured flare artifacts under strong illumination. We build physical and digital evaluation pipelines and quantify the effect on depth-related perception. Across multiple settings, scratch-induced artifacts lead to clear depth distortion and measurable geometry errors while the external scene itself remains unchanged.</p>
  <div class="summary-grid">
    <div class="summary-card">
      <h4>Threat Surface</h4>
      <p>Camera-side optical perturbation during image formation.</p>
    </div>
    <div class="summary-card">
      <h4>Target Tasks</h4>
      <p>Depth estimation and monocular 3D object detection.</p>
    </div>
    <div class="summary-card">
      <h4>Main Finding</h4>
      <p>Small physical defects can reliably induce large geometry shifts.</p>
    </div>
  </div>
</section>

<section id="problem-setup" class="block">
  <h2>Problem Setup</h2>
  <p>Real camera lenses can accumulate tiny scratches over time. Under bright point sources such as headlights, these scratches may produce linear flare artifacts that occlude details or introduce misleading structures for downstream vision models.</p>
  <div class="fig-grid">
    <figure>
      <img src="/assets/projects/scratch-attack/real-world-scratches-1.png" alt="Real-world lens scratches example 1">
      <figcaption>Figure 1. Real-world lens scratch pattern (example A).</figcaption>
    </figure>
    <figure>
      <img src="/assets/projects/scratch-attack/real-world-scratches-2.png" alt="Real-world lens scratches example 2">
      <figcaption>Figure 2. Real-world lens scratch pattern (example B).</figcaption>
    </figure>
  </div>
  <figure style="margin-top:0.8rem;">
    <img src="/assets/projects/scratch-attack/physical-adversarial-attacks.png" alt="Physical adversarial attack categories">
    <figcaption>Figure 3. Representative directions in physical attacks on vision systems.</figcaption>
  </figure>
</section>

<section id="optical-mechanism" class="block">
  <h2>Optical Mechanism</h2>
  <p>A linear scratch perturbs the incident light path and introduces a scattered component. With strong light sources in the scene, this scattered component appears as structured streaks in the image plane. We use a geometry-based view to model this effect for attack construction and analysis.</p>
  <div class="fig-grid">
    <figure>
      <img src="/assets/projects/scratch-attack/lens-scratches-microscope.jpg" alt="Microscopic scratch image">
      <figcaption>Figure 4. Microscopic appearance of lens scratches.</figcaption>
    </figure>
    <figure>
      <img src="/assets/projects/scratch-attack/light-path-focused-vs-scratch-scattered.png" alt="Light path diagram">
      <figcaption>Figure 5. Focused path versus scratch-scattered path.</figcaption>
    </figure>
  </div>
  <figure style="margin-top:0.8rem;">
    <img src="/assets/projects/scratch-attack/attack-surface-overview.png" alt="Attack surface overview">
    <figcaption>Figure 6. Camera-side attack surface compared with object-side perturbations.</figcaption>
  </figure>
</section>

<section id="experiment-setup" class="block">
  <h2>Experiment Setup</h2>
  <div class="cols-2">
    <div>
      <h3>Physical Pipeline</h3>
      <ul>
        <li>Scratch patterns are engraved on an acrylic plate.</li>
        <li>The plate is placed near the lens under strong illumination.</li>
        <li>Depth behavior is evaluated under benign and attacked captures.</li>
      </ul>
    </div>
    <div>
      <h3>Digital Pipeline</h3>
      <ul>
        <li>Night-time driving scenes are selected for evaluation.</li>
        <li>Scratch-induced flare is simulated by image-space editing.</li>
        <li>Monocular 3D detection geometry errors are measured.</li>
      </ul>
    </div>
  </div>
  <figure style="margin-top:0.8rem;">
    <img src="/assets/projects/scratch-attack/physical-attack-setup.png" alt="Physical attack setup">
    <figcaption>Figure 7. Course project physical setup for scratch-induced flare testing.</figcaption>
  </figure>
</section>

<section id="results" class="block">
  <h2>Results</h2>
  <h3>Depth Estimation</h3>
  <p>Attacked inputs can produce hallucinated near obstacles and stronger local distortions around bright light sources.</p>
  <div class="fig-grid">
    <figure>
      <img src="/assets/projects/scratch-attack/monodepth2-benign-vs-attacked.png" alt="Monodepth2 benign vs attacked">
      <figcaption>Figure 8. Benign and attacked depth predictions.</figcaption>
    </figure>
    <figure>
      <img src="/assets/projects/scratch-attack/table-impact-depth-estimation.png" alt="Depth estimation impact table">
      <figcaption>Figure 9. Summary of depth impact under scratch-induced flare artifacts.</figcaption>
    </figure>
  </div>

  <h3 style="margin-top:1rem;">3D Detection Geometry Error</h3>
  <div class="metric-box">
    <table>
      <thead>
        <tr>
          <th>Setting</th>
          <th>PGD</th>
          <th>FCOS3D</th>
        </tr>
      </thead>
      <tbody>
        <tr>
          <td>Pushing direction</td>
          <td>2.9% -&gt; 14.9%</td>
          <td>3.5% -&gt; 18.4%</td>
        </tr>
        <tr>
          <td>Pulling direction</td>
          <td>2.8% -&gt; 8.5%</td>
          <td>3.5% -&gt; 7.6%</td>
        </tr>
        <tr>
          <td>Multi-frame setting</td>
          <td>2.7% -&gt; 5.8%</td>
          <td>3.6% -&gt; 7.2%</td>
        </tr>
      </tbody>
    </table>
  </div>

  <div class="fig-grid">
    <figure>
      <img src="/assets/projects/scratch-attack/impact-3d-detection-pushing.png" alt="Pushing results">
      <figcaption>Figure 10. Error increase in the pushing setting.</figcaption>
    </figure>
    <figure>
      <img src="/assets/projects/scratch-attack/impact-3d-detection-pulling.png" alt="Pulling results">
      <figcaption>Figure 11. Error increase in the pulling setting.</figcaption>
    </figure>
    <figure>
      <img src="/assets/projects/scratch-attack/impact-3d-detection-multi-frame.png" alt="Multi-frame results">
      <figcaption>Figure 12. Error increase in the multi-frame setting.</figcaption>
    </figure>
    <figure>
      <img src="/assets/projects/scratch-attack/table-optimizer-ablation-study.png" alt="Optimizer ablation">
      <figcaption>Figure 13. Optimizer ablation across attack configurations.</figcaption>
    </figure>
  </div>

  <figure style="margin-top:0.8rem;">
    <img src="/assets/projects/scratch-attack/examples-3d-detection.png" alt="3D detection examples">
    <figcaption>Figure 14. Qualitative examples in image and BEV views.</figcaption>
  </figure>
  <div class="note"><strong>Observation:</strong> Even small camera-side perturbations can lead to consistent geometry-level errors across multiple evaluation settings.</div>
</section>

<section id="limitations" class="block">
  <h2>Limitations</h2>
  <ul>
    <li>Current experiments emphasize strong-light and night-scene conditions.</li>
    <li>Scratch parameterization is simplified and does not cover every defect morphology.</li>
    <li>Cross-device generalization requires broader camera hardware testing.</li>
  </ul>
</section>

<section id="takeaways" class="block">
  <h2>Takeaways</h2>
  <ul>
    <li>Camera-side optical artifacts are a meaningful and practical robustness concern.</li>
    <li>Minor lens defects can induce structured perturbations that shift depth cues.</li>
    <li>Depth-aware perception systems should include optical artifact stress tests in evaluation pipelines.</li>
  </ul>
</section>

</div>
