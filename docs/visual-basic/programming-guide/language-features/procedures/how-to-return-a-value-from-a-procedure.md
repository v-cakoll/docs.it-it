---
title: 'Procedura: restituire un valore da una routine'
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic code, procedures
- procedures [Visual Basic], returning from
- procedures [Visual Basic], returning a value
ms.assetid: 4bcc4724-2b4e-4df8-9b4b-16054607f87d
ms.openlocfilehash: 917e52b711645fbf94a132216a3fa90b0dfc15b3
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84414324"
---
# <a name="how-to-return-a-value-from-a-procedure-visual-basic"></a>Procedura: restituire un valore da una routine (Visual Basic)
Una `Function` routine restituisce un valore al codice chiamante eseguendo un' `Return` istruzione o con un' `Exit Function` `End Function` istruzione o.  
  
### <a name="to-return-a-value-using-the-return-statement"></a>Per restituire un valore utilizzando l'istruzione return  
  
1. Inserire un' `Return` istruzione nel punto in cui è stata completata l'attività della stored procedure.  
  
2. Seguire la `Return` parola chiave con un'espressione che restituisce il valore che si vuole restituire al codice chiamante.  
  
3. Una routine può includere più di un'istruzione `Return`.  
  
     Nella `Function` procedura seguente viene calcolato il lato più lungo, o ipotenusa, di un triangolo rettangolo, che viene quindi restituito al codice chiamante.  
  
     [!code-vb[VbVbcnProcedures#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#1)]  
  
     Nell'esempio seguente viene illustrata una tipica chiamata a `hypotenuse` che archivia il valore restituito.  
  
     [!code-vb[VbVbcnProcedures#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#6)]  
  
### <a name="to-return-a-value-using-exit-function-or-end-function"></a>Per restituire un valore utilizzando la funzione Exit o end  
  
1. In almeno una posizione nella `Function` Procedura assegnare un valore al nome della stored procedure.  
  
2. Quando si esegue un' `Exit Function` `End Function` istruzione o, Visual Basic restituisce il valore assegnato più di recente al nome della stored procedure.  
  
3. Una routine può includere più di un'istruzione `Exit Function` ed è possibile combinare istruzioni `Return` e `Exit Function` nella stessa routine.  
  
4. In una procedura è possibile disporre di una sola `End Function` istruzione `Function` .  
  
     Per ulteriori informazioni e un esempio, vedere "valore restituito" nell' [istruzione Function](../../../language-reference/statements/function-statement.md).  
  
## <a name="see-also"></a>Vedere anche

- [Procedure](./index.md)
- [Routine Sub](./sub-procedures.md)
- [Routine Property](./property-procedures.md)
- [Routine di operatore](./operator-procedures.md)
- [Parametri e argomenti delle routine](./procedure-parameters-and-arguments.md)
- [Istruzione Function](../../../language-reference/statements/function-statement.md)
- [Return (istruzione)](../../../language-reference/statements/return-statement.md)
- [Procedura: creare una routine che restituisce un valore](./how-to-create-a-procedure-that-returns-a-value.md)
- [Procedura: chiamare una routine che restituisce un valore](./how-to-call-a-procedure-that-returns-a-value.md)
