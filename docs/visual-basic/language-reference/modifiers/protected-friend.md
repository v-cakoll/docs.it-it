---
title: Protected Friend (Visual Basic)
ms.date: 05/10/2018
helpviewer_keywords:
- Protected Friend keyword [Visual Basic]
- Protected Friend keyword [Visual Basic], syntax
ms.openlocfilehash: b72cbee0394043620e792d1c014bfe55121e175e
ms.sourcegitcommit: 22c3c8f74eaa138dbbbb02eb7d720fce87fc30a9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/18/2018
---
# <a name="protected-friend-visual-basic"></a>Protected Friend (Visual Basic)

La combinazione delle parole chiave `Protected Friend` è un modificatore di accesso ai membri. Entrambi conferisce [Friend](friend.md) l'accesso e [Protected](protected.md) l'accesso per gli elementi dichiarati, in modo che siano accessibili da qualsiasi punto nello stesso assembly, dalla rispettiva classe e dalle classi derivate. È possibile specificare `Protected Friend` solo in membri di classi; non è possibile applicare `Protected Friend` ai membri di una struttura perché le strutture non possono essere ereditate.

> [!NOTE]
> In Visual Studio, selezionare la Guida F1 nei `protected friend` viene fornita la Guida per uno [protetti](protected.md) o [friend](friend.md). L'IDE sceglie il token singolo sotto il cursore anziché la parola composta.

## <a name="rules"></a>Regole

- **Contesto della dichiarazione.** È possibile utilizzare `Protected Friend` solo a livello di classe. Ciò significa che il contesto della dichiarazione per un `Protected` elemento deve essere una classe e non può essere un file di origine, lo spazio dei nomi, interfaccia, modulo, struttura o stored procedure. 


## <a name="see-also"></a>Vedere anche

[Public](../../../visual-basic/language-reference/modifiers/public.md)  
[Protected](../../../visual-basic/language-reference/modifiers/protected.md)  
[Friend](friend.md)   
[Private](../../../visual-basic/language-reference/modifiers/private.md)  
[Protetto privato](./private-protected.md)   
[Livelli di accesso in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)  
[Routine](../../../visual-basic/programming-guide/language-features/procedures/index.md)  
[Strutture](../../../visual-basic/programming-guide/language-features/data-types/structures.md)  
[Oggetti e classi](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
