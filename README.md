# Fråga 1: Versionshantering vs vanliga filer

## Vad är versionshantering och vad är den stora skillnaden mellan att spara en fil via editorns vanliga sparaknapp och att spara ändringar i Git?

Versionshantering innebär att man sparar och håller koll på olika versioner av sin kod.
Det gör att man kan se vad som har ändrats och när det ändrades och man kan enkelt gå tillbaka till tidigare versioner om något skulle bli fel.

När jag trycker på "Spara" i VS Code sparas bara den senaste versionen av filen lokalt på min dator.
När jag istället gör en commit i Git sparar jag en version av mina ändringar i projektets historik. Då kan jag senare gå tillbaka och se hur koden såg ut vid just det tillfället.

## Förklara vad som menas med att Git sparar en tidslinje av frysta ögonblicksbilder (commits). Vad bevisar det faktum att du när som helst kan klicka på din allra första commit på GitHub och fortfarande se alla tre TODO kvar i koden, trots att filen på din dator ser helt annorlunda ut idag?

Git fungerar som en tidslinje där varje commit man gör är en ögonblicksbild av hur projektet ser ut vid ett visst tillfälle.

Varje gång jag gör en commit så sparas en ny version i historiken, utan att tidigare versioner skrivs över.

Om jag exempelvis skapade tre TODO i min första commit och sedan tog bort dem i senare commits, kan jag fortfarande gå tillbaka till min första commit på GitHub och se alla tre.

Det bevisar att Git bevarar tidigare versioner av koden, även om projektet har förändrats sedan dess.

# Fråga 2: Arbetsytan, Staging och Commits

## Beskriv vad kommandona git status, git add och git commit gör i det dagliga arbetsflödet och när du kör dem.

Dessa tre kommandon använder jag när jag vill spara mina kodändringar i Git.

- "git status" visar vilka filer som har ändrats och om de är redo att committas. Jag använder det för att kontrollera vad som har hänt i projektet.
- "git add" lägger till ändringarna i staging, alltså väljer vilka ändringar som skall ingå i nästa commit.
- "git commit" sparar de stagade ändringarna som en ny version i Gits historik, tillsammans med ett meddelande om vad jag har gjort.

## Förklara arbetsytan, staging och commit samt varför Git säger no changes added to commit.

Man kan jämföra Git med ett skrivbord, ett kuvert och en arkivlåda.

- Arbetsytan (Pappret på skrivbordet): Här arbetar jag med filerna och gör ändringar i koden.
- Staging (Kuvertet): Här lägger jag de ändringar jag vill spara i nästa commit, genom att använda "git add".
- Commit (arkivlådan): Här sparas den färdiga versionen i Gits historik när jag kör "git commit".

Om jag ändrar en fil i VS Code och sedan kör "git commit" direkt utan "git add" så får jag meddelandet "no changes added to commit".
Det beror på att Git bara tar med ändringarna som lagts i staging. Ändringarna finns fortfarande kvar i min arbetsyta, men jag har inte lagt dem i kuvertet ännu.
Jag behöver alltså först köra "git add" och sedan "git commit".

# Fråga 3: Lådan hemma vs Montern på GitHub

## Vad är skillnaden mellan mappen på datorn och repot på GitHub, och vad gör git push?

Mappen på min dator är där jag arbetar med projektet och skriver min kod.
Om projektet använder Git finns även en lokal Git-historik på datorn.

Repot på GitHub är en version av Git-projektet som ligger på internet.
Där kan jag lagra och dela projektet med andra.

När jag kör "git push" skickar Git mina lokala commits till mitt repo på GitHub, så att den aktuella grenen där uppdateras.

## Förklara de två rummen/minnesytorna och varför git push säger Everything up-to-date.

Man kan tänka sig att Git har två olika platser där projektets historik finns.

**Låda hemma (lokala Git):** Här sparas mina commits på min egen dator.
När jag kör "git commit" hamnar den nya versionen här.

**Glasmontern (GitHub):** Här finns projektets historik sparad på internet.
För att uppdatera den behöver jag använda "git push".

Om jag ändrar något i min kod men glömmer att köra "git add" och "git commit" innan jag kör "git push", kan jag få meddelandet: "Everything up-to-date".
Det beror på att "git push" inte skickar mina vanliga filändringar direkt, utan skickar commits.
Eftersom jag inte har skapat någon ny commit finns det ingenting nytt att skicka till GitHub.
Ändringarna finns bara i arbetsytan på min dator.
