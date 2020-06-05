---
title: L'istruzione non può terminare con un blocco all'esterno di un'istruzione di riga 'If'
ms.date: 07/20/2015
f1_keywords:
- vbc32005
- bc32005
helpviewer_keywords:
- BC32005
ms.assetid: 4039f51b-e0ee-4789-a89b-45d06de06b5d
ms.openlocfilehash: 3fe3faaa3637446bb6ab443ba1d6e1d1004b4d48
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84400318"
---
# <a name="statement-cannot-end-a-block-outside-of-a-line-if-statement"></a>L'istruzione non può terminare con un blocco all'esterno di un'istruzione di riga 'If'
Un'istruzione a riga singola `If` contiene diverse istruzioni separate da due punti (:), una delle quali è un' `End` istruzione per un blocco di controllo all'esterno della riga singola `If` . Per le istruzioni a riga singola `If` non viene utilizzata l' `End If` istruzione.  
  
 **ID errore:** BC32005  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
- Spostare l'istruzione a riga singola `If` all'esterno del blocco di controllo che contiene l' `End If` istruzione.  
  
## <a name="see-also"></a>Vedere anche

- [Istruzione If...Then...Else](../statements/if-then-else-statement.md)
