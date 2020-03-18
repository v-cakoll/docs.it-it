---
title: Come definire le costanti in C#
ms.date: 07/20/2015
helpviewer_keywords:
- C# language, constants
- constants [C#]
ms.assetid: 43f511be-346c-4b8a-995e-aded94542ece
ms.openlocfilehash: 15526655de8af6fed464376db1ac761468215210
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "75337661"
---
# <a name="how-to-define-constants-in-c"></a><span data-ttu-id="6d052-102">Come definire le costanti in C\#</span><span class="sxs-lookup"><span data-stu-id="6d052-102">How to define constants in C\#</span></span>
<span data-ttu-id="6d052-103">Le costanti sono campi i cui valori vengono impostati in fase di compilazione e non possono mai essere modificati.</span><span class="sxs-lookup"><span data-stu-id="6d052-103">Constants are fields whose values are set at compile time and can never be changed.</span></span> <span data-ttu-id="6d052-104">Usare le costanti per specificare nomi significativi invece di valori letterali numerici ("numeri chiave") per valori particolari.</span><span class="sxs-lookup"><span data-stu-id="6d052-104">Use constants to provide meaningful names instead of numeric literals ("magic numbers") for special values.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="6d052-105">In C# la direttiva per il preprocessore [#define](../../language-reference/preprocessor-directives/preprocessor-define.md) non può essere usata per definire le costanti nel modo adottato in genere in C e C++.</span><span class="sxs-lookup"><span data-stu-id="6d052-105">In C# the [#define](../../language-reference/preprocessor-directives/preprocessor-define.md) preprocessor directive cannot be used to define constants in the way that is typically used in C and C++.</span></span>  
  
 <span data-ttu-id="6d052-106">Per definire valori costanti di tipi integrali (`int`, `byte` e così via) usare un tipo enumerato.</span><span class="sxs-lookup"><span data-stu-id="6d052-106">To define constant values of integral types (`int`, `byte`, and so on) use an enumerated type.</span></span> <span data-ttu-id="6d052-107">Per altre informazioni, vedere [enum](../../language-reference/builtin-types/enum.md).</span><span class="sxs-lookup"><span data-stu-id="6d052-107">For more information, see [enum](../../language-reference/builtin-types/enum.md).</span></span>  
  
 <span data-ttu-id="6d052-108">Per definire costanti non integrali, è possibile raggrupparle in una singola classe statica denominata `Constants`.</span><span class="sxs-lookup"><span data-stu-id="6d052-108">To define non-integral constants, one approach is to group them in a single static class named `Constants`.</span></span> <span data-ttu-id="6d052-109">A questo scopo sarà necessario che tutti i riferimenti alle costanti siano preceduti dal nome della classe, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="6d052-109">This will require that all references to the constants be prefaced with the class name, as shown in the following example.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6d052-110">Esempio</span><span class="sxs-lookup"><span data-stu-id="6d052-110">Example</span></span>  
 [!code-csharp[csProgGuideObjects#89](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#89)]  
  
 <span data-ttu-id="6d052-111">L'uso del qualificatore del nome della classe consente di fare in modo che tutti gli utenti che usano la costante comprendano che si tratta di una costante e che non può essere modificata.</span><span class="sxs-lookup"><span data-stu-id="6d052-111">The use of the class name qualifier helps ensure that you and others who use the constant understand that it is constant and cannot be modified.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6d052-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6d052-112">See also</span></span>

- [<span data-ttu-id="6d052-113">Classi e struct</span><span class="sxs-lookup"><span data-stu-id="6d052-113">Classes and Structs</span></span>](./index.md)
