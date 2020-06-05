---
title: Non è possibile chiamare la funzione Friend su un oggetto che non è un'istanza della classe di definizione
ms.date: 07/20/2015
f1_keywords:
- vbrID97
ms.assetid: b9d821f0-8565-4f15-bb35-184789c69662
ms.openlocfilehash: c18c04470c4c49113e8195b92185326c5c4197c1
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84400848"
---
# <a name="cannot-call-friend-function-on-object-which-is-not-an-instance-of-defining-class"></a>Non è possibile chiamare la funzione Friend su un oggetto che non è un'istanza della classe di definizione
Si è provato a chiamare la routine `Friend` di una classe oppure di accedere a un metodo o a una proprietà `Friend` tra più processi o cross-thread. Una routine `Friend` può essere chiamata da un modulo all'esterno della classe, ma fa parte del progetto in cui è definita la classe.  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
- Assicurarsi di chiamare la routine o di accedervi da un modulo che fa parte del progetto in cui è definita la classe.  
  
## <a name="see-also"></a>Vedere anche

- [Amico](../language-reference/modifiers/friend.md)
