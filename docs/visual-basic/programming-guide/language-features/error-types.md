---
title: Tipi di errore
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
ms.openlocfilehash: 107d93429ad0440ed18169bc6b6ca7b2e21cb77a
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84405144"
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
 Gli *errori logici* sono quelli che vengono visualizzati una volta che l'applicazione è in uso. Spesso si tratta di presupposti difettosi creati dallo sviluppatore o risultati indesiderati o imprevisti in risposta alle azioni dell'utente. Una chiave tipizzata in modo errato, ad esempio, può fornire informazioni non corrette a un metodo oppure si presuppone che un valore valido venga sempre fornito a un metodo in caso contrario. Anche se gli errori logici possono essere gestiti tramite la [gestione delle eccezioni](../../language-reference/statements/try-catch-finally-statement.md) (ad esempio, verificando se un argomento è `Nothing` e generando un <xref:System.ArgumentNullException> ), in genere devono essere risolti correggendo l'errore nella logica e ricompilando l'applicazione.

## <a name="see-also"></a>Vedere anche

- [Istruzione Try...Catch...Finally](../../language-reference/statements/try-catch-finally-statement.md)
- [Nozioni di base sul debugger](/visualstudio/debugger/debugger-feature-tour)
