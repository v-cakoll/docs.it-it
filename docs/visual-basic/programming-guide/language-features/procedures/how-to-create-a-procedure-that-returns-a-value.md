---
title: 'Procedura: Creare una routine che restituisce un valore (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], defining
- Visual Basic code, procedures
- procedures [Visual Basic], returning a value
ms.assetid: 8ee19f95-a9ef-4033-963b-d224dca207c4
ms.openlocfilehash: 115c1df4bd49d5848d72c4cbd0242a49a12740c7
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61863727"
---
# <a name="how-to-create-a-procedure-that-returns-a-value-visual-basic"></a>Procedura: Creare una routine che restituisce un valore (Visual Basic)
Si utilizza un `Function` procedure per restituire un valore al codice chiamante.  
  
### <a name="to-create-a-procedure-that-returns-a-value"></a>Per creare una stored procedure che restituisce un valore  
  
1. Di fuori di qualsiasi altra routine, usare una `Function` istruzione, seguito da un `End Function` istruzione.  
  
2. Nel `Function` istruzione, seguire la `Function` parola chiave con il nome della routine e quindi l'elenco dei parametri tra parentesi.  
  
3. Dopo le parentesi un `As` clausola per specificare il tipo di dati del valore restituito.  
  
4. È possibile inserire istruzioni di codice della stored procedure tra il `Function` e `End Function` istruzioni.  
  
5. Usare un `Return` istruzione per restituire il valore al codice chiamante.  
  
     Nell'esempio `Function` procedure calcola il lato lungo, ovvero l'ipotenusa di un triangolo rettangolo, in base ai valori degli altri due lati.  
  
     [!code-vb[VbVbcnProcedures#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#1)]  
  
     Nell'esempio seguente viene illustrata una tipica chiamata alla `hypotenuse`.  
  
     [!code-vb[VbVbcnProcedures#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#6)]  
  
## <a name="see-also"></a>Vedere anche

- [Routine](./index.md)
- [Routine Sub](./sub-procedures.md)
- [Routine Property](./property-procedures.md)
- [Routine di operatore](./operator-procedures.md)
- [Parametri e argomenti delle routine](./procedure-parameters-and-arguments.md)
- [Istruzione Function](../../../../visual-basic/language-reference/statements/function-statement.md)
- [Procedura: Restituisce il valore da una routine](./how-to-return-a-value-from-a-procedure.md)
- [Procedura: Chiamare una routine che restituisce un valore](./how-to-call-a-procedure-that-returns-a-value.md)
