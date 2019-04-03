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
ms.openlocfilehash: 9d8515b6d5b0caf3552ed05a7e0cd4a271efaf54
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2019
ms.locfileid: "58830344"
---
# <a name="addressof-operator-visual-basic"></a>Operatore AddressOf (Visual Basic)
Crea un'istanza di delegato di routine che fa riferimento la procedura specifica.  
  
## <a name="syntax"></a>Sintassi  
  
```  
AddressOf procedurename  
```  
  
## <a name="parts"></a>Parti  
 `procedurename`  
 Obbligatorio. Specifica la routine a cui fa riferimento il delegato appena creato.  
  
## <a name="remarks"></a>Note  
 Il `AddressOf` operatore crea un delegato della funzione che fa riferimento alla funzione specificata da `procedurename`. Quando la procedura specificata è che un metodo di istanza, quindi il delegato della funzione fa riferimento a sia l'istanza del metodo. Quindi, quando viene richiamato il delegato della funzione viene chiamato il metodo specificato dell'istanza specificata.  
  
 Il `AddressOf` operatore può essere usato come operando di un costruttore di delegato o può essere usato in un contesto in cui il tipo del delegato può essere determinato dal compilatore.  
  
## <a name="example"></a>Esempio  
 Questo esempio Usa la `AddressOf` operatore per definire un delegato per gestire il `Click` eventi di un pulsante.  
  
 [!code-vb[VbVbalrDelegates#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDelegates/VB/Class1.vb#8)]  
  
## <a name="example"></a>Esempio  
 L'esempio seguente usa il `AddressOf` operatore per specificare la funzione di avvio per un thread.  
  
 [!code-vb[VbVbalrDelegates#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDelegates/VB/Class1.vb#9)]  
  
## <a name="see-also"></a>Vedere anche

- [Istruzione Declare](../../../visual-basic/language-reference/statements/declare-statement.md)
- [Istruzione Function](../../../visual-basic/language-reference/statements/function-statement.md)
- [Istruzione Sub](../../../visual-basic/language-reference/statements/sub-statement.md)
- [Delegati](../../../visual-basic/programming-guide/language-features/delegates/index.md)
