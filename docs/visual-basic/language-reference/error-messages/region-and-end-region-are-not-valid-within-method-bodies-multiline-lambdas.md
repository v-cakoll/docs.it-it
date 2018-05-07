---
title: "&#39;#Region&#39; e &#39;area #End&#39; istruzioni non sono valide all'interno di espressioni lambda su più righe di corpi di metodo"
ms.date: 07/20/2015
f1_keywords:
- bc32025
- vbc32025
helpviewer_keywords:
- BC32025
ms.assetid: 43707bf1-1c6b-4d82-b081-e5a17dca51c1
ms.openlocfilehash: bf3843e0ec3009f3dc7d60e91c340a7f20543231
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="39region39-and-39end-region39-statements-are-not-valid-within-method-bodiesmultiline-lambdas"></a>&#39;#Region&#39; e &#39;area #End&#39; istruzioni non sono valide all'interno di espressioni lambda corpi/multiline (metodo)
Il `#Region` blocco deve essere dichiarato a livello di classe, modulo o spazio dei nomi. Un'area comprimibile può includere una o più procedure, ma non può iniziare o terminare all'interno di una stored procedure.  
  
 **ID errore:** BC32025  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
1.  Verificare che la procedura precedente venga terminata correttamente con un `End Function` o `End Sub` istruzione.  
  
2.  Verificare che il `#Region` e `#End Region` direttive sono nello stesso blocco di codice.  
  
## <a name="see-also"></a>Vedere anche  
 [Direttiva #Region](../../../visual-basic/language-reference/directives/region-directive.md)
