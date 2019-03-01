---
title: Tipi di metodi per la gestione delle stringhe in Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- strings [Visual Basic], manipulating [Visual Basic]
- string manipulation
ms.assetid: 905055cd-7f50-48fb-9eed-b0995af1dc1f
ms.openlocfilehash: a75984d0eb64ef8c18def3ae59d5e1f4b6d20ce2
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2019
ms.locfileid: "56980342"
---
# <a name="types-of-string-manipulation-methods-in-visual-basic"></a><span data-ttu-id="dd765-102">Tipi di metodi per la gestione delle stringhe in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="dd765-102">Types of String Manipulation Methods in Visual Basic</span></span>
<span data-ttu-id="dd765-103">Esistono diversi modi per analizzare e modificare le stringhe.</span><span class="sxs-lookup"><span data-stu-id="dd765-103">There are several different ways to analyze and manipulate your strings.</span></span> <span data-ttu-id="dd765-104">Alcuni metodi fanno parte del linguaggio Visual Basic e altri sono intrinseci di `String` classe.</span><span class="sxs-lookup"><span data-stu-id="dd765-104">Some of the methods are a part of the Visual Basic language, and others are inherent in the `String` class.</span></span>  
  
## <a name="visual-basic-language-and-the-net-framework"></a><span data-ttu-id="dd765-105">Linguaggio Visual Basic e .NET Framework</span><span class="sxs-lookup"><span data-stu-id="dd765-105">Visual Basic Language and the .NET Framework</span></span>  
 <span data-ttu-id="dd765-106">Metodi di Visual Basic vengono utilizzati come funzioni intrinseche del linguaggio.</span><span class="sxs-lookup"><span data-stu-id="dd765-106">Visual Basic methods are used as inherent functions of the language.</span></span> <span data-ttu-id="dd765-107">Essi possono essere utilizzati senza qualifica nel codice.</span><span class="sxs-lookup"><span data-stu-id="dd765-107">They may be used without qualification in your code.</span></span> <span data-ttu-id="dd765-108">Nell'esempio seguente viene illustrato l'utilizzo tipico di un comando di modifica di stringhe Visual Basic:</span><span class="sxs-lookup"><span data-stu-id="dd765-108">The following example shows typical use of a Visual Basic string-manipulation command:</span></span>  
  
 [!code-vb[VbVbalrStrings#44](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#44)]  
  
 <span data-ttu-id="dd765-109">In questo esempio, il `Mid` funzione esegue un'operazione diretta sugli `aString` e assegna il valore da `bString`.</span><span class="sxs-lookup"><span data-stu-id="dd765-109">In this example, the `Mid` function performs a direct operation on `aString` and assigns the value to `bString`.</span></span>  
  
 <span data-ttu-id="dd765-110">Per un elenco di metodi di modifica di stringhe Visual Basic, vedere [riepilogo della modifica delle stringhe](../../../../visual-basic/language-reference/keywords/string-manipulation-summary.md).</span><span class="sxs-lookup"><span data-stu-id="dd765-110">For a list of Visual Basic string manipulation methods, see [String Manipulation Summary](../../../../visual-basic/language-reference/keywords/string-manipulation-summary.md).</span></span>  
  
### <a name="shared-methods-and-instance-methods"></a><span data-ttu-id="dd765-111">I metodi condivisi e metodi di istanza</span><span class="sxs-lookup"><span data-stu-id="dd765-111">Shared Methods and Instance Methods</span></span>  
 <span data-ttu-id="dd765-112">È inoltre possibile modificare le stringhe con i metodi del `String` classe.</span><span class="sxs-lookup"><span data-stu-id="dd765-112">You can also manipulate strings with the methods of the `String` class.</span></span> <span data-ttu-id="dd765-113">Esistono due tipi di metodi `String`: *condivisa* metodi e *istanza* metodi.</span><span class="sxs-lookup"><span data-stu-id="dd765-113">There are two types of methods in `String`: *shared* methods and *instance* methods.</span></span>  
  
#### <a name="shared-methods"></a><span data-ttu-id="dd765-114">Metodi condivisi</span><span class="sxs-lookup"><span data-stu-id="dd765-114">Shared Methods</span></span>  
 <span data-ttu-id="dd765-115">Un metodo condiviso è un metodo che deriva dal `String` classe stessa e non richiede un'istanza di tale classe per funzionare.</span><span class="sxs-lookup"><span data-stu-id="dd765-115">A shared method is a method that stems from the `String` class itself and does not require an instance of that class to work.</span></span> <span data-ttu-id="dd765-116">Questi metodi possono essere qualificati con il nome della classe (`String`) anziché con un'istanza del `String` classe.</span><span class="sxs-lookup"><span data-stu-id="dd765-116">These methods can be qualified with the name of the class (`String`) rather than with an instance of the `String` class.</span></span> <span data-ttu-id="dd765-117">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="dd765-117">For example:</span></span>  
  
 [!code-vb[VbVbalrStrings#45](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#45)]  
  
 <span data-ttu-id="dd765-118">Nell'esempio precedente, il <xref:System.String.Copy%2A?displayProperty=nameWithType> è un metodo statico, che agisce su un'espressione fornita e assegna il valore risultante a `bString`.</span><span class="sxs-lookup"><span data-stu-id="dd765-118">In the preceding example, the <xref:System.String.Copy%2A?displayProperty=nameWithType> method is a static method, which acts upon an expression it is given and assigns the resulting value to `bString`.</span></span>  
  
#### <a name="instance-methods"></a><span data-ttu-id="dd765-119">Metodi di istanza</span><span class="sxs-lookup"><span data-stu-id="dd765-119">Instance Methods</span></span>  
 <span data-ttu-id="dd765-120">Metodi di istanza, invece, hanno origine da una particolare istanza di `String` e deve essere qualificato con il nome dell'istanza.</span><span class="sxs-lookup"><span data-stu-id="dd765-120">Instance methods, by contrast, stem from a particular instance of `String` and must be qualified with the instance name.</span></span> <span data-ttu-id="dd765-121">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="dd765-121">For example:</span></span>  
  
 [!code-vb[VbVbalrStrings#46](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#46)]  
  
 <span data-ttu-id="dd765-122">In questo esempio, il <xref:System.String.Substring%2A?displayProperty=nameWithType> è un metodo dell'istanza di `String` (vale a dire `aString`).</span><span class="sxs-lookup"><span data-stu-id="dd765-122">In this example, the <xref:System.String.Substring%2A?displayProperty=nameWithType> method is a method of the instance of `String` (that is, `aString`).</span></span> <span data-ttu-id="dd765-123">Esegue un'operazione sulla `aString` e assegna tale valore a `bString`.</span><span class="sxs-lookup"><span data-stu-id="dd765-123">It performs an operation on `aString` and assigns that value to `bString`.</span></span>  
  
 <span data-ttu-id="dd765-124">Per altre informazioni, vedere la documentazione per il <xref:System.String> classe.</span><span class="sxs-lookup"><span data-stu-id="dd765-124">For more information, see the documentation for the <xref:System.String> class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dd765-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="dd765-125">See also</span></span>
- [<span data-ttu-id="dd765-126">Introduzione alle stringhe in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="dd765-126">Introduction to Strings in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md)
