---
title: Tipi annidati - Guida per programmatori C#
ms.date: 07/10/2017
helpviewer_keywords:
- nested types [C#]
ms.assetid: f2e1b315-e3d1-48ce-977f-7bae0960ba99
ms.openlocfilehash: 982eeceb2088dd6e1e57fe796b38e46c0f2d4de8
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75705496"
---
# <a name="nested-types-c-programming-guide"></a>Tipi annidati (Guida per programmatori C#)
Per tipo annidato si intende un tipo definito all'interno di una [classe](../../language-reference/keywords/class.md) o di uno [struct](../../language-reference/keywords/struct.md). Ad esempio:  
  
 [!code-csharp[csProgGuideObjects#68](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#68)]  
  
Che il tipo esterno sia una classe o uno struct, per impostazione predefinita i tipi annidati sono [private](../../language-reference/keywords/private.md) e sono accessibili solo dal relativo tipo contenitore. Nell'esempio precedente, la classe `Nested` non è accessibile a tipi esterni. 

È possibile anche specificare un [modificatore di accesso](../../language-reference/keywords/access-modifiers.md) per definire l'accessibilità di un tipo annidato, come indicato di seguito:

- I tipi annidati di una **classe** possono essere [public](../../language-reference/keywords/public.md), [protected](../../language-reference/keywords/protected.md), [internal](../../language-reference/keywords/internal.md), [protected internal](../../language-reference/keywords/protected-internal.md), [private](../../language-reference/keywords/private.md) o [private protected](../../language-reference/keywords/private-protected.md). 

   La definizione di una classe annidata `protected`, `protected internal` o `private protected` all'interno di un [classe sealed](../../language-reference/keywords/sealed.md), tuttavia, genera l'avviso del compilatore [CS0628](../../misc/cs0628.md): "Il nuovo membro protected è stato dichiarato nella classe sealed".
  
- I tipi annidati di uno **struct** possono essere [public](../../language-reference/keywords/public.md), [internal](../../language-reference/keywords/internal.md) o [private](../../language-reference/keywords/private.md).
  
Nell'esempio seguente, la classe `Nested` viene resa public:
  
 [!code-csharp[csProgGuideObjects#69](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#69)]  
  
 Il tipo annidato, o interno, può accedere al tipo contenitore, o esterno. Per accedere al tipo contenitore, passarlo come argomento al costruttore del tipo annidato. Ad esempio:  
  
 [!code-csharp[csProgGuideObjects#70](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#70)]  
  
 Un tipo annidato può accedere a tutti i membri accessibili al tipo contenitore. Può accedere a membri privati e protetti del tipo che li contengono, inclusi tutti i membri protetti ereditati.  
  
 Nella dichiarazione precedente il nome completo della classe `Nested` è `Container.Nested`. Questo nome viene utilizzato per creare una nuova istanza della classe annidata, come illustrato di seguito:  
  
 [!code-csharp[csProgGuideObjects#71](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#71)]  
  
## <a name="see-also"></a>Vedere anche

- [Guida per programmatori C#](../index.md)
- [Classi e struct](./index.md)
- [Modificatori di accesso](./access-modifiers.md)
- [Costruttori](./constructors.md)
