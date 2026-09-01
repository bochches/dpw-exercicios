# E00.2 — Arqueologia de histórico

1. Quantos commits o repositório tem?

COMANDO:
PS C:\Users\clara\nest> git rev-list --count HEAD

SAÍDA:
21659

2. Qual foi o primeiro commit?

COMANDO:
git log --reverse --format="%H %ad %s" --date=short | Select-Object -First 1

SAÍDA:
f7c8d10fb20943bc7102c73d5ecbe49e6c0b5ea1 2017-01-08 Initial commit

3. Quem mais modificou injector.ts?

COMANDO:
git shortlog -sn -- packages/core/injector/injector.ts

SAÍDA:
90  Kamil Myśliwiec

4. O que mudou no último commit?

COMANDO:
git log -1 --format="%H | %ad | %an | %s" --date=iso -- packages/core/injector/injector.ts

SAÍDA:
45485b54210e06a517c1ebf86b42b1ea99fc3fe2

5. Quantos commits nos últimos 90 dias?

COMANDO:
git rev-list --count --since="90 days ago" HEAD

SAÍDA:
693

# Comandos do terminal:

PS C:\Users\clara> git clone --filter=blob:none https://github.com/nestjs/nest.git nest
fatal: destination path 'nest' already exists and is not an empty directory.
PS C:\Users\clara> Get-ChildItem C:\Users\clara\nest


    Diretório: C:\Users\clara\nest


Mode                 LastWriteTime         Length Name                                       
----                 -------------         ------ ----                                       
d-----        25/08/2026     20:30                .circleci                                  
d-----        25/08/2026     20:30                .github                                    
d-----        25/08/2026     20:30                .husky                                     
d-----        25/08/2026     20:30                integration                                
d-----        25/08/2026     20:30                packages                                   
d-----        25/08/2026     20:30                sample                                     
d-----        25/08/2026     20:30                scripts                                    
d-----        25/08/2026     20:30                tools                                      
-a----        25/08/2026     20:30            788 .commitlintrc.json                         
-a----        25/08/2026     20:30             80 .gitattributes                             
-a----        25/08/2026     20:30            724 .gitignore                                 
-a----        25/08/2026     20:30            157 .npmignore                                 
-a----        25/08/2026     20:30            488 .oxlintrc.json                             
-a----        25/08/2026     20:30             72 .prettierignore                            
-a----        25/08/2026     20:30             83 .prettierrc                                
-a----        25/08/2026     20:30           3426 CODE_OF_CONDUCT.md                         
-a----        25/08/2026     20:30          14107 CONTRIBUTING.md                            
-a----        25/08/2026     20:30            400 gulpfile.mjs                               
-a----        25/08/2026     20:30            138 lerna.json                                 
-a----        25/08/2026     20:30           1137 LICENSE                                    
-a----        25/08/2026     20:30         832581 package-lock.json                          
-a----        25/08/2026     20:30           6645 package.json                               
-a----        25/08/2026     20:30          11012 Readme.md                                  
-a----        25/08/2026     20:30           6687 readme_jp.md                               
-a----        25/08/2026     20:30           6463 readme_kr.md                               
-a----        25/08/2026     20:30           4918 readme_zh.md                               
-a----        25/08/2026     20:30            202 renovate.json                              
-a----        25/08/2026     20:30            109 SECURITY.md                                
-a----        25/08/2026     20:30           1840 tsconfig.json                              
-a----        25/08/2026     20:30            271 tsconfig.spec.json                         
-a----        25/08/2026     20:30           3393 vitest.config.coverage.mts                 
-a----        25/08/2026     20:30           2392 vitest.config.integration.mts              
-a----        25/08/2026     20:30           2193 vitest.config.mts                          


PS C:\Users\clara> Set-Location C:\Users\clara\nest
PS C:\Users\clara\nest> git status
On branch master
Your branch is up to date with 'origin/master'.

nothing to commit, working tree clean
