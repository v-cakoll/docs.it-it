---
title: 'Procedura: etichettare le istruzioni (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- colons (:)
- statements [Visual Basic], labels
- ': separator character'
- Visual Basic code, labeling statements
ms.assetid: 38f1ff43-2054-42cb-963b-1998e60c6ed4
ms.openlocfilehash: df368bdba73ca35dd70bdd2f4e88cc10af894b5a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33650124"
---
# <a name="how-to-label-statements-visual-basic"></a>Procedura: etichettare le istruzioni (Visual Basic)
Blocchi di istruzioni sono costituiti da righe di codice delimitati da virgola. Righe di codice preceduto da una stringa di identificazione o intero rientrano *etichetta*. Le etichette di istruzione vengono utilizzate per contrassegnare una riga di codice per facilitarne l'identificazione per l'utilizzo con le istruzioni, ad esempio `On Error Goto`.  
  
 Le etichette possono essere identificatori validi di Visual Basic, ad esempio quelle che identificano gli elementi di programmazione, o valori letterali integer. Un'etichetta deve trovarsi all'inizio di una riga di codice sorgente e deve essere seguita da due punti, indipendentemente dal fatto che è seguito da un'istruzione sulla stessa riga.  
  
 Il compilatore identifica le etichette verificando se l'inizio della riga corrisponde a qualsiasi identificatore già definito. In caso contrario, il compilatore presuppone che sia un'etichetta.  
  
 Le etichette sono proprio spazio di dichiarazione e non interferiscono con altri identificatori. Ambito di un'etichetta è il corpo del metodo. Dichiarazione di etichetta ha la precedenza in caso di ambiguità.  
  
> [!NOTE]
>  Le etichette possono essere utilizzate solo in istruzioni eseguibili all'interno di metodi.  
  
### <a name="to-label-a-line-of-code"></a>Per assegnare un'etichetta di una riga di codice  
  
-   Inserire un identificatore, seguito da due punti, all'inizio della riga di codice sorgente.  
  
     Ad esempio, le righe di codice seguente vengono etichettate con `Jump` e `120`, rispettivamente:  
  
     [!code-vb[VbVbalrStatements#708](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/how-to-label-statements_1.vb)]  
  
## <a name="see-also"></a>Vedere anche  
 [Istruzioni](../../../visual-basic/programming-guide/language-features/statements.md)  
 [Nomi di elementi dichiarati](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)  
 [Struttura del programma e convenzioni di scrittura del codice](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md)
