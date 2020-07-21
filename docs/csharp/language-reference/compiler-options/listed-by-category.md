---
title: Opzioni del compilatore C# elencate per categoria
ms.date: 06/04/2020
helpviewer_keywords:
- Visual C# compiler, options listed by category
- compiler options [C#], listed by category
- Visual C#, compiler options listed by category
ms.assetid: 96437ecc-6502-4cd3-b070-e9386a298e83
ms.openlocfilehash: f216534140b6e207ac110bb54b3e4f93a8ac6b70
ms.sourcegitcommit: cf5a800a33de64d0aad6d115ffcc935f32375164
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/20/2020
ms.locfileid: "86474020"
---
# <a name="c-compiler-options-listed-by-category"></a>Opzioni del compilatore C# elencate per categoria

Le seguenti opzioni del compilatore sono ordinate per categoria. Per un elenco alfabetico, vedere [Opzioni del compilatore C# in ordine alfabetico](listed-alphabetically.md).

## <a name="optimization"></a>Optimization

|Opzione|Scopo|
|------------|-------------|
|[-filealign](filealign-compiler-option.md)|Specifica le dimensioni delle sezioni nel file di output.|
|[-Ottimizza](optimize-compiler-option.md)|Abilita/disabilita le ottimizzazioni.|

## <a name="output-files"></a>File di output

|Opzione|Scopo|
|------------|-------------|
|[-deterministico](deterministic-compiler-option.md)|Fa sì che l'output del compilatore sia un assembly il cui contenuto binario è identico in tutte le compilazioni se gli input sono identici.|
|[-doc](doc-compiler-option.md)|Specifica un file XML in cui vengono scritti i commenti sulla documentazione elaborati.|
|[-out](out-compiler-option.md)|Specifica il file di output.|
|[-pathmap](pathmap-compiler-option.md)|Specifica un mapping per i nomi di percorsi di origine restituiti dal compilatore|
|[-pdb](pdb-compiler-option.md)|Specifica il nome file e il percorso del file pdb.|
|[-piattaforma](platform-compiler-option.md)|Specificare la piattaforma di output.|
|[-preferreduilang](preferreduilang-compiler-option.md)|Specificare una lingua per l'output del compilatore.|
|[-refout](refout-compiler-option.md)|Generare un assembly di riferimento oltre all'assembly principale.|
|[-refonly](refonly-compiler-option.md)|Generare un assembly di riferimento invece dell'assembly principale.|
|[-destinazione](target-compiler-option.md)|Specifica il formato del file di output usando una delle opzioni seguenti: [-target: appcontainerexe](target-appcontainerexe-compiler-option.md), [-target: exe](target-exe-compiler-option.md), [-target: Library](target-library-compiler-option.md), [-target: module](target-module-compiler-option.md), [-target: winexe](target-winexe-compiler-option.md)o [-target: winmdobj](target-winmdobj-compiler-option.md).|
|moduleName\<string>|Specificare il nome del modulo di origine|

## <a name="net-framework-assemblies"></a>Assembly .NET Framework

|Opzione|Scopo|
|------------|-------------|
|[-addmodule](addmodule-compiler-option.md)|Specifica uno o più moduli che devono fare parte di questo assembly.|
|[-delaysign](delaysign-compiler-option.md)|Indica al compilatore di aggiungere la chiave pubblica e di lasciare l'assembly non firmato.|
|[-keycontainer](keycontainer-compiler-option.md)|Specifica il nome del contenitore di chiavi crittografiche.|
|[-filefile](keyfile-compiler-option.md)|Specifica il nome file contenente la chiave crittografica.|
|[-lib](lib-compiler-option.md)|Specifica la posizione degli assembly a cui si fa riferimento tramite [-reference](reference-compiler-option.md).|
|[-nostdlib](nostdlib-compiler-option.md)|Indica al compilatore non di non fare importare la libreria standard (mscorlib.dll).|
|[-publicsign](publicsign-compiler-option.md)|Applica una chiave pubblica senza firmare l'assembly, ma imposta il bit nell'assembly che indica che l'assembly è firmato.|
|[-riferimento](reference-compiler-option.md)|Importa i metadati da un file contenente un assembly.|
|-analyzer|Esegue gli analizzatori da questo assembly (forma breve: /a)|
|-additionalfile|Assegna un nome ad altri file che non influiscono direttamente sulla generazione del codice, ma possono essere usati dagli analizzatori per produrre errori o avvisi.|
|-embed|Incorporare tutti i file di origine nel file PDB.|
|incorporare\<file list>|Incorporare file specifici nel file PDB.|

## <a name="debuggingerror-checking"></a>Debug/Controllo errori

|Opzione|Scopo|
|------------|-------------|
|[-bugreport](bugreport-compiler-option.md)|Crea un file contenente informazioni che rendono più semplice segnalare un bug.|
|[-selezionato](checked-compiler-option.md)|Specifica se il calcolo di interi che supera i limiti del tipo di dati genererà un'eccezione in fase di esecuzione.|
|[-debug](debug-compiler-option.md)|Indica al compilatore di generare informazioni di debug.|
|[-errorreport](errorreport-compiler-option.md)|Imposta il comportamento relativo alla segnalazione degli errori.|
|[-fullpaths](fullpaths-compiler-option.md)|Specifica il percorso assoluto del file nell'output del compilatore.|
|[-nowarn](nowarn-compiler-option.md)|Elimina la generazione degli avvisi specificati da parte del compilatore.|
|[-Nullable](nullable-compiler-option.md)|Specifica l'opzione di contesto Nullable.|
|[-warn](warn-compiler-option.md)|Imposta il livello degli avvisi.|
|[-warnaserror](warnaserror-compiler-option.md)|Alza il livello degli avvisi a errori.|
|RuleSet\<file>|Specificare un file di set di regole che disabilita la diagnostica specifica.|

## <a name="preprocessor"></a>Preprocessore

|Opzione|Scopo|
|------------|-------------|
|[-define](define-compiler-option.md)|Definisce i simboli del preprocessore.|

## <a name="resources"></a>Risorse

|Opzione|Scopo|
|------------|-------------|
|[-collegamento](link-compiler-option.md)|Rende disponibili per il progetto le informazioni sui tipi COM negli assembly specificati.|
|[-linkresource](linkresource-compiler-option.md)|Crea un collegamento a una risorsa gestita.|
|[-risorsa](resource-compiler-option.md)|Incorpora una risorsa di .NET Framework nel file di output.|
|[-win32icon](win32icon-compiler-option.md)|Specifica un file ico da inserire nel file di output.|
|[-win32res](win32res-compiler-option.md)|Specifica una risorsa Win32 da inserire nel file di output.|

## <a name="miscellaneous"></a>Varie

|Opzione|Scopo|
|------------|-------------|
|[@](response-file-compiler-option.md)|Specifica un file di risposta.|
|[-?](help-compiler-option.md)|Elenca le opzioni del compilatore in stdout.|
|[-baseaddress](baseaddress-compiler-option.md)|Specifica l'indirizzo di base preferenziale in cui caricare una DLL.|
|[-tabella codici](codepage-compiler-option.md)|Specifica la tabella codici da usare per tutti i file del codice sorgente nella compilazione.|
|[-Guida](help-compiler-option.md)|Elenca le opzioni del compilatore in stdout.|
|[-highentropyva](highentropyva-compiler-option.md)|Specifica che il file eseguibile supporta ASLR (Address Space Layout Randomization).|
|[-langversion](langversion-compiler-option.md)|Specifica la versione del linguaggio: Default, ISO-1, ISO-2, 3, 4, 5, 6, 7, 7.1, 7.2, 7.3 o Latest |
|[-main](main-compiler-option.md)|Specifica il percorso del metodo **Main**.|
|[-noconfig](noconfig-compiler-option.md)|Indica al compilatore di non eseguire la compilazione con csc.rsp.|
|[-nologo](nologo-compiler-option.md)|Elimina i messaggi informativi del compilatore.|
|[-recurse](recurse-compiler-option.md)|Cerca nelle sottodirectory i file di origine da compilare.|
|[-subsystemversion](subsystemversion-compiler-option.md)|Specifica la versione minima del sottosistema che può essere utilizzata dal file eseguibile.|
|[-unsafe](unsafe-compiler-option.md)|Abilita la compilazione del codice che usa la parola chiave [unsafe](../keywords/unsafe.md).|
|[-utf8output](utf8output-compiler-option.md)|Visualizza l'output del compilatore usando la codifica UTF-8.|
|-parallel[+&#124;-]|Specifica se usare la compilazione simultanea (+).|
|-checksumalgorithm:\<alg>|Specificare l'algoritmo per il calcolo del checksum del file di origine archiviato nel file PDB.  I valori supportati sono: SHA256 (impostazione predefinita) o SHA1.<br>A causa di problemi di conflitto con SHA1, Microsoft consiglia SHA256.|

## <a name="obsolete-options"></a>Opzioni obsolete

|Opzione|Scopo|
|---|---|
|-incremental|Abilita la compilazione incrementale.|

## <a name="see-also"></a>Vedere anche

- [Opzioni del compilatore C#](index.md)
- [Opzioni del compilatore C# in ordine alfabetico](listed-alphabetically.md)
- [Come impostare le variabili di ambiente per la riga di comando di Visual Studio](how-to-set-environment-variables-for-the-visual-studio-command-line.md)
