---
title: "Classe delegata &#39; &lt;classname&gt;&#39; non contiene alcun metodo Invoke, un'espressione di questo tipo non può essere la destinazione di una chiamata al metodo"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc30220
- bc30220
helpviewer_keywords: BC30220
ms.assetid: 6be0d61c-f2f9-4f9b-ab90-8871a0d7206d
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 55d0e2442807e25737d90ac4b45a59b9d3e73037
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="delegate-class-39ltclassnamegt39-has-no-invoke-method-so-an-expression-of-this-type-cannot-be-the-target-of-a-method-call"></a>Classe delegata &#39; &lt;classname&gt;&#39; non contiene alcun metodo Invoke, un'espressione di questo tipo non può essere la destinazione di una chiamata al metodo
Una chiamata a `Invoke` tramite un delegato non è riuscita perché `Invoke` non è implementata nella classe delegata.  
  
 **ID errore:** BC30220  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
1.  Verificare che sia stata creata un'istanza della classe delegato con un `Dim` istruzione e una stored procedure è stata assegnata all'istanza del delegato con il `AddressOf` operatore.  
  
2.  Individuare il codice che implementa la classe delegata e assicurarsi che implementa il `Invoke` stored procedure.  
  
## <a name="see-also"></a>Vedere anche  
 [Delegati](../../../visual-basic/programming-guide/language-features/delegates/index.md)  
 [Istruzione Delegate](../../../visual-basic/language-reference/statements/delegate-statement.md)  
 [Operatore AddressOf](../../../visual-basic/language-reference/operators/addressof-operator.md)  
 [Istruzione Dim](../../../visual-basic/language-reference/statements/dim-statement.md)
