---
title: Struttura di un programma Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- conditional compilation [Visual Basic], Visual Basic
- program structure [Visual Basic], Visual Basic
- procedures [Visual Basic], structure
- Visual Basic code, program structure
ms.assetid: ad0c6531-d762-4c77-a700-de16b07b6119
ms.openlocfilehash: dc6b38d78f02a42c8e7cc2aa964e9f3f74996f44
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84408764"
---
# <a name="structure-of-a-visual-basic-program"></a>Struttura di un programma Visual Basic
Un programma Visual Basic è costituito da blocchi predefiniti standard. Una *soluzione* è costituita da uno o più progetti. Un *progetto* può a sua volta contenere uno o più assembly. Ogni *assembly* viene compilato da uno o più file di origine. Un *file di origine* fornisce la definizione e l'implementazione di classi, strutture, moduli e interfacce, che in definitiva contengono tutto il codice.  
  
 Per ulteriori informazioni su questi blocchi predefiniti di un programma Visual Basic, vedere [soluzioni e progetti](/visualstudio/ide/solutions-and-projects-in-visual-studio) e [assembly in .NET](../../../standard/assembly/index.md).  
  
## <a name="file-level-programming-elements"></a>Elementi di programmazione a livello di file  
 Quando si avvia un progetto o un file e si apre l'editor di codice, viene visualizzato il codice già presente e nell'ordine corretto. Il codice scritto deve seguire la sequenza seguente:  
  
1. `Option`istruzioni  
  
2. `Imports`istruzioni  
  
3. `Namespace`istruzioni e elementi a livello di spazio dei nomi  
  
 Se si immettono istruzioni in un ordine diverso, possono verificarsi errori di compilazione.  
  
 Un programma può inoltre contenere istruzioni di compilazione condizionale. È possibile intervallare questi dati nel file di origine tra le istruzioni della sequenza precedente.  
  
### <a name="option-statements"></a>Istruzioni Option  
 `Option`le istruzioni stabiliscono regole di base per il codice successivo, evitando errori di sintassi e logica. L' [istruzione Option Explicit](../../language-reference/statements/option-explicit-statement.md) garantisce che tutte le variabili siano dichiarate e digitate correttamente, riducendo il tempo di debug. L' [istruzione Option Strict](../../language-reference/statements/option-strict-statement.md) consente di ridurre al minimo gli errori logici e la perdita di dati che possono verificarsi quando si lavora tra variabili di tipi di dati diversi. L' [istruzione Option Compare](../../language-reference/statements/option-compare-statement.md) specifica il modo in cui le stringhe vengono confrontate tra loro, in base ai relativi `Binary` `Text` valori o.  
  
### <a name="imports-statements"></a>Istruzioni Imports  
 È possibile includere un' [istruzione Imports (tipo e spazio dei nomi .NET)](../../language-reference/statements/imports-statement-net-namespace-and-type.md) per importare i nomi definiti all'esterno del progetto. Un' `Imports` istruzione consente al codice di fare riferimento alle classi e ad altri tipi definiti nello spazio dei nomi importato, senza doverli qualificare. È possibile utilizzare il numero di `Imports` istruzioni appropriato. Per ulteriori informazioni, vedere [riferimenti e l'istruzione Imports](references-and-the-imports-statement.md).  
  
### <a name="namespace-statements"></a>Istruzioni dello spazio dei nomi  
 Gli spazi dei nomi consentono di organizzare e classificare gli elementi di programmazione per semplificare il raggruppamento e l'accesso. L' [istruzione Namespace](../../language-reference/statements/namespace-statement.md) viene utilizzata per classificare le istruzioni seguenti all'interno di un determinato spazio dei nomi. Per ulteriori informazioni, vedere [Spazi dei nomi in Visual Basic](namespaces.md).  
  
### <a name="conditional-compilation-statements"></a>Istruzioni di compilazione condizionale  
 Le istruzioni di compilazione condizionale possono apparire praticamente in qualsiasi punto del file di origine. Provocano l'inclusione o l'esclusione di parti del codice in fase di compilazione, a seconda di determinate condizioni. È anche possibile usarli per eseguire il debug dell'applicazione, perché il codice condizionale viene eseguito solo in modalità di debug. Per altre informazioni, vedere [compilazione condizionale](conditional-compilation.md).  
  
## <a name="namespace-level-programming-elements"></a>Elementi di programmazione a livello di spazio dei nomi  
 Classi, strutture e moduli contengono tutto il codice presente nel file di origine. Si tratta di elementi a *livello di spazio dei nomi* che possono essere visualizzati all'interno di uno spazio dei nomi o a livello di file di origine. Che contengono le dichiarazioni di tutti gli altri elementi di programmazione. Le interfacce, che definiscono le firme degli elementi ma non forniscono alcuna implementazione, vengono visualizzate anche a livello di modulo. Per ulteriori informazioni sugli elementi a livello di modulo, vedere gli argomenti seguenti:  
  
- [Istruzione Class](../../language-reference/statements/class-statement.md)  
  
- [Istruzione Structure](../../language-reference/statements/structure-statement.md)  
  
- [Istruzione Module](../../language-reference/statements/module-statement.md)  
  
- [Istruzione Interface](../../language-reference/statements/interface-statement.md)  
  
 Gli elementi dati a livello di spazio dei nomi sono enumerazioni e delegati.  
  
## <a name="module-level-programming-elements"></a>Elementi di programmazione a livello di modulo  
 Procedure, operatori, proprietà ed eventi sono gli unici elementi di programmazione che possono conservare il codice eseguibile (istruzioni che eseguono azioni in fase di esecuzione). Sono gli elementi a *livello di modulo* del programma. Per ulteriori informazioni sugli elementi a livello di procedura, vedere gli argomenti seguenti:  
  
- [Istruzione Function](../../language-reference/statements/function-statement.md)  
  
- [Istruzione Sub](../../language-reference/statements/sub-statement.md)  
  
- [Declare Statement](../../language-reference/statements/declare-statement.md)  
  
- [Operator Statement](../../language-reference/statements/operator-statement.md)  
  
- [Property Statement](../../language-reference/statements/property-statement.md)  
  
- [Istruzione Event](../../language-reference/statements/event-statement.md)  
  
 Gli elementi dati a livello di modulo sono variabili, costanti, enumerazioni e delegati.  
  
## <a name="procedure-level-programming-elements"></a>Elementi di programmazione a livello di routine  
 La maggior parte del contenuto degli elementi a *livello di routine* sono istruzioni eseguibili, che costituiscono il codice di runtime del programma. Tutto il codice eseguibile deve essere in alcune procedure ( `Function` ,, `Sub` `Operator` , `Get` , `Set` , `AddHandler` , `RemoveHandler` , `RaiseEvent` ). Per altre informazioni, vedere [Istruzioni](../language-features/statements.md).  
  
 Gli elementi dati a livello di procedura sono limitati a variabili e costanti locali.  
  
## <a name="the-main-procedure"></a>Procedura principale  
 La `Main` procedura è il primo codice da eseguire quando l'applicazione è stata caricata. `Main`funge da punto di partenza e controllo generale per l'applicazione. Sono disponibili quattro tipi di `Main` :  
  
- `Sub Main()`  
  
- `Sub Main(ByVal cmdArgs() As String)`  
  
- `Function Main() As Integer`  
  
- `Function Main(ByVal cmdArgs() As String) As Integer`  
  
 La varietà più comune di questa procedura è `Sub Main()` . Per ulteriori informazioni, vedere la [procedura principale in Visual Basic](main-procedure.md).  
  
## <a name="see-also"></a>Vedere anche

- [Routine Main in Visual Basic](main-procedure.md)
- [Convenzioni di denominazione di Visual Basic](naming-conventions.md)
- [Limitazioni di Visual Basic](limitations.md)
