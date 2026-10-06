# rotax-rules

Fisierele de reguli fiscale **semnate** pe care aplicatia RO-TAX le preia automat (cel mult o data pe zi, in fundal).

| Fisier | Ce este |
|---|---|
| `rules_<an>.json` | Regulile fiscale ale anului (surse, cote, praguri) |
| `rules_<an>.json.sig` | Semnatura Ed25519 (64 de octeti, binar) a fisierului de mai sus |

- Aplicatia verifica semnatura cu o cheie publica inclusa in cod; un fisier fara semnatura valida, alterat sau mai vechi decat regulile active este **respins**, iar aplicatia ramane pe regulile pe care le avea.
- **Nu edita fisierele de mana pe GitHub** si nu schimba terminatiile de linie: orice octet modificat invalideaza semnatura (`.gitattributes` opreste conversia automata). Fisierele se semneaza local si se incarca neschimbate.
- Fiecare publicare trebuie sa creasca `last_verified` din `rules_<an>.json`.
- Calcule estimative, nu consultanta fiscala.
