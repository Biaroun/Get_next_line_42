<div align="center">
  <img src="https://upload.wikimedia.org/wikipedia/commons/8/8d/42_Logo.svg" alt="42 logo" width="120"/>
  <h1>get_next_line</h1>
  <p>Projet 42 : lecture d’un fichier <strong>ligne par ligne</strong> en C</p>

  <p>
    <img src="https://img.shields.io/badge/Language-C-00599C?logo=c&logoColor=white" alt="C"/>
    <img src="https://img.shields.io/badge/Build-Makefile-427819?logo=gnu&logoColor=white" alt="Makefile"/>
    <img src="https://img.shields.io/badge/School-42-black?logo=42&logoColor=white" alt="42"/>
    <img src="https://img.shields.io/badge/Norminette-friendly-success" alt="Norminette"/>
  </p>
</div>

---

## 📚 Description

`get_next_line` est une fonction qui lit, à chaque appel, la prochaine ligne disponible depuis un descripteur de fichier (`fd`).

Ce dépôt contient :

- une version **mandatory** de `get_next_line`
- une version **bonus** (gestion de plusieurs descripteurs de fichier)
- les fonctions utilitaires associées

---

## 🗂️ Structure

- `get_next_line.h` : header de la version mandatory (prototype + `BUFFER_SIZE`)
- `get_next_line.c` : logique principale de lecture
- `get_next_line_utils.c` : fonctions utilitaires
- `get_next_line_bonus.h` : header de la version bonus
- `get_next_line_bonus.c` : version bonus (multi-fd)
- `get_next_line_utils_bonus.c` : utilitaires bonus

---

## ⚙️ Compilation

### Version mandatory

```bash
cc -Wall -Wextra -Werror -D BUFFER_SIZE=42 \
  get_next_line.c get_next_line_utils.c main.c -o gnl
```

### Version bonus

```bash
cc -Wall -Wextra -Werror -D BUFFER_SIZE=42 \
  get_next_line_bonus.c get_next_line_utils_bonus.c main.c -o gnl_bonus
```

> `main.c` est un fichier de test (non fourni ici) à adapter selon tes besoins.

---

## 🚀 Utilisation

Inclure le header correspondant :

```c
#include "get_next_line.h"
// ou
#include "get_next_line_bonus.h"
```

Exemple minimal :

```c
int		fd;
char	*line;

fd = open("test.txt", O_RDONLY);
while ((line = get_next_line(fd)) != NULL)
{
    printf("%s", line);
    free(line);
}
close(fd);
```

---

## 🧠 Prototype

```c
char *get_next_line(int fd);
```

- Retourne une ligne lue depuis `fd` (incluant `\n` si présent)
- Retourne `NULL` à la fin du fichier ou en cas d’erreur
- Fonctionne avec la macro `BUFFER_SIZE` définie à la compilation

---

## ✅ Norme & qualité

- Code C compilé avec : `-Wall -Wextra -Werror`
- Respect de la Norme 42
- Pas de fuite mémoire attendue sur un usage correct

---

## 👤 Auteur

- `biaroun` — 42

---

## 📄 Licence

Projet académique 42.
Usage pédagogique et personnel.
