---
title: Le istruzioni '#Region' e '#End Region' non sono valide nei corpi di metodi o di espressioni lambda su più righe
ms.date: 07/20/2015
f1_keywords:
- bc32025
- vbc32025
helpviewer_keywords:
- BC32025
ms.assetid: 43707bf1-1c6b-4d82-b081-e5a17dca51c1
ms.openlocfilehash: 5652139ab139ea93258eb116f97ba21b76986a24
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84400383"
---
# <a name="region-and-end-region-statements-are-not-valid-within-method-bodiesmultiline-lambdas"></a>Le istruzioni '#Region' e '#End Region' non sono valide nei corpi di metodi o di espressioni lambda su più righe
Il `#Region` blocco deve essere dichiarato a livello di classe, modulo o spazio dei nomi. Un'area comprimibile può includere una o più procedure, ma non può iniziare o terminare all'interno di una routine.  
  
 **ID errore:** BC32025  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
1. Verificare che la procedura precedente sia terminata correttamente con `End Function` un' `End Sub` istruzione o.  
  
2. Verificare che le `#Region` `#End Region` direttive e si trovino nello stesso blocco di codice.  
  
## <a name="see-also"></a>Vedere anche

- [#Region (direttiva)](../directives/region-directive.md)
