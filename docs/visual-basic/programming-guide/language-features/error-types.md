---
title: Tipi di errore (Visual Basic)
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- exceptions, types
- errors [Visual Basic], types
- errors [Visual Basic], logic
- errors [Visual Basic], syntax
- logic errors [Visual Basic], Visual Basic
- run-time errors [Visual Basic], types of errors
- syntax errors [Visual Basic], Visual Basic
ms.assetid: 3048aabf-8c97-4e13-9150-853769cb5f6f
caps.latest.revision: 13
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 2b3cf1307f54a5c902bf8e6379c8760c735a45e4
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/26/2018
---
# <a name="error-types-visual-basic"></a>Tipi di errore (Visual Basic)
In Visual Basic, gli errori (chiamato anche *eccezioni*) rientrano in una delle tre categorie: errori di sintassi, errori di run-time e gli errori di logica.  
  
## <a name="syntax-errors"></a>Errori di sintassi  
 *Errori di sintassi* vengono visualizzati durante la scrittura di codice. Visual Basic controlla il codice come si digita il **Editor di codice** finestra e genera avvisi se si commette un errore, ad esempio ortografia errata di una parola o l'utilizzo improprio di un elemento di linguaggio. Errori di sintassi sono il tipo più comune di errori. È possibile correggerli facilmente nell'ambiente di codifica, non appena si verificano.  
  
> [!NOTE]
>  Il `Option Explicit` istruzione è consente di evitare errori di sintassi. Impone di dichiarare in anticipo, tutte le variabili da utilizzare nell'applicazione. Pertanto, quando tali variabili vengono utilizzate nel codice, gli errori di digitazione vengono rilevati immediatamente e possono essere risolto.  
  
## <a name="run-time-errors"></a>Errori di Run-Time  
 *Errori di run-time* sono quelli che vengono visualizzate solo dopo che viene compilato ed eseguito il codice. Che implicano il codice che potrebbe risultare corretto in quanto non ha gli errori di sintassi, ma che non verrà eseguito. Ad esempio, è possibile scrivere correttamente una riga di codice per aprire un file. Ma se il file è danneggiato, l'applicazione non è possibile eseguire il `Open` (funzione) e arresta l'esecuzione. È possibile risolvere la maggior parte degli errori di runtime per la riscrittura del codice non corretto, quindi ricompilare ed eseguirla nuovamente.  
  
## <a name="logic-errors"></a>Errori di logica  
 *Errori di logica* vengono visualizzati una volta che l'applicazione è in uso. Sono la maggior parte dei risultati indesiderati o imprevisti in risposta alle azioni dell'utente. Ad esempio, una chiave digitata incorrettamente o altri determini potrebbero causare l'applicazione per smettere di funzionare nei parametri previsti o del tutto. Errori logici sono in genere il tipo più difficile da risolvere poiché non è sempre chiaro in cui sono generati.  
  
## <a name="see-also"></a>Vedere anche  
 [Istruzione Try...Catch...Finally](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)  
 [Debugger Basics](/visualstudio/debugger/debugger-basics) (Nozioni di base sul debugger)
