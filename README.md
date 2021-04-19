# Random Baseball Game Generator

This notebook randomly generates baseball games based on the baserunning speed and slugging average of the players in each lineup.

There are seven possible outcomes per at-bat:
  1. Single
  2. Double
  3. Triple
  4. Home run
  5. Fly out (including sacrifice flies)
  6. Ground out (including double plays)
  7. Strike out

These outcomes are determined using a beta distribution where `beta = 3` and `mean = player's slugging pct / 4`, and then then outcome is multiplied by 4 and rounded so that 0: out, 1: single, 2: double, 3: triple, and 4: home run. Outs are randomly divided into strikeouts, fly outs, and ground outs. 14% of singles are converted into home runs (to adjust for the distribution underpredicting HRs).

Speed is defined as the probability a runner advances to third on a single, scores from second on a single, scores from first on a double, scores on a sacrifice fly, or advances to third on a ground out.

Home field advantage is included by giving the home team a 2% boost to slugging pct and the away team a 2% penalty.

Possible improvements:
  1. Include other kinds of outs (baserunning errors)
  2. Include base stealing (based on speed)
  3. Take into account pitcher attributes
  4. Toggle on/off the print statements to allow for simulation analysis
