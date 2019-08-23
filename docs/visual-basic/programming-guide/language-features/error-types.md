---
title: Tipi di errore (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- exceptions, types
- errors [Visual Basic], types
- errors [Visual Basic], logic
- errors [Visual Basic], syntax
- logic errors [Visual Basic], Visual Basic
- run-time errors [Visual Basic], types of errors
- syntax errors [Visual Basic], Visual Basic
ms.assetid: 3048aabf-8c97-4e13-9150-853769cb5f6f
ms.openlocfilehash: ab554b60f7ba44ee0b92b76e1362ffdbb25f2afb
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69965373"
---
# <a name="error-types-visual-basic"></a>Tipi di errore (Visual Basic)
In Visual Basic gli errori rientrano in una delle tre categorie seguenti: errori di sintassi, errori di run-time ed errori logici.

## <a name="syntax-errors"></a>Errori di sintassi
 Gli *errori di sintassi* sono quelli visualizzati durante la scrittura del codice. Se si usa Visual Studio, Visual Basic controlla il codice durante la digitazione nella finestra dell' **Editor del codice** e avvisa l'utente se si commette un errore, ad esempio l'ortografia di una parola o l'uso errato di un elemento di linguaggio. Se si esegue la compilazione dalla riga di comando, Visual Basic Visualizza un errore del compilatore con informazioni sull'errore di sintassi. Gli errori di sintassi sono il tipo più comune di errori. È possibile correggerli facilmente nell'ambiente di codifica non appena si verificano.

> [!NOTE]
> L' `Option Explicit` istruzione è un modo per evitare errori di sintassi. Impone di dichiarare in anticipo tutte le variabili da usare nell'applicazione. Pertanto, quando tali variabili vengono utilizzate nel codice, eventuali errori tipografici vengono rilevati immediatamente e possono essere corretti.

## <a name="run-time-errors"></a>Errori di run-time
 Gli *errori di run-time* sono quelli visualizzati solo dopo la compilazione e l'esecuzione del codice. Queste implicano il codice che potrebbe sembrare corretto in quanto non presenta errori di sintassi, ma che non verrà eseguito. Ad esempio, è possibile scrivere correttamente una riga di codice per aprire un file. Tuttavia, se il file non esiste, l'applicazione non è in grado di aprire il file e viene generata un'eccezione. È possibile correggere la maggior parte degli errori di run-time riscrivendo il codice difettoso o utilizzando la [gestione delle eccezioni](../../language-reference/statements/try-catch-finally-statement.md), quindi ricompilando e rieseguendo il codice.
  
## <a name="logic-errors"></a>Errori di logica
 Gli *errori logici* sono quelli che vengono visualizzati una volta che l'applicazione è in uso. Spesso si tratta di presupposti difettosi creati dallo sviluppatore o risultati indesiderati o imprevisti in risposta alle azioni dell'utente. Una chiave tipizzata in modo errato, ad esempio, può fornire informazioni non corrette a un metodo oppure si presuppone che un valore valido venga sempre fornito a un metodo in caso contrario. Anche se gli errori logici possono essere gestiti tramite la [gestione delle eccezioni](../../language-reference/statements/try-catch-finally-statement.md) (ad esempio, verificando `Nothing` se un argomento <xref:System.ArgumentNullException>è e generando un), in genere devono essere risolti correggendo l'errore nella logica e ricompilando applicazione.

## <a name="see-also"></a>Vedere anche

- [Istruzione Try...Catch...Finally](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
- [Debugger Basics](/visualstudio/debugger/debugger-basics) (Nozioni di base sul debugger)
