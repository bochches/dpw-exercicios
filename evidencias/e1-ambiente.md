# E00.1 — Ambiente reprodutível

## Comandos executados e remoção do node modules

PS C:\dev\dpw-exercicios> pnpm add -D prettier
✓ Lockfile passes supply-chain policies (verified 1d ago)
Already up to date
Progress: resolved 1, reused 0, downloaded 0, added 0, done

   ╭───────────────────────────────────────────────╮
   │                                               │
   │     Update available! 11.22.0 → 11.24.0.      │
   │     Changelog: https://pnpm.io/v/11.24.0      │
   │   To update, run: corepack use pnpm@11.24.0   │
   │                                               │
   ╰───────────────────────────────────────────────╯

Done in 2.3s using pnpm v11.22.0
PS C:\dev\dpw-exercicios> New-Item -ItemType Directory -Force evidencias


    Diretório: C:\dev\dpw-exercicios


Mode                 LastWriteTime         Length Name                
----                 -------------         ------ ----                
d-----        25/08/2026     20:13                evidencias          


PS C:\dev\dpw-exercicios> New-Item evidencias\e1-ambiente.md


    Diretório: C:\dev\dpw-exercicios\evidencias


Mode                 LastWriteTime         Length Name                
----                 -------------         ------ ----                
-a----        25/08/2026     20:13              0 e1-ambiente.md      


PS C:\dev\dpw-exercicios> New-Item evidencias\e2-arqueologia.md


    Diretório: C:\dev\dpw-exercicios\evidencias


Mode                 LastWriteTime         Length Name                
----                 -------------         ------ ----                
-a----        25/08/2026     20:13              0 e2-arqueologia.md   


PS C:\dev\dpw-exercicios> New-Item evidencias\e3-conflito.md


    Diretório: C:\dev\dpw-exercicios\evidencias


Mode                 LastWriteTime         Length Name                
----                 -------------         ------ ----                
-a----        25/08/2026     20:14              0 e3-conflito.md      


PS C:\dev\dpw-exercicios> New-Item evidencias\e4-desfazer.md


    Diretório: C:\dev\dpw-exercicios\evidencias


Mode                 LastWriteTime         Length Name                
----                 -------------         ------ ----                
-a----        25/08/2026     20:14              0 e4-desfazer.md      


PS C:\dev\dpw-exercicios> New-Item evidencias\e5-diagnostico.md


    Diretório: C:\dev\dpw-exercicios\evidencias


Mode                 LastWriteTime         Length Name                
----                 -------------         ------ ----                
-a----        25/08/2026     20:14              0 e5-diagnostico.md   


PS C:\dev\dpw-exercicios> pnpm verificar
$ node --version && pnpm --version
v24.16.0
11.22.0
PS C:\dev\dpw-exercicios> git status
On branch main
Your branch is up to date with 'origin/main'.

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        evidencias/

nothing added to commit but untracked files present (use "git add" to track)
PS C:\dev\dpw-exercicios> git add .
PS C:\dev\dpw-exercicios> git status
On branch main
Your branch is up to date with 'origin/main'.

Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        new file:   evidencias/e1-ambiente.md
        new file:   evidencias/e2-arqueologia.md
        new file:   evidencias/e3-conflito.md
        new file:   evidencias/e4-desfazer.md
        new file:   evidencias/e5-diagnostico.md

PS C:\dev\dpw-exercicios> git commit -m "chore: configura ambiente inicial"
[main 43a5a6d] chore: configura ambiente inicial
 5 files changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 evidencias/e1-ambiente.md
 create mode 100644 evidencias/e2-arqueologia.md
 create mode 100644 evidencias/e3-conflito.md
 create mode 100644 evidencias/e4-desfazer.md
 create mode 100644 evidencias/e5-diagnostico.md
PS C:\dev\dpw-exercicios> git log --oneline
43a5a6d (HEAD -> main) chore: configura ambiente inicial
5f14ce9 (origin/main, origin/HEAD, develop) chore: configura ambiente inicial
PS C:\dev\dpw-exercicios> Remove-Item -Recurse -Force node_modules
PS C:\dev\dpw-exercicios> pnpm install --frozen-lockfile
✓ Lockfile passes supply-chain policies (verified 5m ago)
Lockfile is up to date, resolution step is skipped
Packages: +1
+
Packages are hard linked from the content-addressable store to the virtual store.
  Content-addressable store is at: C:\Users\clara\AppData\Local\pnpm\store\v11
  Virtual store is at:             node_modules/.pnpm
Progress: resolved 1, reused 1, downloaded 0, added 1, done

devDependencies:
+ prettier 3.9.6

Done in 926ms using pnpm v11.22.0
PS C:\dev\dpw-exercicios> git status --short

```powershell
Remove-Item -Recurse -Force node_modules

Link do gitignore: https://github.com/WendryClara/dpw-exercicios/blob/43a5a6ddcdb2324608e461489601df9076c179da/.gitignore#L1