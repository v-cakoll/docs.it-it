---
title: 'Procedura: creare una routine (Visual Basic)'
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- procedures [Visual Basic], defining
- Visual Basic code, procedures
- Visual Basic code, reusing
- procedure declarations
- procedures [Visual Basic], about procedures
ms.assetid: 4f779247-0b50-47e8-9e5c-ab5cf39ac0d2
caps.latest.revision: 27
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 5e23358e26dbc993b0f9290a8491a3c66717b4c6
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-create-a-procedure-visual-basic"></a>Procedura: creare una routine (Visual Basic)
Una routine racchiusa tra un'istruzione di dichiarazione iniziale (`Sub` o `Function`) e un'istruzione di dichiarazione finale (`End Sub` o `End Function`). Codice di procedura è compresa tra queste istruzioni.  
  
 Una routine non può contenere un'altra routine, pertanto le relative istruzioni iniziale e finale devono essere all'esterno di qualsiasi altra routine.  
  
 Se si dispone di codice che esegue la stessa attività in posizioni diverse, è possibile scrivere l'attività una sola volta come una stored procedure e quindi chiamare da diverse posizioni nel codice.  
  
### <a name="to-create-a-procedure-that-does-not-return-a-value"></a>Per creare una routine che non restituisce un valore  
  
1.  All'esterno di qualsiasi altra routine, utilizzare un `Sub` istruzione, seguito da un `End Sub` istruzione.  
  
2.  Nel `Sub` istruzione, seguire la `Sub` (parola chiave) con il nome della routine, quindi l'elenco di parametri tra parentesi.  
  
3.  Inserire istruzioni di codice della stored procedure tra il `Sub` e `End Sub` istruzioni.  
  
### <a name="to-create-a-procedure-that-returns-a-value"></a>Per creare una stored procedure che restituisce un valore  
  
1.  All'esterno di qualsiasi altra routine, utilizzare un `Function` istruzione, seguito da un `End Function` istruzione.  
  
2.  Nel `Function` istruzione, seguire la `Function` (parola chiave) con il nome della routine, quindi l'elenco di parametri tra parentesi e quindi un `As` clausola che specifica il tipo di dati del valore restituito.  
  
3.  Inserire istruzioni di codice della stored procedure tra il `Function` e `End Function` istruzioni.  
  
4.  Utilizzare un `Return` istruzione per restituire il valore al codice chiamante.  
  
### <a name="to-connect-your-new-procedure-with-the-old-repetitive-blocks-of-code"></a>Per collegare la nuova routine con i blocchi di codice precedenti ricorrenti  
  
1.  Verificare che si definisce la nuova procedura in una posizione in cui il vecchio codice ha accesso a esso.  
  
2.  Nel blocco di codice precedente, ricorrenti, sostituire le istruzioni che eseguono attività ricorrenti con una singola istruzione che chiama il `Sub` o `Function` stored procedure.  
  
3.  Se la routine è un `Function` che restituisce un valore, verificare che l'istruzione di chiamata esegua un'azione con il valore restituito, ad esempio archiviare i dati in una variabile, in caso contrario il valore andranno perso.  
  
## <a name="example"></a>Esempio  
 Le operazioni seguenti `Function` procedure calcola il lato più lungo, ovvero l'ipotenusa, di un triangolo rettangolo, in base ai valori per i due lati.  
  
 [!code-vb[VbVbcnProcedures#1](./codesnippet/VisualBasic/how-to-create-a-procedure_1.vb)]  
  
## <a name="see-also"></a>Vedere anche

 [Routine](./index.md)  
 [Routine Sub](./sub-procedures.md)  
 [Routine Function](./function-procedures.md)  
 [Routine Property](./property-procedures.md)  
 [Routine di operatore](./operator-procedures.md)  
 [Parametri e argomenti delle routine](./procedure-parameters-and-arguments.md)  
 [Routine ricorsive](./recursive-procedures.md)  
 [Overload della routine](./procedure-overloading.md)  
 [Oggetti e classi](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)  
 [Programmazione orientata a oggetti (Visual Basic)](../../concepts/object-oriented-programming.md)  
