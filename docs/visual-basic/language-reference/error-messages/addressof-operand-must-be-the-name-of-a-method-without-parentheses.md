---
title: '&#39; AddressOf &#39; operando deve essere il nome di un metodo (senza parentesi)'
ms.date: 07/20/2015
ms.prod: .net
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc30577
- bc30577
helpviewer_keywords:
- BC30577
ms.assetid: c2c55640-5c61-4e66-97a4-4322020c6001
caps.latest.revision: 10
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 02c996f1c94250526982e35395288b07db619db7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="39addressof39-operand-must-be-the-name-of-a-method-without-parentheses"></a>&#39; AddressOf &#39; operando deve essere il nome di un metodo (senza parentesi)
L'operatore `AddressOf` crea un'istanza di delegato di routine che fa riferimento a una routine specifica. La sintassi è come indicato di seguito.  
  
 `AddressOf` `procedurename`  
  
 È stato inserito parentesi per racchiudere l'argomento che segue `AddressOf`, che tuttavia non sono necessarie.  
  
 **ID errore:** BC30577  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
1.  Rimuovere le parentesi che racchiudono il seguente argomento `AddressOf`.  
  
2.  Verificare che l'argomento è un nome di metodo.  
  
## <a name="see-also"></a>Vedere anche  
 [Operatore AddressOf](../../../visual-basic/language-reference/operators/addressof-operator.md)  
 [Delegati](../../../visual-basic/programming-guide/language-features/delegates/index.md)
