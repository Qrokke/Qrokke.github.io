---
layout: default
title: About
description: Personal research page of Asahi Kurokawa — haptics, soft vibrotactile actuators, VR.
---

<section class="hero framed">
  <p class="eyebrow mono">Research Notebook</p>
  <h1>Making virtual surfaces touchable.</h1>
  <p class="lead">
    I study <strong>soft vibrotactile actuators built from liquid metal</strong> and how they can
    reproduce the sensation of <em>tracing</em> — the way we rub a fingertip across a surface to
    understand what it is made of. My goal is a haptic display, small and safe enough for everyday
    devices, that lets people feel the texture of virtual objects in VR and on ordinary screens.
  </p>
</section>

<section class="grid-2">
  <div class="framed card">
    <h2><span class="mono num">A.</span> Who I am</h2>
    <p>
      Master's student at the <strong>Media Experience Design Lab</strong>,
      Graduate School of Information Science and Engineering,
      <strong>Ritsumeikan University</strong> (Ibaraki, Osaka, Japan),
      supervised by Prof. Haruo Noma and Asst. Prof. Mitsuhito Ando.
    </p>
    <ul class="plain">
      <li><span class="mono">ORCID</span> <a href="https://orcid.org/0009-0007-2401-8095">0009-0007-2401-8095</a></li>
      <li><span class="mono">Interests</span> Haptics, vibrotactile displays, soft robotics, VR</li>
      <li><span class="mono">Societies</span> VRSJ · IEEE · JSME</li>
    </ul>
  </div>

  <div class="framed card">
    <h2><span class="mono num">B.</span> What I build</h2>
    <p>
      Actuators made of <strong>silicone tubes filled with a GaInSn liquid-metal alloy</strong>,
      driven by electromagnetic force. Because the structure is soft, thin (~1&nbsp;mm), and
      low-voltage, it can sit directly under the fingertip — inside a computer mouse
      (<em>SVA-M</em>) or as a wearable shear-vibration display (<em>SCA</em>) —
      and deliver wideband (1–500&nbsp;Hz), low-latency vibration.
    </p>
  </div>
</section>

<section class="framed card">
  <h2><span class="mono num">C.</span> Current directions</h2>
  <ul>
    <li><strong>Texture rendering during active tracing.</strong> Quantifying the spatial resolution of haptic textures that users can reliably discriminate while moving their own hand.</li>
    <li><strong>Shear vibrotactile stimulation.</strong> Reproducing the skin-drag component of tracing with a soft coil actuator.</li>
    <li><strong>Toward multimodal fingertip feedback.</strong> Integrating vibrotactile, thermal, and force cues into a unified, compact, wearable display for material perception in VR.</li>
  </ul>
</section>

<section class="framed card">
  <h2><span class="mono num">D.</span> News</h2>
  <ul class="news">
    {% assign news = site.data.news | sort: "date" | reverse %}
    {% for item in news limit: 6 %}
    <li>
      <time class="mono">{{ item.date }}</time>
      <span>{{ item.text | markdownify | remove: '<p>' | remove: '</p>' }}</span>
    </li>
    {% endfor %}
  </ul>
</section>
