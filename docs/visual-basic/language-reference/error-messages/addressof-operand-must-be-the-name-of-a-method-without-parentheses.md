---
title: L'operando 'AddressOf' deve essere il nome di un metodo, senza parentesi
ms.date: 07/20/2015
f1_keywords:
- vbc30577
- bc30577
helpviewer_keywords:
- BC30577
ms.assetid: c2c55640-5c61-4e66-97a4-4322020c6001
ms.openlocfilehash: b8c67c2390df91c6a4af66e020365544e6bf369b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61751631"
---
# <a name="addressof-operand-must-be-the-name-of-a-method-without-parentheses"></a>L'operando 'AddressOf' deve essere il nome di un metodo, senza parentesi
L'operatore `AddressOf` crea un'istanza di delegato di routine che fa riferimento a una routine specifica. La sintassi è come indicato di seguito.  
  
 `AddressOf` `procedurename`  
  
 È stato inserito tra parentesi attorno ai seguenti argomenti `AddressOf`, che tuttavia non sono necessarie.  
  
 **ID errore:** BC30577  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
1. Rimuovere le parentesi che racchiudono l'argomento che segue `AddressOf`.  
  
2. Assicurarsi che l'argomento è un nome di metodo.  
  
## <a name="see-also"></a>Vedere anche

- [Operatore AddressOf](../../../visual-basic/language-reference/operators/addressof-operator.md)
- [Delegati](../../../visual-basic/programming-guide/language-features/delegates/index.md)
