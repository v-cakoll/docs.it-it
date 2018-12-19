---
title: Costruttori privati - Guida per programmatori C#
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- C# language, private constructors
- private constructors [C#]
ms.assetid: 29eeaa7d-8d81-453c-94b9-0e2800172621
ms.openlocfilehash: a0ff8f69f7725b40eaac01acef74857c2a99247c
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/11/2018
ms.locfileid: "53240502"
---
# <a name="private-constructors-c-programming-guide"></a><span data-ttu-id="a81e9-102">Costruttori privati (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="a81e9-102">Private Constructors (C# Programming Guide)</span></span>
<span data-ttu-id="a81e9-103">Un costruttore privato è un costruttore di istanza speciale.</span><span class="sxs-lookup"><span data-stu-id="a81e9-103">A private constructor is a special instance constructor.</span></span> <span data-ttu-id="a81e9-104">Viene generalmente usato in classi contenenti solo membri statici.</span><span class="sxs-lookup"><span data-stu-id="a81e9-104">It is generally used in classes that contain static members only.</span></span> <span data-ttu-id="a81e9-105">Se una classe ha uno o più costruttori privati ma non include alcun costruttore pubblico, le altre classi, ad eccezione di quelle annidate, non potranno creare istanze della classe.</span><span class="sxs-lookup"><span data-stu-id="a81e9-105">If a class has one or more private constructors and no public constructors, other classes (except nested classes) cannot create instances of this class.</span></span> <span data-ttu-id="a81e9-106">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="a81e9-106">For example:</span></span>  
  
 [!code-csharp[csProgGuideObjects#11](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/private-constructors_1.cs)]  
  
 <span data-ttu-id="a81e9-107">La dichiarazione del costruttore vuoto impedisce la generazione automatica di un costruttore predefinito.</span><span class="sxs-lookup"><span data-stu-id="a81e9-107">The declaration of the empty constructor prevents the automatic generation of a default constructor.</span></span> <span data-ttu-id="a81e9-108">Tenere presente che se non si usa un modificatore di accesso con il costruttore, questo rimarrà di tipo privato per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="a81e9-108">Note that if you do not use an access modifier with the constructor it will still be private by default.</span></span> <span data-ttu-id="a81e9-109">Tuttavia, il modificatore [private](../../../csharp/language-reference/keywords/private.md) viene solitamente usato in modo esplicito per specificare che non è possibile creare un'istanza della classe.</span><span class="sxs-lookup"><span data-stu-id="a81e9-109">However, the [private](../../../csharp/language-reference/keywords/private.md) modifier is usually used explicitly to make it clear that the class cannot be instantiated.</span></span>  
  
 <span data-ttu-id="a81e9-110">I costruttori privati vengono usati per impedire la creazione di istanze di una classe in assenza di metodi e campi di istanza, ad esempio la classe <xref:System.Math>, oppure quando viene chiamato un metodo per ottenere un'istanza di una classe.</span><span class="sxs-lookup"><span data-stu-id="a81e9-110">Private constructors are used to prevent creating instances of a class when there are no instance fields or methods, such as the <xref:System.Math> class, or when a method is called to obtain an instance of a class.</span></span> <span data-ttu-id="a81e9-111">Se tutti i metodi della classe sono statici, è consigliabile rendere statica l'intera classe.</span><span class="sxs-lookup"><span data-stu-id="a81e9-111">If all the methods in the class are static, consider making the complete class static.</span></span> <span data-ttu-id="a81e9-112">Per altre informazioni, vedere [Classi statiche e membri di classi statiche](../../../csharp/programming-guide/classes-and-structs/static-classes-and-static-class-members.md).</span><span class="sxs-lookup"><span data-stu-id="a81e9-112">For more information see [Static Classes and Static Class Members](../../../csharp/programming-guide/classes-and-structs/static-classes-and-static-class-members.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="a81e9-113">Esempio</span><span class="sxs-lookup"><span data-stu-id="a81e9-113">Example</span></span>  
 <span data-ttu-id="a81e9-114">Di seguito è riportato l'esempio di una classe che usa un costruttore privato.</span><span class="sxs-lookup"><span data-stu-id="a81e9-114">The following is an example of a class using a private constructor.</span></span>  
  
 [!code-csharp[csProgGuideObjects#12](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/private-constructors_2.cs)]  
  
 <span data-ttu-id="a81e9-115">Se si rimuove il commento dall'istruzione dell'esempio riportata di seguito, verrà generato un errore poiché non è possibile accedere al costruttore a causa del livello di protezione:</span><span class="sxs-lookup"><span data-stu-id="a81e9-115">Notice that if you uncomment the following statement from the example, it will generate an error because the constructor is inaccessible because of its protection level:</span></span>  
  
 [!code-csharp[csProgGuideObjects#13](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/private-constructors_3.cs)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="a81e9-116">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="a81e9-116">C# Language Specification</span></span>  

<span data-ttu-id="a81e9-117">Per altre informazioni, vedere [Operatore as](~/_csharplang/spec/classes.md#private-constructors) in [Specifica del linguaggio C#](../../language-reference/language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="a81e9-117">For more information, see [Private constructors](~/_csharplang/spec/classes.md#private-constructors) in the [C# Language Specification](../../language-reference/language-specification/index.md).</span></span> <span data-ttu-id="a81e9-118">La specifica del linguaggio costituisce il riferimento ufficiale principale per la sintassi e l'uso di C#.</span><span class="sxs-lookup"><span data-stu-id="a81e9-118">The language specification is the definitive source for C# syntax and usage.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="a81e9-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a81e9-119">See Also</span></span>

- [<span data-ttu-id="a81e9-120">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="a81e9-120">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="a81e9-121">Classi e struct</span><span class="sxs-lookup"><span data-stu-id="a81e9-121">Classes and Structs</span></span>](../../../csharp/programming-guide/classes-and-structs/index.md)  
- [<span data-ttu-id="a81e9-122">Costruttori</span><span class="sxs-lookup"><span data-stu-id="a81e9-122">Constructors</span></span>](../../../csharp/programming-guide/classes-and-structs/constructors.md)  
- [<span data-ttu-id="a81e9-123">Finalizzatori</span><span class="sxs-lookup"><span data-stu-id="a81e9-123">Finalizers</span></span>](../../../csharp/programming-guide/classes-and-structs/destructors.md)  
- [<span data-ttu-id="a81e9-124">private</span><span class="sxs-lookup"><span data-stu-id="a81e9-124">private</span></span>](../../../csharp/language-reference/keywords/private.md)  
- [<span data-ttu-id="a81e9-125">public</span><span class="sxs-lookup"><span data-stu-id="a81e9-125">public</span></span>](../../../csharp/language-reference/keywords/public.md)
