---
title: Costruttori privati (Guida per programmatori C#)
ms.date: 07/20/2015
helpviewer_keywords:
- C# language, private constructors
- private constructors [C#]
ms.assetid: 29eeaa7d-8d81-453c-94b9-0e2800172621
ms.openlocfilehash: 1338a6efbe03522093899009178b6f31e558d8dd
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/16/2018
ms.locfileid: "45646996"
---
# <a name="private-constructors-c-programming-guide"></a><span data-ttu-id="cd6e2-102">Costruttori privati (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="cd6e2-102">Private Constructors (C# Programming Guide)</span></span>
<span data-ttu-id="cd6e2-103">Un costruttore privato è un costruttore di istanza speciale.</span><span class="sxs-lookup"><span data-stu-id="cd6e2-103">A private constructor is a special instance constructor.</span></span> <span data-ttu-id="cd6e2-104">Viene generalmente usato in classi contenenti solo membri statici.</span><span class="sxs-lookup"><span data-stu-id="cd6e2-104">It is generally used in classes that contain static members only.</span></span> <span data-ttu-id="cd6e2-105">Se una classe ha uno o più costruttori privati ma non include alcun costruttore pubblico, le altre classi, ad eccezione di quelle annidate, non potranno creare istanze della classe.</span><span class="sxs-lookup"><span data-stu-id="cd6e2-105">If a class has one or more private constructors and no public constructors, other classes (except nested classes) cannot create instances of this class.</span></span> <span data-ttu-id="cd6e2-106">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="cd6e2-106">For example:</span></span>  
  
 [!code-csharp[csProgGuideObjects#11](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/private-constructors_1.cs)]  
  
 <span data-ttu-id="cd6e2-107">La dichiarazione del costruttore vuoto impedisce la generazione automatica di un costruttore predefinito.</span><span class="sxs-lookup"><span data-stu-id="cd6e2-107">The declaration of the empty constructor prevents the automatic generation of a default constructor.</span></span> <span data-ttu-id="cd6e2-108">Tenere presente che se non si usa un modificatore di accesso con il costruttore, questo rimarrà di tipo privato per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="cd6e2-108">Note that if you do not use an access modifier with the constructor it will still be private by default.</span></span> <span data-ttu-id="cd6e2-109">Tuttavia, il modificatore [private](../../../csharp/language-reference/keywords/private.md) viene solitamente usato in modo esplicito per specificare che non è possibile creare un'istanza della classe.</span><span class="sxs-lookup"><span data-stu-id="cd6e2-109">However, the [private](../../../csharp/language-reference/keywords/private.md) modifier is usually used explicitly to make it clear that the class cannot be instantiated.</span></span>  
  
 <span data-ttu-id="cd6e2-110">I costruttori privati vengono usati per impedire la creazione di istanze di una classe in assenza di metodi e campi di istanza, ad esempio la classe <xref:System.Math>, oppure quando viene chiamato un metodo per ottenere un'istanza di una classe.</span><span class="sxs-lookup"><span data-stu-id="cd6e2-110">Private constructors are used to prevent creating instances of a class when there are no instance fields or methods, such as the <xref:System.Math> class, or when a method is called to obtain an instance of a class.</span></span> <span data-ttu-id="cd6e2-111">Se tutti i metodi della classe sono statici, è consigliabile rendere statica l'intera classe.</span><span class="sxs-lookup"><span data-stu-id="cd6e2-111">If all the methods in the class are static, consider making the complete class static.</span></span> <span data-ttu-id="cd6e2-112">Per altre informazioni, vedere [Classi statiche e membri di classi statiche](../../../csharp/programming-guide/classes-and-structs/static-classes-and-static-class-members.md).</span><span class="sxs-lookup"><span data-stu-id="cd6e2-112">For more information see [Static Classes and Static Class Members](../../../csharp/programming-guide/classes-and-structs/static-classes-and-static-class-members.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="cd6e2-113">Esempio</span><span class="sxs-lookup"><span data-stu-id="cd6e2-113">Example</span></span>  
 <span data-ttu-id="cd6e2-114">Di seguito è riportato l'esempio di una classe che usa un costruttore privato.</span><span class="sxs-lookup"><span data-stu-id="cd6e2-114">The following is an example of a class using a private constructor.</span></span>  
  
 [!code-csharp[csProgGuideObjects#12](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/private-constructors_2.cs)]  
  
 <span data-ttu-id="cd6e2-115">Se si rimuove il commento dall'istruzione dell'esempio riportata di seguito, verrà generato un errore poiché non è possibile accedere al costruttore a causa del livello di protezione:</span><span class="sxs-lookup"><span data-stu-id="cd6e2-115">Notice that if you uncomment the following statement from the example, it will generate an error because the constructor is inaccessible because of its protection level:</span></span>  
  
 [!code-csharp[csProgGuideObjects#13](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/private-constructors_3.cs)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="cd6e2-116">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="cd6e2-116">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="cd6e2-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cd6e2-117">See Also</span></span>

- [<span data-ttu-id="cd6e2-118">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="cd6e2-118">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="cd6e2-119">Classi e struct</span><span class="sxs-lookup"><span data-stu-id="cd6e2-119">Classes and Structs</span></span>](../../../csharp/programming-guide/classes-and-structs/index.md)  
- [<span data-ttu-id="cd6e2-120">Costruttori</span><span class="sxs-lookup"><span data-stu-id="cd6e2-120">Constructors</span></span>](../../../csharp/programming-guide/classes-and-structs/constructors.md)  
- [<span data-ttu-id="cd6e2-121">Finalizzatori</span><span class="sxs-lookup"><span data-stu-id="cd6e2-121">Finalizers</span></span>](../../../csharp/programming-guide/classes-and-structs/destructors.md)  
- [<span data-ttu-id="cd6e2-122">private</span><span class="sxs-lookup"><span data-stu-id="cd6e2-122">private</span></span>](../../../csharp/language-reference/keywords/private.md)  
- [<span data-ttu-id="cd6e2-123">public</span><span class="sxs-lookup"><span data-stu-id="cd6e2-123">public</span></span>](../../../csharp/language-reference/keywords/public.md)
