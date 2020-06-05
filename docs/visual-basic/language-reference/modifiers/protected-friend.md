---
title: Protected Friend
ms.date: 05/10/2018
helpviewer_keywords:
- Protected Friend keyword [Visual Basic]
- Protected Friend keyword [Visual Basic], syntax
ms.openlocfilehash: 202d4f4a3a05a64ab1d74621268f28f6b55e8952
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84404836"
---
# <a name="protected-friend-visual-basic"></a>Friend protetto (Visual Basic)

La combinazione delle parole chiave `Protected Friend` è un modificatore di accesso ai membri. Conferisce sia l'accesso [Friend](friend.md) che l'accesso [protetto](protected.md) sugli elementi dichiarati, in modo che siano accessibili da qualsiasi punto dello stesso assembly, dalla propria classe e dalle classi derivate. È possibile specificare `Protected Friend` solo per i membri delle classi. non è possibile applicare `Protected Friend` ai membri di una struttura perché le strutture non possono essere ereditate.

> [!NOTE]
> In Visual Studio, selezionando la Guida sensibile al contesto, `protected friend` viene fornita una guida per [protected](protected.md) o [Friend](friend.md). L'IDE sceglie il singolo token sotto il cursore anziché la parola composta.

## <a name="rules"></a>Regole

**Contesto della dichiarazione. ** È possibile usare `Protected Friend` solo a livello di classe. Ciò significa che il contesto di dichiarazione per un `Protected` elemento deve essere una classe e non può essere un file di origine, uno spazio dei nomi, un'interfaccia, un modulo, una struttura o una procedura.

## <a name="see-also"></a>Vedere anche

- [Pubblica](public.md)
- [Protetto](protected.md)
- [Amico](friend.md)
- [Privata](private.md)
- [Privato protetto](./private-protected.md)
- [Livelli di accesso in Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md)
- [Procedure](../../programming-guide/language-features/procedures/index.md)
- [Strutture](../../programming-guide/language-features/data-types/structures.md)
- [Oggetti e classi](../../programming-guide/language-features/objects-and-classes/index.md)
