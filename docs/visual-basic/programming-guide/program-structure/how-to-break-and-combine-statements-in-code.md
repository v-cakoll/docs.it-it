---
title: 'Procedura: Interrompere e combinare istruzioni nel codice (Visual Basic)'
ms.date: 07/20/2015
f1_keywords:
- vb._
helpviewer_keywords:
- colons (:)
- line continuation
- _ line-continuation character
- ': line separator character'
- Visual Basic code, line breaks in
- Visual Basic code, line breaks
- Visual Basic code, line continuation
- long lines of code
- line terminator
- line-continuation sequence
- underscores [Visual Basic], in code
- statements [Visual Basic], line continuation in
- line breaks [Visual Basic], in code
- line-continuation character [Visual Basic]
- Visual Basic code, line continuation in
- statements [Visual Basic], line breaks in
ms.assetid: dea01dad-a8ac-484a-bb3a-8c45a1b1eccc
ms.openlocfilehash: 6bca3d62cb3e886ee08b9169d63d4c3a38247f3f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33651018"
---
# <a name="how-to-break-and-combine-statements-in-code-visual-basic"></a>Procedura: Interrompere e combinare istruzioni nel codice (Visual Basic)
Quando si scrive codice, è possibile creare in alcuni casi istruzioni molto lunghe che richiedono uno scorrimento orizzontale nell'Editor di codice. Anche se ciò non influiscono sulla modalità di esecuzione del codice, rende difficile per se stessi o altri utenti leggere il codice come appare sul monitor. In questi casi, è consigliabile suddividere una lunga istruzione in più righe.  
  
### <a name="to-break-a-single-statement-into-multiple-lines"></a>Per suddividere una singola istruzione in più righe  
  
-   Utilizzare il carattere di continuazione di riga, ovvero un carattere di sottolineatura (`_`), nel punto in cui si desidera interrompere la riga. Il carattere di continuazione di riga deve essere preceduto da uno spazio e seguito da un terminatore di riga (ritorno a capo).  
  
    > [!NOTE]
    >  In alcuni casi, se si omette il carattere di continuazione di riga, il compilatore Visual Basic in modo implicito continuerà l'istruzione nella riga successiva del codice. Per un elenco di elementi della sintassi per il quale è possibile omettere il carattere di continuazione di riga, vedere "Continuazione di riga implicita" in [istruzioni](../../../visual-basic/programming-guide/language-features/statements.md).  
  
     Nell'esempio seguente, l'istruzione viene suddiviso in quattro linee con caratteri di continuazione di riga che terminano tutte tranne l'ultima riga.  
  
     [!code-vb[VbVbcnConventions#20](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/how-to-break-and-combine-statements-in-code_1.vb)]  
  
     Utilizzo di questa sequenza rende il codice più facile la lettura stampati sia online e quando.  
  
     Il carattere di continuazione di riga deve essere l'ultimo carattere su una riga. È possibile seguire in modo diverso nella stessa riga.  
  
     Esistono alcune limitazioni riguardo in cui è possibile utilizzare il carattere di continuazione di riga; ad esempio, è possibile utilizzare all'interno di un nome dell'argomento. È possibile interrompere un elenco di argomenti con il carattere di continuazione di riga, ma i singoli nomi degli argomenti devono rimanere invariati.  
  
     È possibile continuare un commento con un carattere di continuazione di riga. Il compilatore non esamina i caratteri in un commento per un significato speciale. Per commenti su più righe, ripetere il simbolo di commento (`'`) per ogni riga.  
  
 Anche se il metodo consigliato consiste nell'inserire ogni istruzione su una riga distinta, Visual Basic consente inoltre di inserire più istruzioni sulla stessa riga.  
  
### <a name="to-place-multiple-statements-on-the-same-line"></a>Per inserire più istruzioni sulla stessa riga  
  
-   Separare le istruzioni con due punti (`:`), come nell'esempio seguente.  
  
     [!code-vb[VbVbcnConventions#10](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/how-to-break-and-combine-statements-in-code_2.vb)]  
  
## <a name="see-also"></a>Vedere anche  
 [Struttura del programma e convenzioni di scrittura del codice](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md)  
 [Istruzioni](../../../visual-basic/programming-guide/language-features/statements.md)
