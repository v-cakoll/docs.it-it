---
title: 'Procedura: Creare una routine (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], defining
- Visual Basic code, procedures
- Visual Basic code, reusing
- procedure declarations
- procedures [Visual Basic], about procedures
ms.assetid: 4f779247-0b50-47e8-9e5c-ab5cf39ac0d2
ms.openlocfilehash: 06fed04a0ebe7a0b3111a94308d15d01bcf47c1e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54636534"
---
# <a name="how-to-create-a-procedure-visual-basic"></a>Procedura: Creare una routine (Visual Basic)
Una routine racchiusa tra un'istruzione di dichiarazione iniziale (`Sub` oppure `Function`) e un'istruzione di dichiarazione finale (`End Sub` o `End Function`). Tutto il codice della routine è compresa tra queste istruzioni.  
  
 Una routine non può contenere un'altra routine, in modo che le relative istruzioni iniziale e finale devono essere all'esterno di qualsiasi altra routine.  
  
 Se si dispone di codice che esegue la stessa attività in posizioni diverse, è possibile scrivere attività una sola volta come una procedura e chiamarlo successivamente da diverse posizioni nel codice.  
  
### <a name="to-create-a-procedure-that-does-not-return-a-value"></a>Per creare una routine che non restituisce un valore  
  
1.  Di fuori di qualsiasi altra routine, usare una `Sub` istruzione, seguito da un `End Sub` istruzione.  
  
2.  Nel `Sub` istruzione, seguire la `Sub` parola chiave con il nome della routine, quindi l'elenco di parametri tra parentesi.  
  
3.  È possibile inserire istruzioni di codice della stored procedure tra il `Sub` e `End Sub` istruzioni.  
  
### <a name="to-create-a-procedure-that-returns-a-value"></a>Per creare una stored procedure che restituisce un valore  
  
1.  Di fuori di qualsiasi altra routine, usare una `Function` istruzione, seguito da un `End Function` istruzione.  
  
2.  Nel `Function` istruzione, seguire la `Function` parola chiave con il nome della routine, quindi l'elenco di parametri tra parentesi e quindi un `As` clausola che specifica il tipo di dati del valore restituito.  
  
3.  È possibile inserire istruzioni di codice della stored procedure tra il `Function` e `End Function` istruzioni.  
  
4.  Usare un `Return` istruzione per restituire il valore al codice chiamante.  
  
### <a name="to-connect-your-new-procedure-with-the-old-repetitive-blocks-of-code"></a>Per collegare la nuova routine con i blocchi di codice precedenti ricorrenti  
  
1.  Assicurarsi che si definisce la nuova routine in una posizione in cui il vecchio codice possa accedervi.  
  
2.  Nel blocco di codice precedente e ripetitive, sostituire le istruzioni che eseguono le attività ripetitive con una singola istruzione che chiama il `Sub` o `Function` procedure.  
  
3.  Se la routine è una `Function` che restituisce un valore, assicurarsi che l'istruzione chiama esegua un'azione con il valore restituito, ad esempio archiviare i dati in una variabile, in caso contrario il valore andranno perso.  
  
## <a name="example"></a>Esempio  
 Nell'esempio `Function` procedure calcola il lato lungo, ovvero l'ipotenusa di un triangolo rettangolo, in base ai valori degli altri due lati.  
  
 [!code-vb[VbVbcnProcedures#1](./codesnippet/VisualBasic/how-to-create-a-procedure_1.vb)]  
  
## <a name="see-also"></a>Vedere anche

- [Routine](./index.md)
- [Routine Sub](./sub-procedures.md)
- [Routine Function](./function-procedures.md)
- [Routine Property](./property-procedures.md)
- [Routine di operatore](./operator-procedures.md)
- [Parametri e argomenti delle routine](./procedure-parameters-and-arguments.md)
- [Routine ricorsive](./recursive-procedures.md)
- [Overload della routine](./procedure-overloading.md)
- [Oggetti e classi](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
- [Programmazione orientata a oggetti (Visual Basic)](../../concepts/object-oriented-programming.md)
