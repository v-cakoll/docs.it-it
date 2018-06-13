---
title: 'Procedura: restituire un valore da una routine (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic code, procedures
- procedures [Visual Basic], returning from
- procedures [Visual Basic], returning a value
ms.assetid: 4bcc4724-2b4e-4df8-9b4b-16054607f87d
ms.openlocfilehash: 62e8a52e488247d4dfcde2a560920447abe1c182
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33651834"
---
# <a name="how-to-return-a-value-from-a-procedure-visual-basic"></a>Procedura: restituire un valore da una routine (Visual Basic)
Oggetto `Function` routine restituisce un valore al codice chiamante tramite l'esecuzione di un `Return` istruzione o l'individuazione un `Exit Function` o `End Function` istruzione.  
  
### <a name="to-return-a-value-using-the-return-statement"></a>Per restituire un valore utilizzando l'istruzione Return  
  
1.  Inserire un `Return` istruzione nel punto in cui viene completata l'attività della routine.  
  
2.  Seguire il `Return` (parola chiave) con un'espressione che restituisce il valore da restituire al codice chiamante.  
  
3.  Una routine può includere più di un'istruzione `Return`.  
  
     Le operazioni seguenti `Function` procedure calcola il lato più lungo, ovvero l'ipotenusa, di un triangolo rettangolo e lo restituisce al codice chiamante.  
  
     [!code-vb[VbVbcnProcedures#1](./codesnippet/VisualBasic/how-to-return-a-value-from-a-procedure_1.vb)]  
  
     Nell'esempio seguente viene illustrata una tipica chiamata a `hypotenuse`, che archivia il valore restituito.  
  
     [!code-vb[VbVbcnProcedures#6](./codesnippet/VisualBasic/how-to-return-a-value-from-a-procedure_2.vb)]  
  
### <a name="to-return-a-value-using-exit-function-or-end-function"></a>Per restituire un valore utilizzando Exit Function o End Function  
  
1.  In almeno un punto di `Function` procedure, assegnare un valore al nome della stored procedure.  
  
2.  Quando si esegue un' `Exit Function` o `End Function` istruzione, Visual Basic restituisce l'ultimo valore assegnato al nome della stored procedure.  
  
3.  Una routine può includere più di un'istruzione `Exit Function` ed è possibile combinare istruzioni `Return` e `Exit Function` nella stessa routine.  
  
4.  Si può avere un solo `End Function` istruzione in un `Function` stored procedure.  
  
     Per ulteriori informazioni e un esempio, vedere "Valore restituito" in [istruzione Function](../../../../visual-basic/language-reference/statements/function-statement.md).  
  
## <a name="see-also"></a>Vedere anche  
 [Routine](./index.md)  
 [Routine Sub](./sub-procedures.md)  
 [Routine Property](./property-procedures.md)  
 [Routine di operatore](./operator-procedures.md)  
 [Parametri e argomenti delle routine](./procedure-parameters-and-arguments.md)  
 [Istruzione Function](../../../../visual-basic/language-reference/statements/function-statement.md)  
 [Istruzione Return](../../../../visual-basic/language-reference/statements/return-statement.md)  
 [Procedura: Creare una routine che restituisce un valore](./how-to-create-a-procedure-that-returns-a-value.md)  
 [Procedura: Chiamare una routine che restituisce un valore](./how-to-call-a-procedure-that-returns-a-value.md)
