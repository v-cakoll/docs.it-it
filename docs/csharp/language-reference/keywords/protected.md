---
title: protected (Riferimenti per C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- protected
- protected_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- protected keyword [C#]
ms.assetid: 05ce3794-6675-4025-bddb-eaaa0ec22892
caps.latest.revision: 20
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: c3d24389f66edec313d4f5238b0aee02518e33b7
ms.contentlocale: it-it
ms.lasthandoff: 09/25/2017

---
# <a name="protected-c-reference"></a>protected (Riferimenti per C#)
La parola chiave `protected` è un modificatore di accesso ai membri. Un membro protetto è accessibile all'interno della classe di appartenenza e dalle istanze della classe derivata. Per un confronto di `protected` con altri modificatori di accesso, vedere [Livelli di accessibilità](../../../csharp/language-reference/keywords/accessibility-levels.md).  
  
## <a name="example"></a>Esempio  
 Un membro protetto di una classe di base è accessibile in una classe derivata solo se viene eseguito l'accesso tramite il tipo di classe derivata. Si consideri il segmento di codice di esempio seguente:  
  
 [!code-cs[csrefKeywordsModifiers#11](../../../csharp/language-reference/keywords/codesnippet/CSharp/protected_1.cs)]  
  
 L'istruzione `a.x = 10` genera un errore perché usata all'interno del metodo statico Main e non in un'istanza della classe B.  
  
 I membri struct non possono essere protetti perché struct non può essere ereditato.  
  
## <a name="example"></a>Esempio  
 In questo esempio la classe `DerivedPoint` è derivata da `Point`. Pertanto, è possibile accedere i membri protetti della classe di base direttamente dalla classe derivata.  
  
 [!code-cs[csrefKeywordsModifiers#12](../../../csharp/language-reference/keywords/codesnippet/CSharp/protected_2.cs)]  
  
 Se si impostano i livelli di accesso di `x` e `y` su [privato](../../../csharp/language-reference/keywords/private.md), il compilatore genererà i messaggi di errore seguenti:  
  
 `'Point.y' is inaccessible due to its protection level.`  
  
 `'Point.x' is inaccessible due to its protection level.`  
  
## <a name="c-language-specification"></a>Specifiche del linguaggio C#  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Riferimenti per C#](../../../csharp/language-reference/index.md)   
 [Guida per programmatori C#](../../../csharp/programming-guide/index.md)   
 [Parole chiave di C#](../../../csharp/language-reference/keywords/index.md)   
 [Modificatori di accesso](../../../csharp/language-reference/keywords/access-modifiers.md)   
 [Livelli di accessibilità](../../../csharp/language-reference/keywords/accessibility-levels.md)   
 [Modificatori](../../../csharp/language-reference/keywords/modifiers.md)   
 [public](../../../csharp/language-reference/keywords/public.md)   
 [private](../../../csharp/language-reference/keywords/private.md)   
 [internal](../../../csharp/language-reference/keywords/internal.md)

