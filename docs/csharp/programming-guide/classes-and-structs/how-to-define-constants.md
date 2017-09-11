---
title: 'Procedura: definire le costanti in C#'
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- C# language, constants
- constants [C#]
ms.assetid: 43f511be-346c-4b8a-995e-aded94542ece
caps.latest.revision: 7
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
ms.openlocfilehash: 6c5a6f63675893eb0700afab462bf237f5639d74
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-define-constants-in-c"></a><span data-ttu-id="b5522-102">Procedura: definire le costanti in C#</span><span class="sxs-lookup"><span data-stu-id="b5522-102">How to: Define Constants in C#</span></span>
<span data-ttu-id="b5522-103">Le costanti sono campi i cui valori vengono impostati in fase di compilazione e non possono mai essere modificati.</span><span class="sxs-lookup"><span data-stu-id="b5522-103">Constants are fields whose values are set at compile time and can never be changed.</span></span> <span data-ttu-id="b5522-104">Usare le costanti per specificare nomi significativi invece di valori letterali numerici ("numeri chiave") per valori particolari.</span><span class="sxs-lookup"><span data-stu-id="b5522-104">Use constants to provide meaningful names instead of numeric literals ("magic numbers") for special values.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b5522-105">In C# la direttiva per il preprocessore [#define](../../../csharp/language-reference/preprocessor-directives/preprocessor-define.md) non può essere usata per definire le costanti nel modo adottato in genere in C e C++.</span><span class="sxs-lookup"><span data-stu-id="b5522-105">In C# the [#define](../../../csharp/language-reference/preprocessor-directives/preprocessor-define.md) preprocessor directive cannot be used to define constants in the way that is typically used in C and C++.</span></span>  
  
 <span data-ttu-id="b5522-106">Per definire valori costanti di tipi integrali (`int`, `byte` e così via) usare un tipo enumerato.</span><span class="sxs-lookup"><span data-stu-id="b5522-106">To define constant values of integral types (`int`, `byte`, and so on) use an enumerated type.</span></span> <span data-ttu-id="b5522-107">Per altre informazioni, vedere [enum](../../../csharp/language-reference/keywords/enum.md).</span><span class="sxs-lookup"><span data-stu-id="b5522-107">For more information, see [enum](../../../csharp/language-reference/keywords/enum.md).</span></span>  
  
 <span data-ttu-id="b5522-108">Per definire costanti non integrali, è possibile raggrupparle in una singola classe statica denominata `Constants`.</span><span class="sxs-lookup"><span data-stu-id="b5522-108">To define non-integral constants, one approach is to group them in a single static class named `Constants`.</span></span> <span data-ttu-id="b5522-109">A questo scopo sarà necessario che tutti i riferimenti alle costanti siano preceduti dal nome della classe, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="b5522-109">This will require that all references to the constants be prefaced with the class name, as shown in the following example.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b5522-110">Esempio</span><span class="sxs-lookup"><span data-stu-id="b5522-110">Example</span></span>  
 <span data-ttu-id="b5522-111">[!code-cs[csProgGuideObjects#89](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-define-constants_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="b5522-111">[!code-cs[csProgGuideObjects#89](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-define-constants_1.cs)]</span></span>  
  
 <span data-ttu-id="b5522-112">L'uso del qualificatore del nome della classe consente di fare in modo che tutti gli utenti che usano la costante comprendano che si tratta di una costante e che non può essere modificata.</span><span class="sxs-lookup"><span data-stu-id="b5522-112">The use of the class name qualifier helps ensure that you and others who use the constant understand that it is constant and cannot be modified.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b5522-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b5522-113">See Also</span></span>  
 [<span data-ttu-id="b5522-114">Classi e struct</span><span class="sxs-lookup"><span data-stu-id="b5522-114">Classes and Structs</span></span>](../../../csharp/programming-guide/classes-and-structs/index.md)

