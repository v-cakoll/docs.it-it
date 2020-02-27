---
title: Tipi annidati - Guida per programmatori C#
ms.date: 02/08/2020
helpviewer_keywords:
- nested types [C#]
ms.assetid: f2e1b315-e3d1-48ce-977f-7bae0960ba99
ms.openlocfilehash: 12e44ccc1254424c152a238c8390f133550fa54c
ms.sourcegitcommit: 44a7cd8687f227fc6db3211ccf4783dc20235e51
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/26/2020
ms.locfileid: "77626490"
---
# <a name="nested-types-c-programming-guide"></a>Tipi annidati (Guida per programmatori C#)

Un tipo definito all'interno di una [classe](../../language-reference/keywords/class.md), uno [struct](../../language-reference/builtin-types/struct.md)o un' [interfaccia](../../language-reference/keywords/interface.md) viene definito tipo annidato. Ad esempio:

[!code-csharp[DeclareNestedClass](~/samples/snippets/csharp/objectoriented/nestedtypes.cs#DeclareNestedClass)]

Indipendentemente dal fatto che il tipo esterno sia una classe, un'interfaccia o uno struct, i tipi annidati per impostazione predefinita sono [privati](../../language-reference/keywords/private.md); sono accessibili solo dal tipo che lo contiene. Nell'esempio precedente, la classe `Nested` non è accessibile a tipi esterni.

È possibile anche specificare un [modificatore di accesso](../../language-reference/keywords/access-modifiers.md) per definire l'accessibilità di un tipo annidato, come indicato di seguito:

- I tipi annidati di una **classe** possono essere [public](../../language-reference/keywords/public.md), [protected](../../language-reference/keywords/protected.md), [internal](../../language-reference/keywords/internal.md), [protected internal](../../language-reference/keywords/protected-internal.md), [private](../../language-reference/keywords/private.md) o [private protected](../../language-reference/keywords/private-protected.md).

   La definizione di una classe annidata `protected`, `protected internal` o `private protected` all'interno di un [classe sealed](../../language-reference/keywords/sealed.md), tuttavia, genera l'avviso del compilatore [CS0628](../../misc/cs0628.md): "Il nuovo membro protected è stato dichiarato nella classe sealed".
  
- I tipi annidati di uno **struct** possono essere [public](../../language-reference/keywords/public.md), [internal](../../language-reference/keywords/internal.md) o [private](../../language-reference/keywords/private.md).

Nell'esempio seguente, la classe `Nested` viene resa public:

[!code-csharp[PublicNestedClass](~/samples/snippets/csharp/objectoriented/nestedtypes.cs#PublicNestedClass)]

Il tipo annidato, o interno, può accedere al tipo contenitore, o esterno. Per accedere al tipo contenitore, passarlo come argomento al costruttore del tipo annidato. Ad esempio,

[!code-csharp[DeclareNestedInstance](~/samples/snippets/csharp/objectoriented/nestedtypes.cs#DeclareNestedInstance)]

Un tipo annidato può accedere a tutti i membri accessibili al tipo contenitore. Può accedere a membri privati e protetti del tipo che li contengono, inclusi tutti i membri protetti ereditati.

Nella dichiarazione precedente il nome completo della classe `Nested` è `Container.Nested`. Questo nome viene utilizzato per creare una nuova istanza della classe annidata, come illustrato di seguito:

[!code-csharp[UseNestedInstance](~/samples/snippets/csharp/objectoriented/nestedtypes.cs#UseNestedInstance)]

## <a name="see-also"></a>Vedere anche

- [Guida per programmatori C#](../index.md)
- [Classi e struct](./index.md)
- [Modificatori di accesso](./access-modifiers.md)
- [Costruttori](./constructors.md)
