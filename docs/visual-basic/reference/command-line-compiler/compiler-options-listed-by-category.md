---
title: Opzioni del compilatore elencate per categoria
ms.date: 04/12/2018
helpviewer_keywords:
- Visual Basic compiler, options
ms.assetid: fbe36f7a-7cfa-4f77-a8d4-2be5958568e3
ms.openlocfilehash: 533d3da2f76854d311262ce97b43f240acab5f7d
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84408751"
---
# <a name="visual-basic-compiler-options-listed-by-category"></a>Visual Basic opzioni del compilatore elencate per categoria
Il Visual Basic compilatore della riga di comando viene fornito come alternativa alla compilazione di programmi dall'interno di Visual Studio Integrated Development Environment (IDE). Di seguito è riportato un elenco delle opzioni del compilatore da riga di comando Visual Basic ordinate in base alla categoria funzionale.  

[!INCLUDE[compiler-options](~/includes/compiler-options.md)]
  
## <a name="compiler-output"></a>Output del compilatore  
  
|Opzione|Scopo|  
|---|---|  
|[-nologo](nologo.md)|Elimina i messaggi informativi del compilatore.|  
|[-utf8output](utf8output.md)|Visualizza l'output del compilatore usando la codifica UTF-8.|  
|[-Verbose](verbose.md)|Restituisce informazioni supplementari durante la compilazione.|  
|`-modulename:<string>`|Specificare il nome del modulo di origine|  
|[-preferreduilang](../../../csharp/language-reference/compiler-options/preferreduilang-compiler-option.md)|Specificare una lingua per l'output del compilatore.|
  
## <a name="optimization"></a>Optimization  
  
|Opzione|Scopo|  
|---|---|  
|[-filealign](filealign.md)|Specifica la posizione di allineamento per le sezioni del file di output.|  
|[-Ottimizza](optimize.md)|Abilita/disabilita le ottimizzazioni.|  
  
## <a name="output-files"></a>File di output  
  
|Opzione|Scopo|  
|---|---|  
|[-doc](doc.md)|Elabora commenti per la documentazione in un file XML.|  
|[-deterministic](deterministic.md)|Fa sì che l'output del compilatore sia un assembly il cui contenuto binario è identico in tutte le compilazioni se gli input sono identici.|
|[-netcf](netcf.md)|Imposta il compilatore in modo che abbia come destinazione la .NET Compact Framework.|  
|[-out](out.md)|Specifica un file di output.|  
|[-refonly](refonly-compiler-option.md)|Restituisce solo un assembly di riferimento.|
|[-refout](refout-compiler-option.md)|Specifica il percorso di output di un assembly di riferimento.|
|[-target](target.md)|Specifica il formato dell'output.|  
  
## <a name="net-assemblies"></a>assembly .NET  
  
|Opzione|Scopo|  
|---|---|  
|[-addmodule](addmodule.md)|Fa sì che il compilatore renda disponibili per il progetto in compilazione tutte le informazioni sui tipi presenti nei file specificati.|  
|[-delaysign](delaysign.md)|Specifica se l'assembly avrà firma completa o parziale.|  
|[-imports](imports.md)|Importa uno spazio dei nomi dall'assembly specificato.|  
|[-keycontainer](keycontainer.md)|Specifica il nome di un contenitore di chiavi per una coppia di chiavi allo scopo di assegnare a un assembly un nome sicuro.|  
|[-filefile](keyfile.md)|Specifica un file contenente una chiave o una coppia di chiavi allo scopo di assegnare a un assembly un nome sicuro.|  
|[-libpath](libpath.md)|Specifica il percorso degli assembly a cui fa riferimento l'opzione [-Reference](reference.md) .|  
|[-riferimento](reference.md)|Importa metadati da un assembly.|  
|[-moduleassemblyname](moduleassemblyname.md)|Specifica il nome dell'assembly che conterrà un modulo.|  
|`-analyzer`|Esegue gli analizzatori da questo assembly (forma breve: -a)|  
|`-additionalfile`|Assegna un nome ad altri file che non influiscono direttamente sulla generazione del codice, ma possono essere usati dagli analizzatori per produrre errori o avvisi.|  
  
## <a name="debuggingerror-checking"></a>Debug/controllo degli errori  
  
|Opzione|Scopo|  
|---|---|  
|[-bugreport](bugreport.md)|Crea un file contenente informazioni che rendono più semplice segnalare un bug.|  
|[-debug](debug.md)|Crea informazioni di debug.|  
|[-nowarn](nowarn.md)|Inibisce la capacità del compilatore di generare avvisi.|  
|[-quiet](quiet.md)|Impedisce al compilatore di visualizzare codice per avvisi ed errori relativi alla sintassi.|  
|[-removeintchecks](removeintchecks.md)|Disabilita il controllo dell'overflow di Integer.|  
|[-warnaserror](warnaserror.md)|Alza il livello degli avvisi a errori.|  
|`-ruleset:<file>`|Specificare un file di set di regole che disabilita la diagnostica specifica.|  
  
## <a name="help"></a>Guida  
  
|Opzione|Scopo|  
|---|---|  
|[-?](help.md)|Visualizza le opzioni del compilatore. Questo comando ha la stessa funzione dell'opzione `-help`. Non viene effettuata alcuna compilazione.|  
|[-Guida](help.md)|Visualizza le opzioni del compilatore. Questo comando ha la stessa funzione dell'opzione `-?`. Non viene effettuata alcuna compilazione.|  
  
## <a name="language"></a>Linguaggio  
  
|Opzione|Scopo|  
|---|---|  
|[-langversion](langversion.md)|Specificare la versione del linguaggio: 9&#124;9,0&#124;10&#124;10,0&#124;11&#124;11,0.|  
|[-optionexplicit](optionexplicit.md)|Richiede la dichiarazione esplicita delle variabili.|  
|[-optionstrict](optionstrict.md)|Attiva la semantica dei tipi rigorosa.|  
|[-optioncompare](optioncompare.md)|Specifica se il confronto si verifica tra stringhe di tipo binario oppure se usare una semantica basata sul testo specifica delle impostazioni locali definite.|  
|[-optioninfer](optioninfer.md)|Consente di usare l'inferenza del tipo di variabile locale nelle dichiarazioni di variabile.|  
  
## <a name="preprocessor"></a>Preprocessore  
  
|Opzione|Scopo|  
|---|---|  
|[-define](define.md)|Definisce simboli per la compilazione condizionale.|  
  
## <a name="resources"></a>Risorse  
  
|Opzione|Scopo|  
|---|---|  
|[-linkresource](linkresource.md)|Crea un collegamento a una risorsa gestita.|  
|[-risorsa](resource.md)|Incorpora una risorsa gestita in un assembly.|  
|[-win32icon](win32icon.md)|Inserisce un file ico nel file di output.|  
|[-win32resource](win32resource.md)|Inserisce una risorsa Win32 nel file di output.|  
  
## <a name="miscellaneous"></a>Varie  
  
|Opzione|Scopo|  
|---|---|  
|[@ (Specifica di un file di risposta)](specify-response-file.md)|Specifica un file di risposta.|  
|[-baseaddress](baseaddress.md)|Specifica l'indirizzo di base di una DLL.|  
|[-codepage](codepage.md)|Specifica la tabella codici da usare per tutti i file del codice sorgente nella compilazione.|  
|[-errorreport](errorreport.md)|Specifica il modo in cui il compilatore di Visual Basic deve segnalare gli errori interni del compilatore.|  
|[-highentropyva](highentropyva.md)|Indica al kernel di Windows se un particolare eseguibile supporta ASLR (Address Space Layout Randomization) a entropia elevata.|  
|[-main](main.md)|Specifica la classe che contiene la `Sub Main` procedura da utilizzare all'avvio.|  
|[-noconfig](noconfig.md)|La compilazione non viene eseguita con Vbc.rsp|  
|[-nostdlib](nostdlib.md)|Indica al compilatore di non fare riferimento alle librerie standard.|  
|[-nowin32manifest](nowin32manifest.md)|Indica al compilatore di non incorporare un manifesto dell'applicazione nel file eseguibile.|  
|[-piattaforma](platform.md)|Specifica la piattaforma del processore da impostare come destinazione del file di output.|  
|[-recurse](recurse.md)|Cerca nelle sottodirectory i file di origine da compilare.|  
|[-rootnamespace](rootnamespace.md)|Specifica uno spazio dei nomi per tutte le dichiarazioni di tipo.|  
|[-sdkpath (](sdkpath.md)|Specifica il percorso dei file Mscorlib.dll e Microsoft.VisualBasic.dll.|  
|[-vbruntime](vbruntime.md)|Indica che il compilatore deve compilare senza un riferimento alla libreria di runtime di Visual Basic oppure con un riferimento a una libreria di runtime specifica.|  
|[-win32manifest](win32manifest.md)|Identifica un file manifesto dell'applicazione Win32 definito dall'utente da incorporare nel file eseguibile di tipo PE di un progetto.|  
|`-parallel[+&#124;-]`|Specifica se usare la compilazione simultanea (+).|  
|`-checksumalgorithm:<alg>`|Specificare l'algoritmo per il calcolo del checksum del file di origine archiviato nel file PDB.  I valori supportati sono: SHA1 (predefinito) o SHA256. <br>A causa di problemi di collisione con SHA1, Microsoft consiglia di SHA256 o meglio.|  
  
## <a name="see-also"></a>Vedere anche

- [Opzioni del compilatore Visual Basic in ordine alfabetico](compiler-options-listed-alphabetically.md)
- [Gestire le proprietà di progetti e soluzioni](/visualstudio/ide/managing-project-and-solution-properties)
