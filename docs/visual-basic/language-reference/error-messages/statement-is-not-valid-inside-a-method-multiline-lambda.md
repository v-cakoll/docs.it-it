---
title: Istruzione non è valida all'interno di un'espressione lambda su più righe di metodo
ms.date: 07/20/2015
f1_keywords:
- vbc30024
- bc30024
helpviewer_keywords:
- BC30024
ms.assetid: 758e7a8f-429b-42c1-9a78-778e5b480e04
ms.openlocfilehash: cef5beea16c8589a884b7d3533e0543454783999
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33598855"
---
# <a name="statement-is-not-valid-inside-a-methodmultiline-lambda"></a>Istruzione non valida all'interno di un metodo/espressione lambda su più righe
L'istruzione non è valido all'interno di un `Sub`, `Function`, proprietà `Get`, o proprietà `Set` stored procedure. Alcune istruzioni possono essere inseriti a livello di modulo o classe. Altri, ad esempio `Option Strict`, è necessario essere a livello di spazio dei nomi e precedere tutte le altre dichiarazioni.  
  
 **ID errore:** BC30024  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
-   Rimuovere l'istruzione dalla routine.  
  
## <a name="see-also"></a>Vedere anche  
 [Istruzione Sub](../../../visual-basic/language-reference/statements/sub-statement.md)  
 [Istruzione Function](../../../visual-basic/language-reference/statements/function-statement.md)  
 [Istruzione Get](../../../visual-basic/language-reference/statements/get-statement.md)  
 [Istruzione Set](../../../visual-basic/language-reference/statements/set-statement.md)
