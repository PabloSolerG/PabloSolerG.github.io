---
layout: page
title: Soccer Analytics
description: Data-Driven Insights into Team Tactics 
related_posts: false
img: assets/img/SoccerAnalytics/AreaCoverage_compressed.gif
importance: 3
category: ETH Zürich
related_publications: false
---

This page presents a detailed soccer analytics study focusing on England's offensive and defensive strategies during their Euro 2024 qualifying matches. Using datasets from Wyscout and StatsBomb, the analysis is designed to help teams strategize against England in the 2024 European Championship. The study leverages data-driven methods to provide actionable insights on England's tactics in attack and defense, including team-level and player-level analyses.

The report exclusively examines England's eight qualifying matches, detailing formations, passing patterns, and critical phases of play. Key aspects covered include:
<div style="display: flex; align-items: center; justify-content: center; gap: 20px;">
  <div style="flex: 1; max-width: 100%;">
    <ul>
      <li>Offensive Patterns: Analysis of England's attacking build-up, use of the wings, and reliance on specific players like Harry Kane and Bukayo Saka for goals.</li>
      <li>Defensive Organization: Examination of England's defensive pressing, positioning, and transition dynamics to identify vulnerabilities.</li>
      <li>Set Pieces and Counterattacks: Evaluation of England's proficiency in set pieces and susceptibility to counterattacks, providing a tactical focus for opposing teams.</li>
    </ul>
  </div>
</div>


This page serves as a tactical guide, highlighting England's strengths and weaknesses with visualizations such as pass maps, heatmaps, and event transition probabilities. The findings aim to support teams in crafting effective game plans to counter England's dominance on the field.

---


### Team Level Analyses

#### Passes

We have represented some pass maps of England during the available matches. The positions are represented according to a standard map of the corresponding formation. The width of the lines indicates the amount of passes between the corresponding player positions, and the size of the nodes refers to the accuracy of the footballer.

#### Playing through the middle

<div style="display: flex; justify-content: space-evenly; align-items: center;">
  <img src="/assets/img/SoccerAnalytics/Pass_Eng_IT.png" alt="IT_ENG_Grass" style="width: 45%;">
  <img src="/assets/img/SoccerAnalytics/Pass_Eng_Mac.png" alt="MK_ENG_Grass" style="width: 45%;">
</div>


#### Playing through the wings

<div style="display: flex; justify-content: space-evenly; align-items: center;">
  <img src="/assets/img/SoccerAnalytics/Pass_Eng_Mal.png" alt="MA_ENG_Grass" style="width: 45%;">
  <img src="/assets/img/SoccerAnalytics/Pass_Eng_Ukr.png" alt="ENG_UA_Grass" style="width: 45%;">
</div>

Key insights from these graphs:
- England strongly relies on playing through the wings.
- Opposing teams often achieve good results by isolating the Centre Forward/Striker from their teammates, exploiting their relatively low pass accuracy.
- England's Centre Midfielder tends to avoid risky passes, often passing back to the defenders or to the wings.
- Defenders play a crucial role in moving the ball horizontally across the pitch.

#### Match Analysis: England vs. North Macedonia

<div style="display: flex; justify-content: space-evenly; align-items: center;">
  <img src="/assets/img/SoccerAnalytics/Total_passes_1.png" alt="1stMatchGrass" style="width: 45%;">
  <img src="/assets/img/SoccerAnalytics/Total_passes_2.png" alt="2ndMatchGrass" style="width: 45%;">
</div>

England played more conservatively in the second match, keeping passes closer to their own goal and limiting their attacking chances. This tactical shift was likely due to their secure qualification for the tournament.

#### Pass-Flow Analysis

The pass-flow analysis highlights England's symmetry in play build-up. Compared to other teams, they complete plays faster and favor deep runs on the right flank. Defensively, they channel most passes through the middle while slightly favoring the right midfielders.


<div style="display: flex; justify-content: space-evenly; align-items: center;">
  <img src="/assets/img/SoccerAnalytics/england_pass_flow.gif" alt="england_pass_flow" style="width: 45%;">
  <img src="/assets/img/SoccerAnalytics/allteams_pass_flow.gif" alt="allteams_pass_flow.gif" style="width: 45%;">
</div>

Credit to Charles William (opengoalapp) for the codebase, with adaptations for Wyscout data.

---
### Formation Timeline

England predominantly utilized a 4-3-3 formation during the qualifiers, with occasional shifts to a 4-2-3-1, particularly in later matches. The timeline below shows the variation in formations across the games, reflecting tactical adjustments to different opponents and game contexts.

<div style="text-align: center;">
  <img src="/assets/img/SoccerAnalytics/Formation_Timeline.png" alt="Formation Timeline" style="width: 80%;">
</div>

---

### Goals

England scored a total of 22 goals during their Euro 2024 qualifying campaign, including three own goals by opponents. Harry Kane and Bukayo Saka stood out as the main contributors, with significant involvement in the attacking phases. The distribution of goal types and scorers is represented below using a Sankey diagram.

<div style="text-align: center;">
  <img src="/assets/img/SoccerAnalytics/Eng_goals.png" alt="England Goals Sankey" style="width: 80%;">
</div>


---

### Structural Defensive Analysis

England's defensive strategies are assessed using three key metrics: area coverage, man-to-man marking rates, and passing lane coverage. These metrics are computed based on the opponent's possession of the ball and reveal the robustness of England's defensive structure.

- **Man-to-Man Marking Rates**: This metric quantifies the frequency of defensive players staying within a 4-meter radius of opposing attackers, ensuring tight marking without overlap. England consistently demonstrated high man-to-man marking rates, indicative of their focus on individual defensive assignments.
- **Passing Lane Coverage**: Imaginary lines are drawn between the ball and each attacking player not in possession, and the presence of defenders within 2 meters of these lines determines England’s effectiveness in intercepting passes. Their high coverage rates highlight their ability to disrupt attacking plays.
- **Area Coverage**: England's compactness and spread across the pitch are analyzed through metrics such as width, height, and area coverage. These reveal their ability to occupy more of the field compared to opponents, further bolstering their defensive tenacity.

The following animations illustrate these defensive aspects during the England vs. Italy match:

<div style="display: flex; justify-content: space-around; align-items: center; gap: 20px; flex-wrap: wrap;">
  <div style="text-align: center;">
    <iframe src="https://giphy.com/embed/BENx0AdNta0wUddlEx" width="300" height="300" style="border: none;" frameborder="0" allowfullscreen></iframe>
    <p><strong>Measure of Area Coverage</strong></p>
  </div>
  <div style="text-align: center;">
    <iframe src="https://giphy.com/embed/t83ADEC2icCt6Fvhsa" width="300" height="300" style="border: none;" frameborder="0" allowfullscreen></iframe>
    <p><strong>Measure of Man-to-Man Marking Rates</strong></p>
  </div>
  <div style="text-align: center;">
    <iframe src="https://giphy.com/embed/dp5ZJlcqJ7aOgMGgnN" width="300" height="300" style="border: none;" frameborder="0" allowfullscreen></iframe>
    <p><strong>Measure of Passing Lanes Coverage Rates</strong></p>
  </div>
</div>

England's defensive superiority is further highlighted by their consistent metrics across various matches. Their defensive approach leans more toward man-to-man marking than intercepting passing lanes, a strategic focus that has contributed to their impressive record of conceding only two goals in four matches. These insights provide valuable guidance for tailoring counter-strategies against England's defense.

<div style="text-align: center; margin-top: 20px;">
  <img src="/assets/img/SoccerAnalytics/defensive_stats.png" alt="Defensive Metrics Comparison" style="width: 80%;">
  <p><strong>Defensive Metrics Comparison: England vs. Opponents</strong></p>
</div>
---

### Player Attributes Analysis

Using data from Wyscout covering all eight qualifying matches, we have analyzed multiple player attributes to highlight their strengths and weaknesses. Our analysis includes straightforward metrics such as successful passes and headers won, as well as more complex measures like xGBuildUp. xGBuildUp evaluates a player's involvement in possession chains that lead to dangerous plays. All statistics are normalized to a per-90-minute basis to ensure comparability.

#### Attackers' Attributes

The radar charts for attackers illustrate the diversity in player roles, color-coded into finishers, passers, dribblers, and assisters. While Harry Kane excels at scoring, Jack Grealish outperforms others in creating opportunities, leading in assists. This insight suggests that blocking passing lanes when Grealish is in possession should be a priority. Additionally, Grealish, Saka, and Rashford (not in the official team for the Euros) show significant involvement in dangerous plays, as indicated by their high xGBuildUp values. Jude Bellingham also deserves attention for his exceptional ball recovery and aerial dominance, surpassing even Harry Kane.

<div style="text-align: center;">
  <img src="/assets/img/SoccerAnalytics/player_stats.png" alt="Attackers' Attributes" style="width: 80%;">
  <p><strong>Attackers' Attributes</strong></p>
</div>

#### Midfielders' Attributes

England's core midfield — Alexander-Arnold, Rice, and Phillips — leans toward the defensive side but plays crucial roles in initiating attacks, as reflected by their high xGBuildUp scores. Alexander-Arnold, in particular, excels at dribbling and generating assists, marking him as a player to watch closely. Phillips stands out in defensive metrics, excelling in aerial duels and ball recovery, highlighting his importance in midfield stability.

<div style="text-align: center;">
  <img src="/assets/img/SoccerAnalytics/midfield_player_stats.png" alt="Midfielders' Attributes" style="width: 80%;">
  <p><strong>Midfielders' Attributes</strong></p>
</div>

#### Defenders' Attributes

Our analysis of defenders reveals key insights into England’s starting eleven. Harry Maguire dominates in aerial duels, while Luke Shaw excels at ball recovery. Subtle details emerge, such as center-backs exhibiting higher xGBuildUp scores than full-backs, underscoring their role in initiating dangerous plays. Interestingly, their xGBuildUp values surpass those of some midfielders and forwards. This suggests a need for defensive strategies that restrict the playmaking abilities of center-backs. Additionally, Luke Shaw’s direct assist contributions, which are four times higher than Kyle Walker's, highlight his offensive capabilities.

<div style="text-align: center;">
  <img src="/assets/img/SoccerAnalytics/defensive_player_stats.png" alt="Defenders' Attributes" style="width: 65%;">
  <p><strong>Defenders' Attributes</strong></p>
</div>

