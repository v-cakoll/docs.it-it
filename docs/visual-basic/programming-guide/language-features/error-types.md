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
ms.openlocfilehash: 07db963ac3cf9d1c0d17c420480189d362cdaf2c
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2019
ms.locfileid: "58831566"
---
# <a name="error-types-visual-basic"></a>Tipi di errore (Visual Basic)
In Visual Basic, gli errori (chiamato anche *eccezioni*) possono essere suddivise in tre categorie: errori di sintassi, gli errori di runtime ed errori per la logica.  
  
## <a name="syntax-errors"></a>Errori di sintassi  
 *Errori di sintassi* sono quelli che vengono visualizzati durante la scrittura di codice. Visual Basic controlla il codice durante la digitazione nel **Editor di codice** finestra e genera avvisi se si commette un errore, ad esempio ortografia errata di una parola o utilizzo improprio di un elemento di linguaggio. Errori di sintassi sono il tipo più comune degli errori. È possibile correggerli con facilità nell'ambiente di codifica, non appena si verificano.  
  
> [!NOTE]
>  Il `Option Explicit` istruzione è consente di evitare errori di sintassi. Viene forzato, è possibile dichiarare in anticipo, tutte le variabili da utilizzare nell'applicazione. Pertanto, quando tali variabili vengono usate nel codice, gli errori di digitazione vengono rilevati immediatamente e possono essere corretti.  
  
## <a name="run-time-errors"></a>Errori di Run-Time  
 *Errori di run-time* sono quelli che vengono visualizzate solo dopo che viene compilato ed eseguito il codice. Queste comprendono il codice che può sembrare corretto che non siano presenti errori di sintassi, ma che non verranno eseguiti. Ad esempio, si potrebbe scrivere correttamente una riga di codice per aprire un file. Ma se il file è danneggiato, l'applicazione non è possibile eseguire il `Open` funzione e interrompe l'esecuzione. Per risolvere la maggior parte degli errori di runtime, riscrivere il codice non corretto, quindi ricompilare ed eseguirla nuovamente.  
  
## <a name="logic-errors"></a>Errori di logica  
 *Errori di logica* vengono visualizzati una volta che l'applicazione è in uso. Sono la maggior parte dei risultati indesiderati o imprevisti in risposta alle azioni dell'utente. Ad esempio, una chiave digitata incorrettamente o altri determini potrebbero causare l'applicazione per smettere di funzionare nei parametri previsti o completamente. Gli errori per la logica sono in genere il tipo più difficile da risolvere, poiché non è sempre chiaro dove provengono.  
  
## <a name="see-also"></a>Vedere anche

- [Istruzione Try...Catch...Finally](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
- [Debugger Basics](/visualstudio/debugger/debugger-basics) (Nozioni di base sul debugger)
