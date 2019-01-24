---
title: 'Procedura: Etichetta istruzioni (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- colons (:)
- statements [Visual Basic], labels
- ': separator character'
- Visual Basic code, labeling statements
ms.assetid: 38f1ff43-2054-42cb-963b-1998e60c6ed4
ms.openlocfilehash: 00a08bd3bd1f866cec883b6591b03ebd9d858b90
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54552260"
---
# <a name="how-to-label-statements-visual-basic"></a>Procedura: Etichetta istruzioni (Visual Basic)
Blocchi di istruzioni sono costituiti da righe di codice delimitati da punti. Righe di codice preceduto da una stringa o numero intero di identificazione si dice che trovano *etichettato*. Le etichette di istruzione vengono utilizzate per contrassegnare una riga di codice per facilitarne l'identificazione per l'uso con le istruzioni, ad esempio `On Error Goto`.  
  
 Le etichette possono essere identificatori Visual Basic validi, ad esempio quelli che identificano gli elementi di programmazione, o i valori letterali integer. Un'etichetta deve essere visualizzati all'inizio di una riga di codice sorgente e deve essere seguita da due punti, indipendentemente dal fatto che è seguito da un'istruzione nella stessa riga.  
  
 Il compilatore identifica le etichette, controllare se l'inizio della riga corrisponde a qualsiasi identificatore già definito. In caso contrario, il compilatore presuppone che sia un'etichetta.  
  
 Le etichette sono proprio spazio di dichiarazione e non interferiscono con altri identificatori. Ambito dell'etichetta è il corpo del metodo. Dichiarazione di etichetta ha la precedenza in qualsiasi situazione ambigua.  
  
> [!NOTE]
>  Le etichette possono essere utilizzate solo in istruzioni eseguibili nei metodi.  
  
### <a name="to-label-a-line-of-code"></a>Per assegnare un'etichetta di una riga di codice  
  
-   Inserire un identificatore, seguito da due punti, all'inizio della riga di codice sorgente.  
  
     Ad esempio, le righe di codice seguenti sono contrassegnate con `Jump` e `120`, rispettivamente:  
  
     [!code-vb[VbVbalrStatements#708](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/how-to-label-statements_1.vb)]  
  
## <a name="see-also"></a>Vedere anche
- [Istruzioni](../../../visual-basic/programming-guide/language-features/statements.md)
- [Nomi di elementi dichiarati](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)
- [Struttura del programma e convenzioni di scrittura del codice](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md)
