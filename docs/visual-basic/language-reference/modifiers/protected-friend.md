---
title: Friend protetto (Visual Basic)
ms.date: 05/10/2018
helpviewer_keywords:
- Protected Friend keyword [Visual Basic]
- Protected Friend keyword [Visual Basic], syntax
ms.openlocfilehash: d3592feaece1d5ce85ee6e2657d8a2715c4097a3
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2019
ms.locfileid: "72524781"
---
# <a name="protected-friend-visual-basic"></a>Friend protetto (Visual Basic)

La combinazione delle parole chiave `Protected Friend` è un modificatore di accesso ai membri. Conferisce sia l'accesso [Friend](friend.md) che l'accesso [protetto](protected.md) sugli elementi dichiarati, in modo che siano accessibili da qualsiasi punto dello stesso assembly, dalla propria classe e dalle classi derivate. È possibile specificare `Protected Friend` solo per i membri delle classi; non è possibile applicare `Protected Friend` ai membri di una struttura perché le strutture non possono essere ereditate.

> [!NOTE]
> In Visual Studio, selezionando la Guida sensibile al contesto `protected friend` viene fornita una guida per [protected](protected.md) o [Friend](friend.md). L'IDE sceglie il singolo token sotto il cursore anziché la parola composta.

## <a name="rules"></a>Regole

**Contesto di dichiarazione.** È possibile utilizzare `Protected Friend` solo a livello di classe. Ciò significa che il contesto di dichiarazione per un elemento di `Protected` deve essere una classe e non può essere un file di origine, uno spazio dei nomi, un'interfaccia, un modulo, una struttura o una procedura.

## <a name="see-also"></a>Vedere anche

- [Public](../../../visual-basic/language-reference/modifiers/public.md)
- [Protected](../../../visual-basic/language-reference/modifiers/protected.md)
- [Friend](friend.md)
- [Private](../../../visual-basic/language-reference/modifiers/private.md)
- [Private Protected](./private-protected.md)
- [Livelli di accesso in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)
- [Routine](../../../visual-basic/programming-guide/language-features/procedures/index.md)
- [Strutture](../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [Oggetti e classi](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
