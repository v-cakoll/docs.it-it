---
title: "&#39; #Region &#39; e &#39; area #End &#39; le istruzioni non sono valide all'interno di espressioni lambda su più righe di corpi di metodo"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc32025
- vbc32025
helpviewer_keywords:
- BC32025
ms.assetid: 43707bf1-1c6b-4d82-b081-e5a17dca51c1
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 614d0c7324bfbf07bc5736c799e8b54937ead081
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="39region39-and-39end-region39-statements-are-not-valid-within-method-bodiesmultiline-lambdas"></a>&#39; #Region &#39; e &#39; area #End &#39; le istruzioni non sono valide all'interno di espressioni lambda corpi/su più righe (metodo)
Il `#Region` blocco deve essere dichiarato a livello di classe, modulo o spazio dei nomi. Un'area comprimibile può includere una o più procedure, ma non può iniziare o terminare all'interno di una stored procedure.  
  
 **ID errore:** BC32025  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
1.  Verificare che la procedura precedente venga terminata correttamente con un `End Function` o `End Sub` istruzione.  
  
2.  Verificare che il `#Region` e `#End Region` direttive sono nello stesso blocco di codice.  
  
## <a name="see-also"></a>Vedere anche  
 [Direttiva #Region](../../../visual-basic/language-reference/directives/region-directive.md)
