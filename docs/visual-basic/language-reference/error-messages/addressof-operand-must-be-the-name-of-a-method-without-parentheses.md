---
title: '&#39;AddressOf&#39; operando deve essere il nome di un metodo (senza parentesi)'
ms.date: 07/20/2015
f1_keywords:
- vbc30577
- bc30577
helpviewer_keywords:
- BC30577
ms.assetid: c2c55640-5c61-4e66-97a4-4322020c6001
ms.openlocfilehash: 6f9827d885996ffab8bdab91d0f774a57073e4a3
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54565150"
---
# <a name="39addressof39-operand-must-be-the-name-of-a-method-without-parentheses"></a>&#39;AddressOf&#39; operando deve essere il nome di un metodo (senza parentesi)
L'operatore `AddressOf` crea un'istanza di delegato di routine che fa riferimento a una routine specifica. La sintassi è come indicato di seguito.  
  
 `AddressOf` `procedurename`  
  
 È stato inserito tra parentesi attorno ai seguenti argomenti `AddressOf`, che tuttavia non sono necessarie.  
  
 **ID errore:** BC30577  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
1.  Rimuovere le parentesi che racchiudono l'argomento che segue `AddressOf`.  
  
2.  Assicurarsi che l'argomento è un nome di metodo.  
  
## <a name="see-also"></a>Vedere anche
- [Operatore AddressOf](../../../visual-basic/language-reference/operators/addressof-operator.md)
- [Delegati](../../../visual-basic/programming-guide/language-features/delegates/index.md)
