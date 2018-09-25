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
ms.openlocfilehash: fe200add4e29fe4bbe0fdf335dcd94107b8ff1eb
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/25/2018
ms.locfileid: "47113569"
---
# <a name="return-statement-visual-basic"></a>Istruzione Return (Visual Basic)
Restituisce il controllo al codice che ha chiamato un' `Function`, `Sub`, `Get`, `Set`, o `Operator` procedure.  
  
## <a name="syntax"></a>Sintassi  
  
```  
Return  
-or-  
Return expression  
```  
  
## <a name="part"></a>Parte  
 `expression`  
 Obbligatorio in un `Function`, `Get`, o `Operator` procedure. Espressione che rappresenta il valore deve essere restituito al codice chiamante.  
  
## <a name="remarks"></a>Note  
 In un `Sub` o `Set` procedure, il `Return` istruzione è equivalente a un `Exit Sub` o `Exit Property` istruzione, e `expression` non deve essere specificato.  
  
 In un `Function`, `Get`, o `Operator` routine, il `Return` istruzione deve includere `expression`, e `expression` deve restituire un tipo di dati che è convertibile nel tipo restituito della procedura. In un `Function` oppure `Get` procedura, è l'alternativa di assegnazione di un'espressione per il nome della routine come il valore restituito e quindi eseguendo un `Exit Function` o `Exit Property` istruzione. In un' `Operator` procedure, è necessario usare `Return expression`.  
  
 È possibile includere un numero `Return` le istruzioni nel modo appropriato per la stessa procedura.  
  
> [!NOTE]
>  Il codice in un `Finally` blocco viene eseguito dopo un `Return` istruzione in un `Try` oppure `Catch` blocco viene rilevata, ma prima che `Return` istruzione viene eseguita. Oggetto `Return` istruzione non può essere incluso in un `Finally` blocco.  
  
## <a name="example"></a>Esempio  
 L'esempio seguente usa il `Return` istruzione più volte per tornare al codice chiamante quando la procedura non è necessario eseguire altre operazioni.  
  
 [!code-vb[VbVbalrStatements#53](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/return-statement_1.vb)]  
  
## <a name="see-also"></a>Vedere anche  
 [Istruzione Function](../../../visual-basic/language-reference/statements/function-statement.md)  
 [Istruzione Sub](../../../visual-basic/language-reference/statements/sub-statement.md)  
 [Istruzione Get](../../../visual-basic/language-reference/statements/get-statement.md)  
 [Istruzione Set](../../../visual-basic/language-reference/statements/set-statement.md)  
 [Istruzione Operator](../../../visual-basic/language-reference/statements/operator-statement.md)  
 [Istruzione Property](../../../visual-basic/language-reference/statements/property-statement.md)  
 [Istruzione Exit](../../../visual-basic/language-reference/statements/exit-statement.md)  
 [Istruzione Try...Catch...Finally](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
