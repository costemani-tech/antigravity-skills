---
name: camera-movements-ai
description: Guia e vocabulário técnico de movimentações de câmera, iluminação cinematográfica, lentes e enquadramentos (inspirado no Director's Eye do MoodNode) para geração de vídeos de IA (Veo 3, Google Flow, Sora, Runway, Kling, Flux).
---

# 🎥 Camera Movements & Cinema Techniques for AI Video Prompts (Skill)

> Esta skill fornece o vocabulário técnico, a sintaxe exata e dicas de engenharia de prompt (*Director's Eye*) para aplicar em IAs geradoras de vídeo e imagem (Veo 3, Google Flow, Sora, Kling, Runway, Flux, Midjourney).

---

## 💡 Regras de Engenharia de Prompt (Director's Eye - Pro Tips)

1. **Posição da Instrução:** Adicione a instrução da câmera e estilo cinematográfico sempre no **início** ou no **bloco de enquadramento** do prompt em inglês.
2. **Especificidade numéricas evitam alucinação:**
   - ❌ Em vez de apenas `Dutch Angle`, use: `Dutch angle, camera tilted 25 degrees clockwise, diagonal horizon line`.
   - ❌ Em vez de apenas `Bird's Eye View`, use: `True bird's eye view, camera directly overhead at 90 degrees pointing straight down, only top of head visible`.
   - ❌ Em vez de apenas `Medium shot`, especifique a linha de corte: `Medium shot, framed strictly from waist up`.
3. **Reforço de Vocabulário:** Combine a técnica de câmera com termos de lente, profundidade de campo e iluminação para forçar o modelo de IA a respeitar a estética cinematográfica.

---

## 📐 Categoria 1: Aproximação e Distanciamento (Dolly & Zoom)

1. **Slow Dolly In**: `Slow dolly in camera shot towards [Subject]` (Aproximação suave - Ideal para HOOKs e foco de fala).
2. **Fast Push In**: `Dynamic fast push-in camera movement on [Subject]` (Aproximação rápida - Ideal para revelações e impactos).
3. **Dolly Zoom (Hitchcock Effect)**: `Dolly zoom effect background expanding while keeping [Subject] fixed` (Efeito vertigem/tensão).
4. **Zoom Out / Pull Back**: `Slow pull back camera shot revealing the surrounding environment` (Revelação do cenário).
5. **Crash Zoom**: `Rapid crash zoom shot focusing on [Subject] face` (Zoom ultra-rápido de estilo dramático).

---

## 🔄 Categoria 2: Rotação e Movimento Orbital (Pan & Orbit)

6. **Smooth Orbital 360**: `Smooth 360-degree orbital camera movement around [Subject]` (Giro panorâmico 360° no personagem).
7. **Panning Shot (Left to Right)**: `Smooth horizontal pan camera moving from left to right` (Varredura de tela).
8. **Tilt Up / Down**: `Smooth camera tilt up from desk to [Subject] face` (Inclinação vertical).
9. **Whip Pan**: `Fast whip pan transition shot` (Transição rápida de chicote).
10. **Arc Shot**: `Semi-circle arc camera movement around [Subject]` (Giro de 180°).

---

## 🏃 Categoria 3: Acompanhamento e Perseguição (Tracking & Follow)

11. **Tracking Shot**: `Smooth horizontal tracking shot following [Subject]` (Câmera anda paralelamente ao personagem).
12. **Follow Shot (Behind)**: `Camera tracking [Subject] from behind walking forward` (Seguindo o personagem por trás).
13. **Lead Shot (Front)**: `Camera moving backwards in front of [Subject] walking` (Acompanhando pela frente).
14. **Over-The-Shoulder (OTS)**: `Over-the-shoulder shot (OTS), foreground shoulder soft blur, background subject sharp focus` (Câmera por cima do ombro).
15. **POV (Point of View)**: `First-person POV shot looking at [Object/Screen]` (Visão em primeira pessoa).

---

## 🎨 Categoria 4: Ângulos e Perspectiva (Angles & Framing)

16. **Low Angle (Hero Shot)**: `EXTREME LOW ANGLE SHOT — camera placed at ground level tilted up 60 degrees, subject towering high above` (Cria autoridade e imponência).
17. **High Angle**: `EXTREME HIGH ANGLE SHOT — camera positioned 12 feet high above subject, tilted down 60 degrees, forced perspective` (Sensação de vulnerabilidade ou visão geral).
18. **Dutch Angle / Canted Frame**: `DUTCH ANGLE / CANTED FRAME — camera tilted on roll axis by 25 degrees clockwise, diagonal horizon line` (Inclinado para tensão ou instabilidade).
19. **Bird's Eye View (Top Down 90°)**: `TRUE BIRD'S EYE VIEW — camera directly overhead pointing straight down at 90 degrees, top of head visible, flat overhead pattern` (Visão aérea vertical de 90°).
20. **Worm's Eye View**: `WORM'S EYE VIEW — camera flat on the ground looking straight up, exaggerated foreshortening, subject towering overhead` (Perspectiva extrema do chão).
21. **Medium Shot (Waist Up)**: `STRICT MEDIUM SHOT — framed precisely from the waist up, chest and shoulders filling frame` (Enquadramento de cintura para cima).
22. **Close-Up (CU)**: `CLOSE-UP PORTRAIT — head and shoulders framed tightly, soft background bokeh` (Foco no rosto e expressões).
23. **Extreme Close-Up (ECU)**: `EXTREME CLOSE-UP — macro tight shot on subject iris/eyes, razor sharp focus, high detail texture` (Detalhe microscópico).

---

## 💡 Categoria 5: Iluminação Cinematográfica (Cinematic Lighting)

24. **Chiaroscuro / Tenebrism**: `CHIAROSCURO LIGHTING — extreme high contrast, single hard light source, deep shadow engulfing 80% of frame, Caravaggio painterly style`.
25. **Volumetric Lighting / God Rays**: `Volumetric light beams breaking through haze, atmospheric fog, visible light rays`.
26. **Rim Lighting / Edge Light**: `Strong rim lighting separating subject from dark background, bright glowing silhouette outline`.
27. **Golden Hour Warm Glow**: `Golden hour warm sunlight, soft long shadows, warm amber lighting`.
28. **Neon Noir**: `Neon noir aesthetic, vibrant cyan and magenta neon reflections on wet pavement, dark moody shadows`.

---

## 🔍 Categoria 6: Lentes e Profundidade de Campo (Lens & DOF)

29. **Anamorphic Lens Flare**: `Cinematic anamorphic 2.39:1 widescreen lens flare, horizontal blue streaks, oval bokeh`.
30. **Shallow Depth of Field (Bokeh)**: `Shallow depth of field, f/1.4 aperture, creamy blurred background bokeh`.
31. **Macro Lens Detail**: `100mm macro lens shot, extreme sharpness, intricate surface details`.
32. **Fisheye Distortion**: `Fisheye ultra-wide lens, curved spherical edge distortion, exaggerated perspective`.

---

## ⚡ Categoria 7: Transições Focais e Efeitos Especiais

33. **Rack Focus**: `Cinematic rack focus from foreground object blur to background sharp [Subject]`.
34. **Handheld / Shaky Cam**: `Subtle organic handheld camera shake movement`.
35. **Hyperlapse / Time-Lapse**: `Fast hyperlapse camera movement through dark tech studio`.
36. **Bullet Time (Matrix Effect)**: `Frozen time bullet time camera rotation around [Subject]`.

