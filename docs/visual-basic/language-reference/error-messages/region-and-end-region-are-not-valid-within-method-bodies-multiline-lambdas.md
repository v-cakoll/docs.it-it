---
title: '&#39;#Region&#39; e &#39;area #End&#39; istruzioni non sono valide nelle espressioni lambda su più righe corpi di metodo'
ms.date: 07/20/2015
f1_keywords:
- bc32025
- vbc32025
helpviewer_keywords:
- BC32025
ms.assetid: 43707bf1-1c6b-4d82-b081-e5a17dca51c1
ms.openlocfilehash: 55399cd123ce4d67cc833f2eabe3230acdafc0bf
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54737215"
---
# <a name="39region39-and-39end-region39-statements-are-not-valid-within-method-bodiesmultiline-lambdas"></a>&#39;#Region&#39; e &#39;area #End&#39; istruzioni non sono valide nelle espressioni lambda corpi/su più righe (metodo)
Il `#Region` blocco deve essere dichiarato a livello di classe, modulo o dello spazio dei nomi. Un'area comprimibile può includere una o più procedure, ma non può iniziare o terminare all'interno di una procedura.  
  
 **ID errore:** BC32025  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
1.  Assicurarsi che la procedura precedente venga terminata correttamente con un `End Function` o `End Sub` istruzione.  
  
2.  Verificare che il `#Region` e `#End Region` direttive sono nello stesso blocco di codice.  
  
## <a name="see-also"></a>Vedere anche
- [Direttiva #Region](../../../visual-basic/language-reference/directives/region-directive.md)
