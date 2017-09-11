---
title: Costruttori privati (Guida per programmatori C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- C# language, private constructors
- private constructors [C#]
ms.assetid: 29eeaa7d-8d81-453c-94b9-0e2800172621
caps.latest.revision: 19
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
ms.openlocfilehash: 1ccd3db5f95e3a237bb37d9e09c34f415fcfd752
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="private-constructors-c-programming-guide"></a><span data-ttu-id="622f4-102">Costruttori privati (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="622f4-102">Private Constructors (C# Programming Guide)</span></span>
<span data-ttu-id="622f4-103">Un costruttore privato è un costruttore di istanza speciale.</span><span class="sxs-lookup"><span data-stu-id="622f4-103">A private constructor is a special instance constructor.</span></span> <span data-ttu-id="622f4-104">Viene generalmente usato in classi contenenti solo membri statici.</span><span class="sxs-lookup"><span data-stu-id="622f4-104">It is generally used in classes that contain static members only.</span></span> <span data-ttu-id="622f4-105">Se una classe ha uno o più costruttori privati ma non include alcun costruttore pubblico, le altre classi, ad eccezione di quelle annidate, non potranno creare istanze della classe.</span><span class="sxs-lookup"><span data-stu-id="622f4-105">If a class has one or more private constructors and no public constructors, other classes (except nested classes) cannot create instances of this class.</span></span> <span data-ttu-id="622f4-106">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="622f4-106">For example:</span></span>  
  
 <span data-ttu-id="622f4-107">[!code-cs[csProgGuideObjects#11](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/private-constructors_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="622f4-107">[!code-cs[csProgGuideObjects#11](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/private-constructors_1.cs)]</span></span>  
  
 <span data-ttu-id="622f4-108">La dichiarazione del costruttore vuoto impedisce la generazione automatica di un costruttore predefinito.</span><span class="sxs-lookup"><span data-stu-id="622f4-108">The declaration of the empty constructor prevents the automatic generation of a default constructor.</span></span> <span data-ttu-id="622f4-109">Tenere presente che se non si usa un modificatore di accesso con il costruttore, questo rimarrà di tipo privato per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="622f4-109">Note that if you do not use an access modifier with the constructor it will still be private by default.</span></span> <span data-ttu-id="622f4-110">Tuttavia, il modificatore [private](../../../csharp/language-reference/keywords/private.md) viene solitamente usato in modo esplicito per specificare che non è possibile creare un'istanza della classe.</span><span class="sxs-lookup"><span data-stu-id="622f4-110">However, the [private](../../../csharp/language-reference/keywords/private.md) modifier is usually used explicitly to make it clear that the class cannot be instantiated.</span></span>  
  
 <span data-ttu-id="622f4-111">I costruttori privati vengono usati per impedire la creazione di istanze di una classe in assenza di metodi e campi di istanza, ad esempio la classe <xref:System.Math>, oppure quando viene chiamato un metodo per ottenere un'istanza di una classe.</span><span class="sxs-lookup"><span data-stu-id="622f4-111">Private constructors are used to prevent creating instances of a class when there are no instance fields or methods, such as the <xref:System.Math> class, or when a method is called to obtain an instance of a class.</span></span> <span data-ttu-id="622f4-112">Se tutti i metodi della classe sono statici, è consigliabile rendere statica l'intera classe.</span><span class="sxs-lookup"><span data-stu-id="622f4-112">If all the methods in the class are static, consider making the complete class static.</span></span> <span data-ttu-id="622f4-113">Per altre informazioni, vedere [Classi statiche e membri di classi statiche](../../../csharp/programming-guide/classes-and-structs/static-classes-and-static-class-members.md).</span><span class="sxs-lookup"><span data-stu-id="622f4-113">For more information see [Static Classes and Static Class Members](../../../csharp/programming-guide/classes-and-structs/static-classes-and-static-class-members.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="622f4-114">Esempio</span><span class="sxs-lookup"><span data-stu-id="622f4-114">Example</span></span>  
 <span data-ttu-id="622f4-115">Di seguito è riportato l'esempio di una classe che usa un costruttore privato.</span><span class="sxs-lookup"><span data-stu-id="622f4-115">The following is an example of a class using a private constructor.</span></span>  
  
 <span data-ttu-id="622f4-116">[!code-cs[csProgGuideObjects#12](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/private-constructors_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="622f4-116">[!code-cs[csProgGuideObjects#12](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/private-constructors_2.cs)]</span></span>  
  
 <span data-ttu-id="622f4-117">Se si rimuove il commento dall'istruzione dell'esempio riportata di seguito, verrà generato un errore poiché non è possibile accedere al costruttore a causa del livello di protezione:</span><span class="sxs-lookup"><span data-stu-id="622f4-117">Notice that if you uncomment the following statement from the example, it will generate an error because the constructor is inaccessible because of its protection level:</span></span>  
  
 <span data-ttu-id="622f4-118">[!code-cs[csProgGuideObjects#13](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/private-constructors_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="622f4-118">[!code-cs[csProgGuideObjects#13](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/private-constructors_3.cs)]</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="622f4-119">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="622f4-119">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="622f4-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="622f4-120">See Also</span></span>  
 <span data-ttu-id="622f4-121">[Guida per programmatori C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="622f4-121">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="622f4-122">[Classi e struct](../../../csharp/programming-guide/classes-and-structs/index.md) </span><span class="sxs-lookup"><span data-stu-id="622f4-122">[Classes and Structs](../../../csharp/programming-guide/classes-and-structs/index.md) </span></span>  
 <span data-ttu-id="622f4-123">[Costruttori](../../../csharp/programming-guide/classes-and-structs/constructors.md) </span><span class="sxs-lookup"><span data-stu-id="622f4-123">[Constructors](../../../csharp/programming-guide/classes-and-structs/constructors.md) </span></span>  
 <span data-ttu-id="622f4-124">[Finalizzatori](../../../csharp/programming-guide/classes-and-structs/destructors.md) </span><span class="sxs-lookup"><span data-stu-id="622f4-124">[Finalizers](../../../csharp/programming-guide/classes-and-structs/destructors.md) </span></span>  
 <span data-ttu-id="622f4-125">[private](../../../csharp/language-reference/keywords/private.md) </span><span class="sxs-lookup"><span data-stu-id="622f4-125">[private](../../../csharp/language-reference/keywords/private.md) </span></span>  
 [<span data-ttu-id="622f4-126">public</span><span class="sxs-lookup"><span data-stu-id="622f4-126">public</span></span>](../../../csharp/language-reference/keywords/public.md)

