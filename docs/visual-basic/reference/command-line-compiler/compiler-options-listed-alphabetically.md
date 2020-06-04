---
title: Opzioni del compilatore elencate in ordine alfabetico
ms.date: 04/12/2018
helpviewer_keywords:
- Visual Basic compiler, options
ms.assetid: e67febba-bacf-4e1f-a143-c141e063f90e
ms.openlocfilehash: 19e14953c08f90ea1ab245fa3124a462ccba162f
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84408738"
---
# <a name="visual-basic-compiler-options-listed-alphabetically"></a>Opzioni del compilatore Visual Basic elencate in ordine alfabetico
Il Visual Basic compilatore della riga di comando viene fornito come alternativa alla compilazione di programmi da Visual Studio Integrated Development Environment (IDE). Di seguito è riportato un elenco delle opzioni del compilatore da riga di comando Visual Basic ordinate alfabeticamente.  

[!INCLUDE[compiler-options](~/includes/compiler-options.md)]
  
|Opzione|Scopo|  
|------------|-------------|  
|[@ (Specifica di un file di risposta)](specify-response-file.md)|Specifica un file di risposta.|  
|[-?](help.md)|Visualizza le opzioni del compilatore. Questo comando ha la stessa funzione dell'opzione `-help`. Non viene effettuata alcuna compilazione.|  
|`-additionalfile`|Assegna un nome ad altri file che non influiscono direttamente sulla generazione del codice, ma possono essere usati dagli analizzatori per produrre errori o avvisi.|  
|[-addmodule](addmodule.md)|Fa sì che il compilatore renda disponibili per il progetto in compilazione tutte le informazioni sui tipi presenti nei file specificati.|  
|`-analyzer`|Esegue gli analizzatori da questo assembly (forma breve: -a)|  
|[-baseaddress](baseaddress.md)|Specifica l'indirizzo di base di una DLL.|  
|[-bugreport](bugreport.md)|Crea un file contenente informazioni che rendono più semplice segnalare un bug.|  
|`-checksumalgorithm:<alg>`|Specificare l'algoritmo per il calcolo del checksum del file di origine archiviato nel file PDB.  I valori supportati sono: SHA1 (predefinito) o SHA256. <br>A causa di problemi di collisione con SHA1, Microsoft consiglia di SHA256 o meglio.|  
|[-codepage](codepage.md)|Specifica la tabella codici da usare per tutti i file del codice sorgente nella compilazione.|  
|[-debug](debug.md)|Crea informazioni di debug.|  
|[-define](define.md)|Definisce simboli per la compilazione condizionale.|  
|[-delaysign](delaysign.md)|Specifica se l'assembly avrà firma completa o parziale.|  
|[-deterministic](deterministic.md)|Fa sì che l'output del compilatore sia un assembly il cui contenuto binario è identico in tutte le compilazioni se gli input sono identici.|
|[-doc](doc.md)|Elabora commenti sulla documentazione in un file XML.|  
|[-errorreport](errorreport.md)|Specifica il modo in cui il compilatore di Visual Basic deve segnalare gli errori interni del compilatore.|  
|[-filealign](filealign.md)|Specifica la posizione di allineamento per le sezioni del file di output.|  
|[-Guida](help.md)|Visualizza le opzioni del compilatore. Questo comando ha la stessa funzione dell'opzione `-?`. Non viene effettuata alcuna compilazione.|  
|[-highentropyva](highentropyva.md)|Indica se un particolare eseguibile supporta ASLR (Address Space Layout Randomization) a entropia elevata.|  
|[-imports](imports.md)|Importa uno spazio dei nomi dall'assembly specificato.|  
|[-keycontainer](keycontainer.md)|Specifica il nome di un contenitore di chiavi per una coppia di chiavi allo scopo di assegnare a un assembly un nome sicuro.|  
|[-filefile](keyfile.md)|Specifica un file che contiene una chiave o una coppia di chiavi allo scopo di assegnare a un assembly un nome sicuro.|  
|[-langversion](langversion.md)|Specificare la versione del linguaggio: 9&#124;9,0&#124;10&#124;10,0&#124;11&#124;11,0.|  
|[-libpath](libpath.md)|Specifica il percorso degli assembly a cui fa riferimento l'opzione [-Reference](reference.md) .|  
|[-linkresource](linkresource.md)|Crea un collegamento a una risorsa gestita.|  
|[-main](main.md)|Specifica la classe che contiene la `Sub Main` procedura da utilizzare all'avvio.|  
|[-moduleassemblyname](moduleassemblyname.md)|Specifica il nome dell'assembly che conterrà un modulo.|  
|`-modulename:<string>`|Specificare il nome del modulo di origine|  
|[-netcf](netcf.md)|Imposta il compilatore in modo che abbia come destinazione la .NET Compact Framework.|  
|[-noconfig](noconfig.md)|La compilazione non viene eseguita con Vbc.rsp.|  
|[-nologo](nologo.md)|Elimina i messaggi informativi del compilatore.|  
|[-nostdlib](nostdlib.md)|Indica al compilatore di non fare riferimento alle librerie standard.|  
|[-nowarn](nowarn.md)|Inibisce la capacità del compilatore di generare avvisi.|  
|[-nowin32manifest](nowin32manifest.md)|Indica al compilatore di non incorporare un manifesto dell'applicazione nel file eseguibile.|  
|[-Ottimizza](optimize.md)|Abilita/disabilita l'ottimizzazione del codice.|  
|[-optioncompare](optioncompare.md)|Specifica se il confronto si verifica tra stringhe di tipo binario oppure se usare una semantica basata sul testo specifica delle impostazioni locali definite.|  
|[-optionexplicit](optionexplicit.md)|Richiede la dichiarazione esplicita delle variabili.|  
|[-optioninfer](optioninfer.md)|Consente di usare l'inferenza del tipo di variabile locale nelle dichiarazioni di variabile.|  
|[-optionstrict](optionstrict.md)|Attiva la semantica del linguaggio rigorosa.|  
|[-out](out.md)|Specifica un file di output.|  
|<code>-parallel[+&#124;-]</code>|Specifica se usare la compilazione simultanea (+).|  
|[-piattaforma](platform.md)|Specifica la piattaforma del processore da impostare come destinazione del file di output.|  
|`-preferreduilang`|Specificare il nome della lingua di output preferita.|  
|[-quiet](quiet.md)|Impedisce al compilatore di visualizzare codice per avvisi ed errori relativi alla sintassi.|  
|[-recurse](recurse.md)|Cerca nelle sottodirectory i file di origine da compilare.|  
|[-riferimento](reference.md)|Importa metadati da un assembly.|  
|[-refonly](refonly-compiler-option.md)|Restituisce solo un assembly di riferimento.|
|[-refout](refout-compiler-option.md)|Specifica il percorso di output di un assembly di riferimento.|
|[-removeintchecks](removeintchecks.md)|Disabilita il controllo dell'overflow di Integer.|  
|[-risorsa](resource.md)|Incorpora una risorsa gestita in un assembly.|  
|[-rootnamespace](rootnamespace.md)|Specifica uno spazio dei nomi per tutte le dichiarazioni di tipo.|  
|`-ruleset:<file>`|Specificare un file di set di regole che disabilita la diagnostica specifica.|  
|[-sdkpath (](sdkpath.md)|Specifica il percorso dei file Mscorlib.dll e Microsoft.VisualBasic.dll.|  
|[-subsystemversion](subsystemversion.md)|Specifica la versione minima del sottosistema che può essere usata dal file eseguibile generato.|  
|[-target](target.md)|Specifica il formato del file di output.|  
|[-utf8output](utf8output.md)|Visualizza l'output del compilatore usando la codifica UTF-8.|  
|[-vbruntime](vbruntime.md)|Indica che il compilatore deve compilare senza un riferimento alla libreria di runtime di Visual Basic oppure con un riferimento a una libreria di runtime specifica.|  
|[-Verbose](verbose.md)|Restituisce informazioni supplementari durante la compilazione.|  
|[-warnaserror](warnaserror.md)|Alza il livello degli avvisi a errori.|  
|[-win32icon](win32icon.md)|Inserisce un file ico nel file di output.|  
|[-win32manifest](win32manifest.md)|Identifica un file manifesto dell'applicazione Win32 definito dall'utente da incorporare nel file eseguibile di tipo PE di un progetto.|  
|[-win32resource](win32resource.md)|Inserisce una risorsa Win32 nel file di output.|  
  
## <a name="see-also"></a>Vedere anche

- [Opzioni del compilatore Visual Basic elencate per categoria](compiler-options-listed-by-category.md)
- [Gestire le proprietà di progetti e soluzioni](/visualstudio/ide/managing-project-and-solution-properties)
