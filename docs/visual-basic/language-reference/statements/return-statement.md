---
title: Istruzione Return
ms.date: 07/20/2015
f1_keywords:
- vb.Return
helpviewer_keywords:
- Return statement [Visual Basic], syntax
- control flow [Visual Basic], returning control to expressions
- Return statement [Visual Basic]
- expressions [Visual Basic], returning control to
ms.assetid: ac86e7f0-5a67-42c3-9834-0e0381efa3ec
ms.openlocfilehash: cdb58e32c30c8e6c1662fb698ac5576c3f71258c
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84404200"
---
# <a name="return-statement-visual-basic"></a>Istruzione Return (Visual Basic)
Restituisce il controllo al codice che ha chiamato `Function` una `Sub` routine,, `Get` , `Set` o `Operator` .  
  
## <a name="syntax"></a>Sintassi  
  
```vb  
Return  
' -or-  
Return expression  
```  
  
## <a name="part"></a>Parte  
 `expression`  
 Obbligatorio in una `Function` `Get` procedura, o `Operator` . Espressione che rappresenta il valore da restituire al codice chiamante.  
  
## <a name="remarks"></a>Commenti  
 In una `Sub` `Set` routine o l' `Return` istruzione è equivalente a un' `Exit Sub` istruzione o `Exit Property` e `expression` non deve essere fornita.  
  
 In una `Function` `Get` routine, o `Operator` , l' `Return` istruzione deve includere `expression` e `expression` deve restituire un tipo di dati convertibile nel tipo restituito della routine. In una `Function` `Get` routine o è inoltre possibile assegnare un'espressione al nome della stored procedure per fungere da valore restituito e quindi eseguire un' `Exit Function` `Exit Property` istruzione o. In una `Operator` procedura è necessario utilizzare `Return expression` .  
  
 È possibile includere tutte `Return` le istruzioni appropriate nella stessa procedura.  
  
> [!NOTE]
> Il codice in un `Finally` blocco viene eseguito dopo `Return` che un'istruzione in un `Try` `Catch` blocco o viene rilevata, ma prima dell' `Return` esecuzione dell'istruzione. Un' `Return` istruzione non può essere inclusa in un `Finally` blocco.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente l'istruzione viene utilizzata `Return` più volte per tornare al codice chiamante quando la procedura non deve eseguire altre operazioni.  
  
 [!code-vb[VbVbalrStatements#53](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#53)]  
  
## <a name="see-also"></a>Vedere anche

- [Istruzione Function](function-statement.md)
- [Istruzione Sub](sub-statement.md)
- [Istruzione Get](get-statement.md)
- [Istruzione set](set-statement.md)
- [Operator Statement](operator-statement.md)
- [Property Statement](property-statement.md)
- [Istruzione Exit](exit-statement.md)
- [Istruzione Try...Catch...Finally](try-catch-finally-statement.md)
