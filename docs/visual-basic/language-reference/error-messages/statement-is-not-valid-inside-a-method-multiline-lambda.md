---
title: Istruzione non valida all'interno di un metodo/espressione lambda su più righe
ms.date: 07/20/2015
f1_keywords:
- vbc30024
- bc30024
helpviewer_keywords:
- BC30024
ms.assetid: 758e7a8f-429b-42c1-9a78-778e5b480e04
ms.openlocfilehash: f3c43d640259d5e1af545e2610088aab5d70453d
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84396246"
---
# <a name="statement-is-not-valid-inside-a-methodmultiline-lambda"></a>Istruzione non valida all'interno di un metodo/espressione lambda su più righe
L'istruzione non è valida all'interno di una `Sub` `Function` `Get` routine Property,, o `Set` . È possibile inserire alcune istruzioni a livello di modulo o di classe. Altri, ad esempio `Option Strict` , devono essere a livello di spazio dei nomi e precedere tutte le altre dichiarazioni.  
  
 **ID errore:** BC30024  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
- Rimuovere l'istruzione dalla procedura.  
  
## <a name="see-also"></a>Vedere anche

- [Istruzione Sub](../statements/sub-statement.md)
- [Istruzione Function](../statements/function-statement.md)
- [Istruzione Get](../statements/get-statement.md)
- [Istruzione set](../statements/set-statement.md)
