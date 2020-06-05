---
title: Operatore AddressOf
ms.date: 07/20/2015
f1_keywords:
- AddressOf
- vb.AddressOf
helpviewer_keywords:
- AddressOf operator [Visual Basic]
- addresses, passing to API procedures
ms.assetid: 8105a59d-60d8-4ab5-b221-5899cdfacbf4
ms.openlocfilehash: 3e7db8e7329ce8d21b6e07863e6f1673a6389608
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84372064"
---
# <a name="addressof-operator-visual-basic"></a>Operatore AddressOf (Visual Basic)
Crea un'istanza di delegato che fa riferimento alla procedura specifica.  
  
## <a name="syntax"></a>Sintassi  
  
```vb  
AddressOf procedurename  
```  
  
## <a name="parts"></a>Parti  
 `procedurename`  
 Obbligatorio. Specifica la procedura a cui fa riferimento il delegato appena creato.  
  
## <a name="remarks"></a>Commenti  
 L' `AddressOf` operatore crea un delegato che punta alla subroutine o alla funzione specificata da `procedurename` . Quando la procedura specificata è un metodo di istanza, il delegato fa riferimento sia all'istanza sia al metodo. Quindi, quando viene richiamato il delegato, viene chiamato il metodo specificato dell'istanza specificata.  
  
 L' `AddressOf` operatore può essere usato come operando di un costruttore di delegato o può essere usato in un contesto in cui il tipo del delegato può essere determinato dal compilatore.  
  
## <a name="example"></a>Esempio  
 In questo esempio viene usato l' `AddressOf` operatore per designare un delegato per gestire l' `Click` evento di un pulsante.  
  
 [!code-vb[VbVbalrDelegates#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDelegates/VB/Class1.vb#8)]  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene usato l' `AddressOf` operatore per designare la funzione di avvio per un thread.  
  
 [!code-vb[VbVbalrDelegates#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDelegates/VB/Class1.vb#9)]  
  
## <a name="see-also"></a>Vedere anche

- [Declare Statement](../statements/declare-statement.md)
- [Istruzione Function](../statements/function-statement.md)
- [Istruzione Sub](../statements/sub-statement.md)
- [Delegati](../../programming-guide/language-features/delegates/index.md)
