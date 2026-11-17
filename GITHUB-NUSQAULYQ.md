# GitHub арқылы Windows EXE жасау

Бұл жинақ бастапқы шифрлау қолданбасын сақтап, GitHub Actions арқылы **екі Windows EXE** жасайды:

- **Орнатылатын EXE** — компьютерге орнату және жұмыс үстеліне таңбаша қосу үшін.
- **Portable EXE** — орнатусыз бірден ашу үшін.

## Жасау тәртібі

1. GitHub.com сайтына кіріп, **New repository** басыңыз.
2. Репозиторийге `Wheatstone-Gronsfeld` атауын беріп, **Create repository** басыңыз.
3. **uploading an existing file** (немесе **Add file → Upload files**) таңдаңыз.
4. Осы ZIP ішіндегі `Wheatstone-Gronsfeld` бумасының **ішіндегісін** репозиторийдің түбіріне жүктеңіз. `.github/workflows/windows-exe.yml` файлы міндетті түрде сақталуы керек. GitHub веб-интерфейсі жасырын `.github` бумасын жүктемесе, **Add file → Create new file** арқылы `.github/workflows/windows-exe.yml` атауымен ZIP-тегі файлдың мәтінін салыңыз.
5. **Commit changes** басыңыз.
6. **Actions → Build Windows EXE → Run workflow → Run workflow** таңдаңыз (немесе `main` тармағына алғашқы push-тен кейін автоматты іске қосылады).
7. Жасыл ✓ белгісін күтіңіз. Жасалған workflow бетін төмен сырғытып, **Artifacts → Wheatstone-Gronsfeld-Windows-EXE** басыңыз.
8. Жүктелген ZIP ішіндегі екі `.exe` файлының қалағанын қолданыңыз.

**Ескерту:** `.exe` файлын осы архивте алдын ала жинаған жоқпыз. Оны GitHub-тың Windows компьютері жинайды. Электрондық қолтаңба болмағандықтан Windows SmartScreen ескертуі шығуы мүмкін. Тек өзіңіз жасаған файлды іске қосыңыз. GitHub Actions тегін лимиттері/қолжетімділігі аккаунтқа байланысты.

## Қосымша

Компьютерде Node.js орнатылған болса, жоба бумасында `npm install`, одан соң `npm start` арқылы локалды тексеруге болады. Windows-та `npm run dist:win` арқылы жинауға болады.

Бұрынғы `Open.cmd` / `Install.cmd` файлдары сақталды, бірақ дайын EXE қолдану үшін қажет емес.
