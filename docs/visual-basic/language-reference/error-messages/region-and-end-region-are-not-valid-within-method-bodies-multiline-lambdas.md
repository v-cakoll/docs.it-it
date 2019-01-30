---
title: Le istruzioni '#Region' e '#End Region' non sono valide nelle espressioni lambda su più righe corpi di metodo
ms.date: 07/20/2015
f1_keywords:
- bc32025
- vbc32025
helpviewer_keywords:
- BC32025
ms.assetid: 43707bf1-1c6b-4d82-b081-e5a17dca51c1
ms.openlocfilehash: 2a2f5692518c6784dfc6e3be6302f1e8dcf2aaa7
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/30/2019
ms.locfileid: "55265571"
---
# <a name="region-and-end-region-statements-are-not-valid-within-method-bodiesmultiline-lambdas"></a>Le istruzioni '#Region' e '#End Region' non sono valide nei corpi di metodi o di espressioni lambda su più righe
Il `#Region` blocco deve essere dichiarato a livello di classe, modulo o dello spazio dei nomi. Un'area comprimibile può includere una o più procedure, ma non può iniziare o terminare all'interno di una procedura.  
  
 **ID errore:** BC32025  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
1.  Assicurarsi che la procedura precedente venga terminata correttamente con un `End Function` o `End Sub` istruzione.  
  
2.  Verificare che il `#Region` e `#End Region` direttive sono nello stesso blocco di codice.  
  
## <a name="see-also"></a>Vedere anche
- [Direttiva #Region](../../../visual-basic/language-reference/directives/region-directive.md)
