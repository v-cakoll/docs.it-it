---
title: 'Procedura: restituire un valore da una routine'
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic code, procedures
- procedures [Visual Basic], returning from
- procedures [Visual Basic], returning a value
ms.assetid: 4bcc4724-2b4e-4df8-9b4b-16054607f87d
ms.openlocfilehash: 1371e4ed0ff28f9caf56eabf2a1bb9290edbe75c
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74346033"
---
# <a name="how-to-return-a-value-from-a-procedure-visual-basic"></a>Procedura: restituire un valore da una routine (Visual Basic)
Una routine `Function` restituisce un valore al codice chiamante eseguendo un'istruzione `Return` o rilevando un'istruzione `Exit Function` o `End Function`.  
  
### <a name="to-return-a-value-using-the-return-statement"></a>Per restituire un valore utilizzando l'istruzione return  
  
1. Inserire un'istruzione `Return` nel punto in cui è stata completata l'attività della stored procedure.  
  
2. Seguire la parola chiave `Return` con un'espressione che restituisce il valore che si vuole restituire al codice chiamante.  
  
3. Una routine può includere più di un'istruzione `Return`.  
  
     Con la seguente procedura `Function` viene calcolato il lato più lungo, o ipotenusa, di un triangolo rettangolo, che viene quindi restituito al codice chiamante.  
  
     [!code-vb[VbVbcnProcedures#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#1)]  
  
     Nell'esempio seguente viene illustrata una tipica chiamata a `hypotenuse`, che archivia il valore restituito.  
  
     [!code-vb[VbVbcnProcedures#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#6)]  
  
### <a name="to-return-a-value-using-exit-function-or-end-function"></a>Per restituire un valore utilizzando la funzione Exit o end  
  
1. In almeno una posizione nella procedura `Function` assegnare un valore al nome della stored procedure.  
  
2. Quando si esegue un'istruzione `Exit Function` o `End Function`, Visual Basic restituisce il valore assegnato più di recente al nome della stored procedure.  
  
3. Una routine può includere più di un'istruzione `Exit Function` ed è possibile combinare istruzioni `Return` e `Exit Function` nella stessa routine.  
  
4. In una procedura `Function` è possibile disporre di una sola istruzione `End Function`.  
  
     Per ulteriori informazioni e un esempio, vedere "valore restituito" nell' [istruzione Function](../../../../visual-basic/language-reference/statements/function-statement.md).  
  
## <a name="see-also"></a>Vedere anche

- [Routine](./index.md)
- [Routine Sub](./sub-procedures.md)
- [Routine Property](./property-procedures.md)
- [Routine di operatore](./operator-procedures.md)
- [Parametri e argomenti delle routine](./procedure-parameters-and-arguments.md)
- [Istruzione Function](../../../../visual-basic/language-reference/statements/function-statement.md)
- [Istruzione Return](../../../../visual-basic/language-reference/statements/return-statement.md)
- [Procedura: Creare una routine che restituisce un valore](./how-to-create-a-procedure-that-returns-a-value.md)
- [Procedura: Chiamare una routine che restituisce un valore](./how-to-call-a-procedure-that-returns-a-value.md)
