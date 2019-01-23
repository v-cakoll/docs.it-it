---
title: Non è accessibile &#39;Main&#39; metodo con una firma appropriata è stato trovato &#39; &lt;nome&gt;&#39;
ms.date: 07/20/2015
f1_keywords:
- bc30737
- vbc30737
helpviewer_keywords:
- BC30737
ms.assetid: 3f40bacd-3fac-4741-b204-852f693d4340
ms.openlocfilehash: 3398195ef9d503e47ab569ff85cb2a827c4270f1
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54501490"
---
# <a name="no-accessible-39main39-method-with-an-appropriate-signature-was-found-in-39ltnamegt39"></a>Non è accessibile &#39;Main&#39; metodo con una firma appropriata è stato trovato &#39; &lt;nome&gt;&#39;
Le applicazioni della riga di comando devono avere un `Sub Main` definito. `Main` deve essere dichiarato come `Public Shared` se è definito in una classe o come `Public` se definita in un modulo.  
  
 **ID errore:** BC30737  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
-   Definire un `Public Sub Main` procedure per il progetto. Dichiara la classe come `Shared` se e solo se viene definita in una classe.  
  
## <a name="see-also"></a>Vedere anche
- [Struttura di un programma Visual Basic](../../../visual-basic/programming-guide/program-structure/structure-of-a-visual-basic-program.md)
- [Routine](../../../visual-basic/programming-guide/language-features/procedures/index.md)
