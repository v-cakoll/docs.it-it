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
ms.openlocfilehash: e88520bd7e731a35b98c1d40c5210dc5d1314911
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74350274"
---
# <a name="addressof-operator-visual-basic"></a>Operatore AddressOf (Visual Basic)
Crea un'istanza di delegato che fa riferimento alla procedura specifica.  
  
## <a name="syntax"></a>Sintassi  
  
```vb  
AddressOf procedurename  
```  
  
## <a name="parts"></a>Parti  
 `procedurename`  
 Obbligatoria. Specifica la procedura a cui fa riferimento il delegato appena creato.  
  
## <a name="remarks"></a>Osservazioni  
 L'operatore `AddressOf` crea un delegato che punta alla subroutine o alla funzione specificata da `procedurename`. Quando la procedura specificata è un metodo di istanza, il delegato fa riferimento sia all'istanza sia al metodo. Quindi, quando viene richiamato il delegato, viene chiamato il metodo specificato dell'istanza specificata.  
  
 L'operatore `AddressOf` può essere usato come operando di un costruttore di delegato o può essere usato in un contesto in cui il tipo del delegato può essere determinato dal compilatore.  
  
## <a name="example"></a>Esempio  
 In questo esempio viene usato l'operatore `AddressOf` per designare un delegato per gestire l'evento `Click` di un pulsante.  
  
 [!code-vb[VbVbalrDelegates#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDelegates/VB/Class1.vb#8)]  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene usato l'operatore `AddressOf` per designare la funzione di avvio per un thread.  
  
 [!code-vb[VbVbalrDelegates#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDelegates/VB/Class1.vb#9)]  
  
## <a name="see-also"></a>Vedere anche

- [Istruzione Declare](../../../visual-basic/language-reference/statements/declare-statement.md)
- [Istruzione Function](../../../visual-basic/language-reference/statements/function-statement.md)
- [Istruzione Sub](../../../visual-basic/language-reference/statements/sub-statement.md)
- [Delegati](../../../visual-basic/programming-guide/language-features/delegates/index.md)
