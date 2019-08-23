---
title: Istruzione Return (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Return
helpviewer_keywords:
- Return statement [Visual Basic], syntax
- control flow [Visual Basic], returning control to expressions
- Return statement [Visual Basic]
- expressions [Visual Basic], returning control to
ms.assetid: ac86e7f0-5a67-42c3-9834-0e0381efa3ec
ms.openlocfilehash: af49ea95d7f9d01072190ac3ccf6ba2f1041347e
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69957669"
---
# <a name="return-statement-visual-basic"></a>Istruzione Return (Visual Basic)
Restituisce il controllo al codice che ha chiamato `Function`una `Sub`routine `Get`, `Set`,, `Operator` o.  
  
## <a name="syntax"></a>Sintassi  
  
```  
Return  
-or-  
Return expression  
```  
  
## <a name="part"></a>Parte  
 `expression`  
 Obbligatorio in una `Function`procedura `Get`, o `Operator` . Espressione che rappresenta il valore da restituire al codice chiamante.  
  
## <a name="remarks"></a>Note  
 In una `Sub` routine `Set` o l' `Return` istruzione è equivalente a un' `Exit Sub` istruzione o `Exit Property` e `expression` non deve essere fornita.  
  
 In una `Function`routine `Get`, o `Operator` , l' `Return` istruzione deve includere `expression`e `expression` deve restituire un tipo di dati convertibile nel tipo restituito della routine. In una `Function` routine `Get` o è inoltre possibile assegnare un'espressione al nome della stored procedure per fungere da valore restituito e quindi eseguire un' `Exit Function` istruzione o `Exit Property` . In una `Operator` procedura è necessario utilizzare `Return expression`.  
  
 È possibile includere `Return` tutte le istruzioni appropriate nella stessa procedura.  
  
> [!NOTE]
> Il codice in un `Finally` blocco viene eseguito dopo `Return` che `Return` un'istruzione `Try` in `Catch` un blocco o viene rilevata, ma prima dell'esecuzione dell'istruzione. Un' `Return` istruzione non può essere inclusa in `Finally` un blocco.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente l' `Return` istruzione viene utilizzata più volte per tornare al codice chiamante quando la procedura non deve eseguire altre operazioni.  
  
 [!code-vb[VbVbalrStatements#53](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#53)]  
  
## <a name="see-also"></a>Vedere anche

- [Istruzione Function](../../../visual-basic/language-reference/statements/function-statement.md)
- [Istruzione Sub](../../../visual-basic/language-reference/statements/sub-statement.md)
- [Istruzione Get](../../../visual-basic/language-reference/statements/get-statement.md)
- [Istruzione Set](../../../visual-basic/language-reference/statements/set-statement.md)
- [Istruzione Operator](../../../visual-basic/language-reference/statements/operator-statement.md)
- [Istruzione Property](../../../visual-basic/language-reference/statements/property-statement.md)
- [Istruzione Exit](../../../visual-basic/language-reference/statements/exit-statement.md)
- [Istruzione Try...Catch...Finally](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
