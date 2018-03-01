---
title: Tipi annidati (Guida per programmatori C#)
ms.date: 07/10/2017
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
helpviewer_keywords:
- nested types [C#]
ms.assetid: f2e1b315-e3d1-48ce-977f-7bae0960ba99
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: ab13c68b638062ab89c90dbfc51b51b8d72d3bde
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="nested-types-c-programming-guide"></a>Tipi annidati (Guida per programmatori C#)
Per tipo annidato si intende un tipo definito all'interno di una [classe](../../../csharp/language-reference/keywords/class.md) o di uno [struct](../../../csharp/language-reference/keywords/struct.md). Ad esempio:  
  
[!code-csharp[csProgGuideObjects#68](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/nested-types_1.cs)]  
  
Che il tipo esterno sia una classe o uno struct, per impostazione predefinita i tipi annidati sono [private](../../../csharp/language-reference/keywords/private.md) e sono accessibili solo dal relativo tipo contenitore. Nell'esempio precedente, la classe `Nested` non è accessibile a tipi esterni. 

È possibile anche specificare un [modificatore di accesso](../../language-reference/keywords/access-modifiers.md) per definire l'accessibilità di un tipo annidato, come indicato di seguito:

- Annidati di tipi di un **classe** può essere [pubblica](../../../csharp/language-reference/keywords/public.md), [protetti](../../../csharp/language-reference/keywords/protected.md), [interno](../../../csharp/language-reference/keywords/internal.md), [protected internal](../../../csharp/language-reference/keywords/protected-internal.md), [privata](../../../csharp/language-reference/keywords/private.md) o [protetto privato](../../../csharp/language-reference/keywords/private-protected.md). 

   Tuttavia, la definizione di un `protected`, `protected internal` o `private protected` annidati classe all'interno di un [classe sealed](../../language-reference/keywords/sealed.md) genera l'avviso del compilatore [CS0628](../../misc/cs0628.md), "nuovo membro protetto dichiarato nella classe sealed".
  
- I tipi annidati di uno **struct** possono essere [public](../../../csharp/language-reference/keywords/public.md), [internal](../../../csharp/language-reference/keywords/internal.md) o [private](../../../csharp/language-reference/keywords/private.md).
  
Nell'esempio seguente, la classe `Nested` viene resa public:
  
[!code-csharp[csProgGuideObjects#69](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/nested-types_2.cs)]  
  
 Il tipo annidato, o interno, può accedere al tipo contenitore, o esterno. Per accedere al tipo contenitore, passarlo come argomento al costruttore del tipo annidato. Ad esempio:  
  
 [!code-csharp[csProgGuideObjects#70](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/nested-types_3.cs)]  
  
 Un tipo annidato può accedere a tutti i membri accessibili al tipo contenitore. Può accedere a membri privati e protetti del tipo che li contengono, inclusi tutti i membri protetti ereditati.  
  
 Nella dichiarazione precedente il nome completo della classe `Nested` è `Container.Nested`. Questo nome viene utilizzato per creare una nuova istanza della classe annidata, come illustrato di seguito:  
  
 [!code-csharp[csProgGuideObjects#71](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/nested-types_4.cs)]  
  
## <a name="see-also"></a>Vedere anche  
 [Guida per programmatori C#](../../../csharp/programming-guide/index.md)  
 [Classi e struct](../../../csharp/programming-guide/classes-and-structs/index.md)  
 [Modificatori di accesso](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md)  
 [Costruttori](../../../csharp/programming-guide/classes-and-structs/constructors.md)
