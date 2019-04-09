---
title: Protected Friend (Visual Basic)
ms.date: 05/10/2018
helpviewer_keywords:
- Protected Friend keyword [Visual Basic]
- Protected Friend keyword [Visual Basic], syntax
ms.openlocfilehash: 331c63dc290d4096e8158f265ee869b47743a273
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59151775"
---
# <a name="protected-friend-visual-basic"></a>Protected Friend (Visual Basic)

La combinazione delle parole chiave `Protected Friend` è un modificatore di accesso ai membri. Entrambi conferisce [Friend](friend.md) l'accesso e [Protected](protected.md) accesso per gli elementi dichiarati, in modo che siano accessibili da qualsiasi punto nello stesso assembly, dalla propria classe e dalle classi derivate. È possibile specificare `Protected Friend` solo in membri di classi; non è possibile applicare `Protected Friend` ai membri di una struttura perché le strutture non possono essere ereditate.

> [!NOTE]
> In Visual Studio, selezionare la Guida F1 nei `protected friend` vengono fornite informazioni per uno [protetti](protected.md) oppure [friend](friend.md). L'IDE sceglie il token single sotto il cursore anziché la parola composta.

## <a name="rules"></a>Regole

- **Contesto della dichiarazione.** È possibile usare `Protected Friend` solo a livello di classe. Ciò significa che il contesto della dichiarazione per un `Protected` elemento deve essere una classe e non può essere un file di origine, lo spazio dei nomi, interfaccia, modulo, struttura o procedure. 

## <a name="see-also"></a>Vedere anche

- [Public](../../../visual-basic/language-reference/modifiers/public.md)
- [Protetta](../../../visual-basic/language-reference/modifiers/protected.md)
- [Friend](friend.md)
- [Private](../../../visual-basic/language-reference/modifiers/private.md)
- [Private Protected](./private-protected.md)
- [Livelli di accesso in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)
- [Procedure](../../../visual-basic/programming-guide/language-features/procedures/index.md)
- [Strutture](../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [Oggetti e classi](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
