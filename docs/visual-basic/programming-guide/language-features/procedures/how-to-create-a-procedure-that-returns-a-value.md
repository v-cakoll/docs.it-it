---
title: 'Procedura: creare una routine che restituisce un valore'
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], defining
- Visual Basic code, procedures
- procedures [Visual Basic], returning a value
ms.assetid: 8ee19f95-a9ef-4033-963b-d224dca207c4
ms.openlocfilehash: 2655aba6ce37be831d8dd4202ffd484cfd3fd5ef
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84388349"
---
# <a name="how-to-create-a-procedure-that-returns-a-value-visual-basic"></a>Procedura: creare una routine che restituisce un valore (Visual Basic)
Usare una `Function` procedura per restituire un valore al codice chiamante.  
  
### <a name="to-create-a-procedure-that-returns-a-value"></a>Per creare una routine che restituisce un valore  
  
1. All'esterno di qualsiasi altra procedura, utilizzare un' `Function` istruzione, seguita da un' `End Function` istruzione.  
  
2. Nell' `Function` istruzione seguire la `Function` parola chiave con il nome della stored procedure, quindi l'elenco di parametri tra parentesi.  
  
3. Seguire le parentesi con una `As` clausola per specificare il tipo di dati del valore restituito.  
  
4. Inserire le istruzioni di codice della stored procedure tra le `Function` `End Function` istruzioni e.  
  
5. Utilizzare un' `Return` istruzione per restituire il valore al codice chiamante.  
  
     La `Function` procedura seguente calcola il lato più lungo, o ipotenusa, di un triangolo rettangolo, dati i valori per gli altri due lati.  
  
     [!code-vb[VbVbcnProcedures#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#1)]  
  
     Nell'esempio seguente viene illustrata una tipica chiamata a `hypotenuse` .  
  
     [!code-vb[VbVbcnProcedures#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#6)]  
  
## <a name="see-also"></a>Vedere anche

- [Procedure](./index.md)
- [Routine Sub](./sub-procedures.md)
- [Routine Property](./property-procedures.md)
- [Routine di operatore](./operator-procedures.md)
- [Parametri e argomenti delle routine](./procedure-parameters-and-arguments.md)
- [Istruzione Function](../../../language-reference/statements/function-statement.md)
- [Procedura: restituire un valore da una routine](./how-to-return-a-value-from-a-procedure.md)
- [Procedura: chiamare una routine che restituisce un valore](./how-to-call-a-procedure-that-returns-a-value.md)
