---
title: Operatore AddressOf (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- AddressOf
- vb.AddressOf
helpviewer_keywords:
- AddressOf operator [Visual Basic]
- addresses, passing to API procedures
ms.assetid: 8105a59d-60d8-4ab5-b221-5899cdfacbf4
ms.openlocfilehash: 7c229c32a3b295b4dbfe50ca2abc60d4ad5f2145
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="addressof-operator-visual-basic"></a>Operatore AddressOf (Visual Basic)
Crea un'istanza di delegato di routine che fa riferimento la procedura specifica.  
  
## <a name="syntax"></a>Sintassi  
  
```  
AddressOf procedurename  
```  
  
## <a name="parts"></a>Parti  
 `procedurename`  
 Obbligatorio. Specifica la procedura per fare riferimento il delegato appena creato.  
  
## <a name="remarks"></a>Note  
 Il `AddressOf` operatore crea un delegato della funzione che fa riferimento alla funzione specificata da `procedurename`. Quando la stored procedure specificata è che un metodo di istanza, quindi il delegato della funzione fa riferimento l'istanza sia il metodo. Quindi, quando viene richiamato il delegato della funzione viene chiamato il metodo specificato dell'istanza specificata.  
  
 Il `AddressOf` operatore può essere usato come operando di un costruttore di delegato o può essere utilizzato in un contesto in cui il tipo del delegato può essere determinato dal compilatore.  
  
## <a name="example"></a>Esempio  
 Questo esempio viene utilizzato il `AddressOf` operatore per designare un delegato per gestire il `Click` evento di un pulsante.  
  
 [!code-vb[VbVbalrDelegates#8](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/addressof-operator_1.vb)]  
  
## <a name="example"></a>Esempio  
 L'esempio seguente usa il `AddressOf` operatore per specificare la funzione di avvio per un thread.  
  
 [!code-vb[VbVbalrDelegates#9](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/addressof-operator_2.vb)]  
  
## <a name="see-also"></a>Vedere anche  
 [Istruzione Declare](../../../visual-basic/language-reference/statements/declare-statement.md)  
 [Istruzione Function](../../../visual-basic/language-reference/statements/function-statement.md)  
 [Istruzione Sub](../../../visual-basic/language-reference/statements/sub-statement.md)  
 [Delegati](../../../visual-basic/programming-guide/language-features/delegates/index.md)
