---
title: Struttura di un programma Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- conditional compilation [Visual Basic], Visual Basic
- program structure [Visual Basic], Visual Basic
- procedures [Visual Basic], structure
- Visual Basic code, program structure
ms.assetid: ad0c6531-d762-4c77-a700-de16b07b6119
ms.openlocfilehash: 42e366a844f9c5e80a8f617bf73dfd869608540d
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59295770"
---
# <a name="structure-of-a-visual-basic-program"></a>Struttura di un programma Visual Basic
Un programma Visual Basic è composto da blocchi di compilazione standard. Oggetto *soluzione* è costituito da uno o più progetti. Oggetto *progetto* a sua volta può contenere uno o più assembly. Ciascuna *assembly* viene compilato da uno o più file di origine. Oggetto *file di origine* fornisce la definizione e implementazione di classi, strutture, moduli e interfacce che contengono infine tutto il codice.  
  
 Per altre informazioni su questi blocchi predefiniti di un programma Visual Basic, vedere [progetti e soluzioni](/visualstudio/ide/solutions-and-projects-in-visual-studio) e [assembly in .NET](../../../standard/assembly/index.md).  
  
## <a name="file-level-programming-elements"></a>Elementi di programmazione a livello di file  
 Quando si avvia un progetto o un file e aprire l'editor di codice, viene visualizzato un codice già in uso e nell'ordine corretto. Qualsiasi codice che si scrive deve seguire la sequenza seguente:  
  
1. `Option` Istruzioni  
  
2. `Imports` Istruzioni  
  
3. `Namespace` istruzioni e gli elementi a livello di spazio dei nomi  
  
 Se si immettono istruzioni in un ordine diverso, possono causare errori di compilazione.  
  
 Un programma può contenere anche istruzioni di compilazione condizionale. È possibile integrare questi elementi nel file di origine tra le istruzioni della sequenza precedente.  
  
### <a name="option-statements"></a>Istruzione Option  
 `Option` le istruzioni stabiliscono le regole di base per il codice successivo, contribuendo ad evitare errori di sintassi e per la logica. Il [istruzione Option Explicit](../../../visual-basic/language-reference/statements/option-explicit-statement.md) garantisce che tutte le variabili vengono dichiarate e digitate correttamente, riducendo in fase di debug. Il [Option Strict Statement](../../../visual-basic/language-reference/statements/option-strict-statement.md) consente di ridurre al minimo per la logica degli errori e perdita di dati che può verificarsi quando si lavora alternando tra le variabili dei tipi di dati diversi. Il [istruzione Option Compare](../../../visual-basic/language-reference/statements/option-compare-statement.md) specifica le stringhe di modalità devono essere confrontate tra loro, in base a una loro `Binary` o `Text` valori.  
  
### <a name="imports-statements"></a>Istruzioni Imports  
 È possibile includere un' [istruzione Imports (tipo e .NET Namespace)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) per importare i nomi definiti all'esterno del progetto. Un `Imports` istruzione consente al codice fare riferimento alle classi e altri tipi definiti nello spazio dei nomi importato, senza la necessità di fornire il nome completo. È possibile usare come molte `Imports` istruzioni come appropriato. Per altre informazioni, vedere [riferimenti e istruzione Imports](../../../visual-basic/programming-guide/program-structure/references-and-the-imports-statement.md).  
  
### <a name="namespace-statements"></a>Istruzioni Namespace  
 Gli spazi dei nomi utili per organizzare e classificare gli elementi di programmazione per semplificare il raggruppamento e l'accesso. Si utilizza il [istruzione Namespace](../../../visual-basic/language-reference/statements/namespace-statement.md) per classificare le seguenti istruzioni all'interno di un determinato spazio dei nomi. Per ulteriori informazioni, vedere [Spazi dei nomi in Visual Basic](../../../visual-basic/programming-guide/program-structure/namespaces.md).  
  
### <a name="conditional-compilation-statements"></a>Istruzioni di compilazione condizionale  
 Le istruzioni di compilazione condizionale possono essere presenti quasi ovunque nel file di origine. Che possano provocare parti del codice da includere o escludere in fase di compilazione in base a determinate condizioni. È possibile anche usare li per eseguire il debug dell'applicazione, perché il codice condizionale viene eseguito in modalità solo di debug. Per altre informazioni, vedere [compilazione condizionale](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md).  
  
## <a name="namespace-level-programming-elements"></a>Elementi di programmazione a livello di Namespace  
 Le classi, strutture e i moduli contengono tutto il codice nel file di origine. Si trovano *a livello di spazio dei nomi* elementi, che possono essere visualizzati all'interno di uno spazio dei nomi o a livello di file di origine. Contengono le dichiarazioni di tutti gli altri elementi di programmazione. Interfacce che definiscono le firme di elemento, ma non forniscono alcuna implementazione, vengono visualizzati anche a livello di modulo. Per altre informazioni sugli elementi a livello di modulo, vedere gli argomenti seguenti:  
  
-   [Istruzione Class](../../../visual-basic/language-reference/statements/class-statement.md)  
  
-   [Istruzione Structure](../../../visual-basic/language-reference/statements/structure-statement.md)  
  
-   [Istruzione Module](../../../visual-basic/language-reference/statements/module-statement.md)  
  
-   [Istruzione Interface](../../../visual-basic/language-reference/statements/interface-statement.md)  
  
 Gli elementi di dati a livello di spazio dei nomi sono le enumerazioni e delegati.  
  
## <a name="module-level-programming-elements"></a>Elementi di programmazione a livello di modulo  
 Le procedure, operatori, proprietà ed eventi sono gli unici elementi di programmazione che possono contenere codice eseguibile (istruzioni che eseguono azioni in fase di esecuzione). Sono le *a livello di modulo* gli elementi del programma. Per altre informazioni sugli elementi a livello di routine, vedere gli argomenti seguenti:  
  
-   [Istruzione Function](../../../visual-basic/language-reference/statements/function-statement.md)  
  
-   [Istruzione Sub](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
-   [Istruzione Declare](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
-   [Istruzione Operator](../../../visual-basic/language-reference/statements/operator-statement.md)  
  
-   [Istruzione Property](../../../visual-basic/language-reference/statements/property-statement.md)  
  
-   [Istruzione Event](../../../visual-basic/language-reference/statements/event-statement.md)  
  
 Gli elementi di dati a livello di modulo sono variabili, costanti, enumerazioni e delegati.  
  
## <a name="procedure-level-programming-elements"></a>Elementi di programmazione a livello di routine  
 La maggior parte del contenuto del *a livello di routine* elementi sono istruzioni eseguibili, che costituiscono il codice in fase di esecuzione del programma. Tutto il codice eseguibile deve essere in una procedura (`Function`, `Sub`, `Operator`, `Get`, `Set`, `AddHandler`, `RemoveHandler`, `RaiseEvent`). Per altre informazioni, vedere [Istruzioni](../../../visual-basic/programming-guide/language-features/statements.md).  
  
 Gli elementi di dati a livello di routine sono limitati alle costanti e variabili locali.  
  
## <a name="the-main-procedure"></a>Procedura principale  
 Il `Main` procedure è il primo codice da eseguire quando l'applicazione è stato caricato. `Main` viene utilizzato come il punto di partenza e controllo generale per l'applicazione. Esistono quattro versioni di `Main`:  
  
-   `Sub Main()`  
  
-   `Sub Main(ByVal cmdArgs() As String)`  
  
-   `Function Main() As Integer`  
  
-   `Function Main(ByVal cmdArgs() As String) As Integer`  
  
 Il più comune di questa procedura è `Sub Main()`. Per altre informazioni, vedere [routine Main in Visual Basic](../../../visual-basic/programming-guide/program-structure/main-procedure.md).  
  
## <a name="see-also"></a>Vedere anche

- [Routine Main in Visual Basic](../../../visual-basic/programming-guide/program-structure/main-procedure.md)
- [Convenzioni di denominazione di Visual Basic](../../../visual-basic/programming-guide/program-structure/naming-conventions.md)
- [Limitazioni di Visual Basic](../../../visual-basic/programming-guide/program-structure/limitations.md)
