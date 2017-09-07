---
title: Tipi annidati (Guida per programmatori C#)
ms.date: 2017-07-10
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- nested types [C#]
ms.assetid: f2e1b315-e3d1-48ce-977f-7bae0960ba99
caps.latest.revision: 13
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 853ec746d9be01ed63d7a229ca86e99d9f192374
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="nested-types-c-programming-guide"></a>Tipi annidati (Guida per programmatori C#)
Per tipo annidato si intende un tipo definito all'interno di una [classe](../../../csharp/language-reference/keywords/class.md) o di uno [struct](../../../csharp/language-reference/keywords/struct.md). Ad esempio:  
  
[!code-cs[csProgGuideObjects#68](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/nested-types_1.cs)]  
  
Che il tipo esterno sia una classe o uno struct, per impostazione predefinita i tipi annidati sono [private](../../../csharp/language-reference/keywords/private.md) e sono accessibili solo dal relativo tipo contenitore. Nell'esempio precedente, la classe `Nested` non è accessibile a tipi esterni. 

È possibile anche specificare un [modificatore di accesso](../../language-reference/keywords/access-modifiers.md) per definire l'accessibilità di un tipo annidato, come indicato di seguito:

- I tipi annidati di una **classe** possono essere [public](../../../csharp/language-reference/keywords/public.md), [protected](../../../csharp/language-reference/keywords/protected.md), [internal](../../../csharp/language-reference/keywords/internal.md), `protected internal` o [private](../../../csharp/language-reference/keywords/private.md). 

   La definizione di una classe annidata `protected` o `protected internal` all'interno di un [classe sealed](../../language-reference/keywords/sealed.md), tuttavia, genera l'avviso del compilatore [CS0628](../../misc/cs0628.md): "Il nuovo membro protected è stato dichiarato nella classe sealed".
  
- I tipi annidati di uno **struct** possono essere [public](../../../csharp/language-reference/keywords/public.md), [internal](../../../csharp/language-reference/keywords/internal.md) o [private](../../../csharp/language-reference/keywords/private.md).
  
Nell'esempio seguente, la classe `Nested` viene resa public:
  
[!code-cs[csProgGuideObjects#69](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/nested-types_2.cs)]  
  
 Il tipo annidato, o interno, può accedere al tipo contenitore, o esterno. Per accedere al tipo contenitore, passarlo come argomento al costruttore del tipo annidato. Ad esempio:  
  
 [!code-cs[csProgGuideObjects#70](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/nested-types_3.cs)]  
  
 Un tipo annidato può accedere a tutti i membri accessibili al tipo contenitore. Può accedere a membri privati e protetti del tipo che li contengono, inclusi tutti i membri protetti ereditati.  
  
 Nella dichiarazione precedente il nome completo della classe `Nested` è `Container.Nested`. Questo nome viene utilizzato per creare una nuova istanza della classe annidata, come illustrato di seguito:  
  
 [!code-cs[csProgGuideObjects#71](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/nested-types_4.cs)]  
  
## <a name="see-also"></a>Vedere anche  
 [Guida per programmatori C#](../../../csharp/programming-guide/index.md)   
 [Classi e struct](../../../csharp/programming-guide/classes-and-structs/index.md)   
 [Modificatori di accesso](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md)   
 [Costruttori](../../../csharp/programming-guide/classes-and-structs/constructors.md)

