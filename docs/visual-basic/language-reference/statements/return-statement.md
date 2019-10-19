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
ms.openlocfilehash: edaaf09f5a984344f7e89c9da988c529774934e9
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2019
ms.locfileid: "72583262"
---
# <a name="return-statement-visual-basic"></a>Istruzione Return (Visual Basic)
Restituisce il controllo al codice che ha chiamato una procedura di `Function`, `Sub`, `Get`, `Set` o `Operator`.  
  
## <a name="syntax"></a>Sintassi  
  
```vb  
Return  
' -or-  
Return expression  
```  
  
## <a name="part"></a>Parte  
 `expression`  
 Obbligatorio in una procedura `Function`, `Get` o `Operator`. Espressione che rappresenta il valore da restituire al codice chiamante.  
  
## <a name="remarks"></a>Note  
 In una procedura `Sub` o `Set`, l'istruzione `Return` è equivalente a un'istruzione `Exit Sub` o `Exit Property` e non è necessario fornire `expression`.  
  
 In una procedura `Function`, `Get` o `Operator`, l'istruzione `Return` deve includere `expression` e `expression` deve restituire un tipo di dati convertibile nel tipo restituito della stored procedure. In una procedura `Function` o `Get` è inoltre possibile assegnare un'espressione al nome della stored procedure per fungere da valore restituito, quindi eseguire un'istruzione `Exit Function` o `Exit Property`. In una procedura `Operator` è necessario usare `Return expression`.  
  
 È possibile includere il numero di istruzioni `Return` appropriate nella stessa procedura.  
  
> [!NOTE]
> Il codice in un blocco `Finally` viene eseguito dopo che è stata rilevata un'istruzione `Return` in un blocco `Try` o `Catch`, ma prima che venga eseguita l'istruzione `Return`. Non è possibile includere un'istruzione `Return` in un blocco di `Finally`.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene utilizzata l'istruzione `Return` più volte per tornare al codice chiamante quando la procedura non deve eseguire altre operazioni.  
  
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
