---
title: L'operando 'AddressOf' deve essere il nome di un metodo, senza parentesi
ms.date: 07/20/2015
f1_keywords:
- vbc30577
- bc30577
helpviewer_keywords:
- BC30577
ms.assetid: c2c55640-5c61-4e66-97a4-4322020c6001
ms.openlocfilehash: 37b02ab76730458b757835fda37b8cb145ed93ad
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/30/2019
ms.locfileid: "55262114"
---
# <a name="addressof-operand-must-be-the-name-of-a-method-without-parentheses"></a>L'operando 'AddressOf' deve essere il nome di un metodo, senza parentesi
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
