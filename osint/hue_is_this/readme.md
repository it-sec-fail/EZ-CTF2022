# Hue is This?
170 points
Solves: 82  Medium
I think you need  to do a -180 turn to find her name and the song.

Flag Format: EZ-CTF{Her_Name_And_The_7th_Song_In_The_Album}

## Solving

Okay a good old osint challenge. I uploaded the image on [yandex.com](https://yandex.com/) and was able to find the correct image. It is an album cover for the goa album `Rock Bitch Mafia` 
from the `The Green Nuns Of The Revolution`. This also give me the second part of the answer *Rock Bitch*, because this is the 7th title on the album.
Okay... now we just need `her` name?

After some further investigations I was able to find [this site](https://www.discogs.com/de/release/3724-The-Green-Nuns-Of-The-Revolution-Rock-Bitch-Mafia).
There are some further informations:

```text
The front cover model is India Waters, the daughter of Roger Waters (from Pink Floyd).

From booklet:
"The fruits of the earth belong to us all, and the earth itself to nobody."
J.J. Ro[u]sseau

℗ & © Flying Rhino Records Ltd 1997

This album is dedicated to Mother Theresa.

Distributed by SRD in the UK.
Distributed by Flying Rhino for the rest of the world.
Mastered @ C.T.S. Studios
```

So this should be her name, right? *India Waters*

The the flag should be:

> EZ-CTF{India_Waters_Rock_Bitch}
