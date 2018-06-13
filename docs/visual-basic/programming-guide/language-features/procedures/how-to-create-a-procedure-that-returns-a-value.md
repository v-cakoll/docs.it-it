---
title: 'Procedura: creare una routine che restituisce un valore (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], defining
- Visual Basic code, procedures
- procedures [Visual Basic], returning a value
ms.assetid: 8ee19f95-a9ef-4033-963b-d224dca207c4
ms.openlocfilehash: 472f55173a4897a23a82812a2b24bf1646c1a6ed
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33648437"
---
# <a name="how-to-create-a-procedure-that-returns-a-value-visual-basic"></a>Procedura: creare una routine che restituisce un valore (Visual Basic)
Si utilizza un `Function` procedure per restituire un valore al codice chiamante.  
  
### <a name="to-create-a-procedure-that-returns-a-value"></a>Per creare una stored procedure che restituisce un valore  
  
1.  All'esterno di qualsiasi altra routine, utilizzare un `Function` istruzione, seguito da un `End Function` istruzione.  
  
2.  Nel `Function` istruzione, seguire la `Function` (parola chiave) con il nome della routine e, quindi l'elenco di parametri tra parentesi.  
  
3.  Dopo le parentesi un `As` clausola per specificare il tipo di dati del valore restituito.  
  
4.  Inserire istruzioni di codice della stored procedure tra il `Function` e `End Function` istruzioni.  
  
5.  Utilizzare un `Return` istruzione per restituire il valore al codice chiamante.  
  
     Le operazioni seguenti `Function` procedure calcola il lato più lungo, ovvero l'ipotenusa, di un triangolo rettangolo, in base ai valori per i due lati.  
  
     [!code-vb[VbVbcnProcedures#1](./codesnippet/VisualBasic/how-to-create-a-procedure-that-returns-a-value_1.vb)]  
  
     Nell'esempio seguente viene illustrata una tipica chiamata a `hypotenuse`.  
  
     [!code-vb[VbVbcnProcedures#6](./codesnippet/VisualBasic/how-to-create-a-procedure-that-returns-a-value_2.vb)]  
  
## <a name="see-also"></a>Vedere anche  
 [Routine](./index.md)  
 [Routine Sub](./sub-procedures.md)  
 [Routine Property](./property-procedures.md)  
 [Routine di operatore](./operator-procedures.md)  
 [Parametri e argomenti delle routine](./procedure-parameters-and-arguments.md)  
 [Istruzione Function](../../../../visual-basic/language-reference/statements/function-statement.md)  
 [Procedura: Restituire un valore da una routine](./how-to-return-a-value-from-a-procedure.md)  
 [Procedura: Chiamare una routine che restituisce un valore](./how-to-call-a-procedure-that-returns-a-value.md)
