---
title: Costruttori privati - Guida per programmatori C#
ms.date: 07/20/2015
helpviewer_keywords:
- C# language, private constructors
- private constructors [C#]
ms.assetid: 29eeaa7d-8d81-453c-94b9-0e2800172621
ms.openlocfilehash: 2f8b93fbeb7c2996f3e2683fe86f159fbfa61a92
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75705444"
---
# <a name="private-constructors-c-programming-guide"></a><span data-ttu-id="021c1-102">Costruttori privati (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="021c1-102">Private Constructors (C# Programming Guide)</span></span>
<span data-ttu-id="021c1-103">Un costruttore privato è un costruttore di istanza speciale.</span><span class="sxs-lookup"><span data-stu-id="021c1-103">A private constructor is a special instance constructor.</span></span> <span data-ttu-id="021c1-104">Viene generalmente usato in classi contenenti solo membri statici.</span><span class="sxs-lookup"><span data-stu-id="021c1-104">It is generally used in classes that contain static members only.</span></span> <span data-ttu-id="021c1-105">Se una classe ha uno o più costruttori privati ma non include alcun costruttore pubblico, le altre classi, ad eccezione di quelle annidate, non potranno creare istanze della classe.</span><span class="sxs-lookup"><span data-stu-id="021c1-105">If a class has one or more private constructors and no public constructors, other classes (except nested classes) cannot create instances of this class.</span></span> <span data-ttu-id="021c1-106">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="021c1-106">For example:</span></span>  
  
 [!code-csharp[csProgGuideObjects#11](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#11)]  
  
 <span data-ttu-id="021c1-107">La dichiarazione del costruttore vuoto impedisce la generazione automatica di un costruttore senza parametri.</span><span class="sxs-lookup"><span data-stu-id="021c1-107">The declaration of the empty constructor prevents the automatic generation of a parameterless constructor.</span></span> <span data-ttu-id="021c1-108">Tenere presente che se non si usa un modificatore di accesso con il costruttore, questo rimarrà di tipo privato per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="021c1-108">Note that if you do not use an access modifier with the constructor it will still be private by default.</span></span> <span data-ttu-id="021c1-109">Tuttavia, il modificatore [private](../../language-reference/keywords/private.md) viene solitamente usato in modo esplicito per specificare che non è possibile creare un'istanza della classe.</span><span class="sxs-lookup"><span data-stu-id="021c1-109">However, the [private](../../language-reference/keywords/private.md) modifier is usually used explicitly to make it clear that the class cannot be instantiated.</span></span>  
  
 <span data-ttu-id="021c1-110">I costruttori privati vengono usati per impedire la creazione di istanze di una classe in assenza di metodi e campi di istanza, ad esempio la classe <xref:System.Math>, oppure quando viene chiamato un metodo per ottenere un'istanza di una classe.</span><span class="sxs-lookup"><span data-stu-id="021c1-110">Private constructors are used to prevent creating instances of a class when there are no instance fields or methods, such as the <xref:System.Math> class, or when a method is called to obtain an instance of a class.</span></span> <span data-ttu-id="021c1-111">Se tutti i metodi della classe sono statici, è consigliabile rendere statica l'intera classe.</span><span class="sxs-lookup"><span data-stu-id="021c1-111">If all the methods in the class are static, consider making the complete class static.</span></span> <span data-ttu-id="021c1-112">Per altre informazioni, vedere [Classi statiche e membri di classi statiche](./static-classes-and-static-class-members.md).</span><span class="sxs-lookup"><span data-stu-id="021c1-112">For more information see [Static Classes and Static Class Members](./static-classes-and-static-class-members.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="021c1-113">Esempio</span><span class="sxs-lookup"><span data-stu-id="021c1-113">Example</span></span>  
 <span data-ttu-id="021c1-114">Di seguito è riportato l'esempio di una classe che usa un costruttore privato.</span><span class="sxs-lookup"><span data-stu-id="021c1-114">The following is an example of a class using a private constructor.</span></span>  
  
 [!code-csharp[csProgGuideObjects#12](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#12)]  
  
 <span data-ttu-id="021c1-115">Se si rimuove il commento dall'istruzione dell'esempio riportata di seguito, verrà generato un errore poiché non è possibile accedere al costruttore a causa del livello di protezione:</span><span class="sxs-lookup"><span data-stu-id="021c1-115">Notice that if you uncomment the following statement from the example, it will generate an error because the constructor is inaccessible because of its protection level:</span></span>  
  
 [!code-csharp[csProgGuideObjects#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#13)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="021c1-116">Specifica del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="021c1-116">C# Language Specification</span></span>  

<span data-ttu-id="021c1-117">Per altre informazioni, vedere [Operatore as](~/_csharplang/spec/classes.md#private-constructors) in [Specifica del linguaggio C#](/dotnet/csharp/language-reference/language-specification/introduction).</span><span class="sxs-lookup"><span data-stu-id="021c1-117">For more information, see [Private constructors](~/_csharplang/spec/classes.md#private-constructors) in the [C# Language Specification](/dotnet/csharp/language-reference/language-specification/introduction).</span></span> <span data-ttu-id="021c1-118">La specifica del linguaggio costituisce il riferimento ufficiale principale per la sintassi e l'uso di C#.</span><span class="sxs-lookup"><span data-stu-id="021c1-118">The language specification is the definitive source for C# syntax and usage.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="021c1-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="021c1-119">See also</span></span>

- [<span data-ttu-id="021c1-120">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="021c1-120">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="021c1-121">Classi e struct</span><span class="sxs-lookup"><span data-stu-id="021c1-121">Classes and Structs</span></span>](./index.md)
- [<span data-ttu-id="021c1-122">Costruttori</span><span class="sxs-lookup"><span data-stu-id="021c1-122">Constructors</span></span>](./constructors.md)
- [<span data-ttu-id="021c1-123">Finalizzatori</span><span class="sxs-lookup"><span data-stu-id="021c1-123">Finalizers</span></span>](./destructors.md)
- [<span data-ttu-id="021c1-124">private</span><span class="sxs-lookup"><span data-stu-id="021c1-124">private</span></span>](../../language-reference/keywords/private.md)
- [<span data-ttu-id="021c1-125">public</span><span class="sxs-lookup"><span data-stu-id="021c1-125">public</span></span>](../../language-reference/keywords/public.md)
