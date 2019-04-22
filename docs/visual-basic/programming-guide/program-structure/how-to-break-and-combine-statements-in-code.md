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
ms.openlocfilehash: 680084c39b90d4f664f48559fa21388ce192d999
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "58837741"
---
# <a name="how-to-break-and-combine-statements-in-code-visual-basic"></a>Procedura: Interrompere e combinare istruzioni nel codice (Visual Basic)
Quando si scrive codice, è possibile creare in alcuni casi le istruzioni di lunga durate che richiedono uno scorrimento orizzontale nell'Editor del codice. Anche se ciò non influiscono sulla modalità di esecuzione del codice, rende difficile per te o per altri utenti a leggere il codice visualizzato sul monitor. In questi casi, è necessario considerare suddividendo la singola istruzione lunga in più righe.  
  
### <a name="to-break-a-single-statement-into-multiple-lines"></a>Per suddividere una singola istruzione in più righe  
  
-   Usare il carattere di continuazione di riga, ovvero un carattere di sottolineatura (`_`), nel punto in cui si desidera interrompere la riga. Il carattere di continuazione di riga deve essere preceduto da uno spazio e seguito da un terminatore di riga (ritorno a capo).  
  
    > [!NOTE]
    >  In alcuni casi, se si omette il carattere di continuazione di riga, il compilatore Visual Basic in modo implicito continuerà l'istruzione nella riga successiva del codice. Per un elenco di elementi della sintassi per il quale è possibile omettere il carattere di continuazione di riga, vedere "Continuazione di riga implicita" nella [istruzioni](../../../visual-basic/programming-guide/language-features/statements.md).  
  
     Nell'esempio seguente, l'istruzione viene suddivisa in quattro righe con terminazione di tutti i caratteri di continuazione di riga, ma l'ultima riga.  
  
     [!code-vb[VbVbcnConventions#20](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnConventions/VB/Class1.vb#20)]  
  
     Utilizzo di questa sequenza rende il codice più leggibile, stampati sia online e quando.  
  
     Il carattere di continuazione di riga deve essere l'ultimo carattere in una riga. È non è possibile seguirla con altre operazioni sulla stessa riga.  
  
     Esistono alcune limitazioni riguardo in cui è possibile usare il carattere di continuazione di riga. è ad esempio, non è possibile usarlo all'interno di un nome di argomento. È possibile interrompere un elenco di argomenti con il carattere di continuazione di riga, ma i singoli tipi degli argomenti devono rimanere invariati.  
  
     È possibile proseguire un commento con un carattere di continuazione di riga. Il compilatore non esamina i caratteri in un commento per un significato speciale. Per commenti su più righe, ripetere il simbolo di commento (`'`) per ogni riga.  
  
 Anche se il metodo consigliato consiste nell'inserire ogni istruzione in una riga distinta, Visual Basic consente inoltre di inserire istruzioni di più sulla stessa riga.  
  
### <a name="to-place-multiple-statements-on-the-same-line"></a>Per inserire più istruzioni sulla stessa riga  
  
-   Separare le istruzioni con un carattere due punti (`:`), come illustrato nell'esempio seguente.  
  
     [!code-vb[VbVbcnConventions#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnConventions/VB/Class1.vb#10)]  
  
## <a name="see-also"></a>Vedere anche

- [Struttura del programma e convenzioni di scrittura del codice](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md)
- [Istruzioni](../../../visual-basic/programming-guide/language-features/statements.md)
