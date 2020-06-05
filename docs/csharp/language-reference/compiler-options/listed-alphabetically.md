---
title: Opzioni del compilatore C# in ordine alfabetico
ms.date: 06/04/2020
helpviewer_keywords:
- compiler options [C#], listed alphabetically
- C# language, compiler options listed alphabetically
- Visual C# compiler, options listed alphabetically
- Visual C#, compiler options listed alphabetically
ms.assetid: 43535ea0-ca47-4a15-b528-615087a86092
ms.openlocfilehash: 9765d13191f862a2e92bb00aa66a92c3a64ac303
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/05/2020
ms.locfileid: "84446939"
---
# <a name="c-compiler-options-listed-alphabetically"></a>Opzioni del compilatore C# in ordine alfabetico

Le seguenti opzioni del compilatore sono ordinate alfabeticamente. Per un elenco organizzato per categorie, vedere [Opzioni del compilatore C# elencate per categoria](listed-by-category.md).

|Opzione|Scopo|
|------------|-------------|
|[@](response-file-compiler-option.md)|Legge un file di risposta per altre opzioni|
|[-?](help-compiler-option.md)|Visualizza un messaggio relativo all'utilizzo in stdout.|
|-additionalfile|Assegna un nome ad altri file che non influiscono direttamente sulla generazione del codice, ma possono essere usati dagli analizzatori per produrre errori o avvisi.|
|[-addmodule](addmodule-compiler-option.md)|Collega i moduli specificati nell'assembly|
|-analyzer|Esegue gli analizzatori da questo assembly (forma breve: -a)|
|[-appconfig](appconfig-compiler-option.md)|Specifica il percorso del file app.config in fase di associazione di assembly.|
|[-baseaddress](baseaddress-compiler-option.md)|Specifica l'indirizzo di base della libreria da compilare.|
|[-bugreport](bugreport-compiler-option.md)|Crea un file di report sui bug. Questo file verrà inviato con le informazioni sull'arresto anomalo se viene usato con -errorreport:prompt o -errorreport:send.|
|[-selezionato](checked-compiler-option.md)|Fa generare al compilatore i controlli dell'overflow.|
|-checksumalgorithm:\<alg>|Specifica l'algoritmo per il calcolo del checksum del file di origine archiviato nel file PDB.  I valori supportati sono: SHA256 (impostazione predefinita) o SHA1.<br>A causa di problemi di conflitto con SHA1, Microsoft consiglia SHA256. |
|[-codepage](codepage-compiler-option.md)|Specifica la tabella di codici da utilizzare per l'apertura dei file di origine.|
|[-debug](debug-compiler-option.md)|Crea informazioni di debug.|
|[-define](define-compiler-option.md)|Definisce i simboli di compilazione condizionale.|
|[-delaysign](delaysign-compiler-option.md)|Ritarda la firma dell'assembly usando solo la parte pubblica della chiave con nome sicuro.|
|[-deterministic](deterministic-compiler-option.md)|Fa sì che l'output del compilatore sia un assembly il cui contenuto binario è identico in tutte le compilazioni se gli input sono identici.|
|[-doc](doc-compiler-option.md)|Specifica un file XML della documentazione da generare.|
|-embed|Incorporare tutti i file di origine nel file PDB.|
|incorporare\<file list>|Incorporare file specifici nel file PDB.|
|-errorendlocation|Riga e colonna di output della posizione finale di ogni errore.|
|ErrorLog\<file>|Specificare un file per registrare tutti i dati di diagnostica del compilatore e dell'analizzatore.|
|[-errorreport](errorreport-compiler-option.md)|Specifica come gestire gli errori interni del compilatore: prompt, send o none. Il valore predefinito è none.|
|[-filealign](filealign-compiler-option.md)|Specifica l'allineamento usato per le sezioni del file di output.|
|[-fullpaths](fullpaths-compiler-option.md)|Fa generare al compilatore percorsi completi.|
|[-Guida](help-compiler-option.md)|Visualizza un messaggio relativo all'utilizzo in stdout.|
|[-highentropyva](highentropyva-compiler-option.md)|Specifica che è supportata la funzionalità ASLR a entropia elevata.|
|-incremental|Abilita la compilazione incrementale [obsoleto]|
|[-keycontainer](keycontainer-compiler-option.md)|Specifica un contenitore di chiavi con nome sicuro.|
|[-filefile](keyfile-compiler-option.md)|Specifica un file di chiave con nome sicuro.|
|[langversion\<string>](langversion-compiler-option.md)|Specifica la versione del linguaggio: Default, ISO-1, ISO-2, 3, 4, 5, 6, 7, 7.1, 7.2, 7.3 o Latest |
|[-lib](lib-compiler-option.md)|Specifica directory aggiuntive in cui cercare i riferimenti.|
|[-collegamento](link-compiler-option.md)|Rende disponibili per il progetto le informazioni sui tipi COM negli assembly specificati.|
|[-linkresource](linkresource-compiler-option.md)|Collega la risorsa specificata all'assembly.|
|[-main](main-compiler-option.md)|Specifica il tipo che contiene il punto di ingresso, ignorando tutti gli altri punti di ingresso possibili.|
|[-moduleassemblyname](moduleassemblyname-compiler-option.md)|Specifica l'assembly i cui tipi non pubblici sono accessibili da un file con estensione NETMODULE.|
|moduleName\<string>|Specificare il nome del modulo di origine|
|[-noconfig](noconfig-compiler-option.md)|Indica al compilatore di non includere automaticamente il file CSC.RSP.|
|[-nologo](nologo-compiler-option.md)|Impedisce la visualizzazione del messaggio di copyright del compilatore.|
|[-nostdlib](nostdlib-compiler-option.md)|Indica al compilatore non di non fare riferimento alla libreria standard (mscorlib.dll).|
|[-nowarn](nowarn-compiler-option.md)|Disabilita messaggi di avviso specifici|
|[-nowin32manifest](nowin32manifest-compiler-option.md)|Indica il compilatore di non incorporare un manifesto dell'applicazione nel file eseguibile.|
|[-Nullable](nullable-compiler-option.md)|Specifica l'opzione di contesto Nullable.|
|[-Ottimizza](optimize-compiler-option.md)|Abilita/disabilita le ottimizzazioni.|
|[-out](out-compiler-option.md)|Specifica il nome del file di output (impostazione predefinita: nome base del file con la classe principale o il primo file).|
|-parallel[+&#124;-]|Specifica se usare la compilazione simultanea (+).|
|[-pathmap](pathmap-compiler-option.md)|Specifica un mapping per i nomi di percorsi di origine restituiti dal compilatore.|
|[-pdb](pdb-compiler-option.md)|Specifica il nome file e il percorso del file pdb.|
|[-piattaforma](platform-compiler-option.md)|Limita le piattaforme in cui è possibile eseguire il codice: x86, Itanium, x64, anycpu o anycpu32bitpreferred. Il valore predefinito è anycpu.|
|[-preferreduilang](preferreduilang-compiler-option.md)|Specifica la lingua da utilizzare per l'output del compilatore.|
|[-publicsign](publicsign-compiler-option.md)|Applica una chiave pubblica senza firmare l'assembly, ma imposta il bit nell'assembly che indica che l'assembly è firmato.|
|[-recurse](recurse-compiler-option.md)|Include tutti i file presenti nella directory corrente e nelle relative sottodirectory in base alle specifiche dei caratteri jolly.|
|[-riferimento](reference-compiler-option.md)|Fa riferimento ai metadati dei file di assembly specificati.|
|[-refout](refout-compiler-option.md)|Generare un assembly di riferimento oltre all'assembly principale.|
|[-refonly](refonly-compiler-option.md)|Generare un assembly di riferimento invece dell'assembly principale.|
|-reportanalyzer|Restituire informazioni aggiuntive dell'analizzatore, ad esempio il tempo di esecuzione.|
|[-risorsa](resource-compiler-option.md)|Incorpora la risorsa specificata.|
|RuleSet\<file>|Specificare un file di set di regole che disabilita la diagnostica specifica.|
|[-subsystemversion](subsystemversion-compiler-option.md)|Specifica la versione minima del sottosistema che può essere utilizzata dal file eseguibile.|
|[-destinazione](target-compiler-option.md)|Specifica il formato del file di output tramite una delle quattro opzioni seguenti: [-target: appcontainerexe](target-appcontainerexe-compiler-option.md), [-target: exe](target-exe-compiler-option.md), [-target: Library](target-library-compiler-option.md), [-target: module](target-module-compiler-option.md), [-target: winexe](target-winexe-compiler-option.md), [-target: winmdobj](target-winmdobj-compiler-option.md).|
|[-unsafe](unsafe-compiler-option.md)|Consente codice [unsafe](../keywords/unsafe.md).|
|[-utf8output](utf8output-compiler-option.md)|Restituisce i messaggi del compilatore usando la codifica UTF-8.|
|-version|Visualizza il numero di versione del compilatore ed esce.|
|[-warn](warn-compiler-option.md)|Imposta il livello degli avvisi (0-4).|
|[-warnaserror](warnaserror-compiler-option.md)|Segnala determinati avvisi come errori.|
|[-win32icon](win32icon-compiler-option.md)|Usa questa icona per l'output.|
|[-win32manifest](win32manifest-compiler-option.md)|Specifica un file manifesto win32 personalizzato.|
|[-win32res](win32res-compiler-option.md)|Specifica il file di risorse win32 (res).|

## <a name="see-also"></a>Vedere anche

- [Opzioni del compilatore C#](index.md)
- [Opzioni del compilatore C# elencate per categoria](listed-by-category.md)
- [Come impostare le variabili di ambiente per la riga di comando di Visual Studio](how-to-set-environment-variables-for-the-visual-studio-command-line.md)
- [\<compiler>Elemento](../../../framework/configure-apps/file-schema/compiler/compiler-element.md)
