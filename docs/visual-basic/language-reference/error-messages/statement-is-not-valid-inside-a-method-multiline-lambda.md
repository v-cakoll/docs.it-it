---
title: Istruzione non valida all'interno di un'espressione lambda su più righe (metodo)
ms.date: 07/20/2015
f1_keywords:
- vbc30024
- bc30024
helpviewer_keywords:
- BC30024
ms.assetid: 758e7a8f-429b-42c1-9a78-778e5b480e04
ms.openlocfilehash: 994cafc44a37d16d0f70caec560f530c6a836ec0
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "62055121"
---
# <a name="statement-is-not-valid-inside-a-methodmultiline-lambda"></a>Istruzione non valida all'interno di un metodo/espressione lambda su più righe
L'istruzione non è valido all'interno di un `Sub`, `Function`, proprietà `Get`, o proprietà `Set` procedure. Alcune istruzioni possono essere inseriti a livello di classe o modulo. Altri, ad esempio `Option Strict`, devono essere a livello di spazio dei nomi e precedere tutte le altre dichiarazioni.  
  
 **ID errore:** BC30024  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
- Rimuovere l'istruzione della procedura.  
  
## <a name="see-also"></a>Vedere anche

- [Istruzione Sub](../../../visual-basic/language-reference/statements/sub-statement.md)
- [Istruzione Function](../../../visual-basic/language-reference/statements/function-statement.md)
- [Istruzione Get](../../../visual-basic/language-reference/statements/get-statement.md)
- [Istruzione Set](../../../visual-basic/language-reference/statements/set-statement.md)
