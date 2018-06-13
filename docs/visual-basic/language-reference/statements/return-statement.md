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
ms.openlocfilehash: 2f614045be1b91b9c747d961cdefd526ba1bab98
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33603522"
---
# <a name="return-statement-visual-basic"></a>Istruzione Return (Visual Basic)
Restituisce il controllo al codice che ha chiamato un `Function`, `Sub`, `Get`, `Set`, o `Operator` stored procedure.  
  
## <a name="syntax"></a>Sintassi  
  
```  
Return  
-or-  
Return expression  
```  
  
## <a name="part"></a>Parte  
 `expression`  
 Obbligatorio in un `Function`, `Get`, o `Operator` stored procedure. Espressione che rappresenta il valore deve essere restituito al codice chiamante.  
  
## <a name="remarks"></a>Note  
 In un `Sub` o `Set` procedure, il `Return` equivale all'istruzione un' `Exit Sub` o `Exit Property` istruzione e `expression` non è necessario specificare.  
  
 In un `Function`, `Get`, o `Operator` procedure, il `Return` deve includere l'istruzione `expression`, e `expression` deve restituire un tipo di dati che è convertibile nel tipo restituito della procedura. In un `Function` o `Get` procedura, è anche possibile assegnare un'espressione al nome della procedura da utilizzare come valore restituito e quindi eseguendo un `Exit Function` o `Exit Property` istruzione. In un `Operator` procedura, è necessario utilizzare `Return``expression`.  
  
 È possibile includere un numero `Return` istruzioni appropriate nella stessa routine.  
  
> [!NOTE]
>  Il codice in un `Finally` blocco viene eseguito dopo un `Return` istruzione in un `Try` o `Catch` blocco viene rilevata, ma prima che `Return` dell'istruzione. Oggetto `Return` istruzione non può essere incluso un `Finally` blocco.  
  
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
