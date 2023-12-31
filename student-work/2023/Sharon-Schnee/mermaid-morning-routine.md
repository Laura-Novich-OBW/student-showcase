# Mermaid Morning Routine

```mermaid
   flowchart TD
   A((Alarm rings))-->B{Is it time to get up?};
   B--No-->C[Hit snooze];
   B--Probably-->C[Hit snooze];
   B--Yes-->C[Hit snooze];
   C==>A;
   B==Daughter calling==>D[Get up];
   B==IT'S LATE==>D
   D-->E[Wash up];
   E-->F[Get dressed];
   F-->G[Help get ready and send to school];
   G-->H{How tired am I?};
   H--Very tired-->I[Nap];
   I-->A;
   H--Not so tired-->K{Have some time?};
   K--Yes-->L[Exercise];
   L-->M[Shower];
   M-->N[Get ready for work];
   K--No-->N;
   N-->O[Make coffee];
   O-->P[Get to work]
```
