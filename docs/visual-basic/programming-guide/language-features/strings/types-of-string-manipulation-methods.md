---
title: Tipi di metodi per la gestione delle stringhe in Visual Basic
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- strings [Visual Basic], manipulating [Visual Basic]
- string manipulation
ms.assetid: 905055cd-7f50-48fb-9eed-b0995af1dc1f
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: b437be4a6f4a0cc9d5a4d21291a80c9cb8fffcd3
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="types-of-string-manipulation-methods-in-visual-basic"></a><span data-ttu-id="79b0f-102">Tipi di metodi per la gestione delle stringhe in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="79b0f-102">Types of String Manipulation Methods in Visual Basic</span></span>
<span data-ttu-id="79b0f-103">Esistono diversi modi per analizzare e modificare le stringhe.</span><span class="sxs-lookup"><span data-stu-id="79b0f-103">There are several different ways to analyze and manipulate your strings.</span></span> <span data-ttu-id="79b0f-104">Alcuni dei metodi fanno parte di [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] language, mentre altri sono inerenti la `String` classe.</span><span class="sxs-lookup"><span data-stu-id="79b0f-104">Some of the methods are a part of the [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] language, and others are inherent in the `String` class.</span></span>  
  
## <a name="visual-basic-language-and-the-net-framework"></a><span data-ttu-id="79b0f-105">Linguaggio Visual Basic e .NET Framework</span><span class="sxs-lookup"><span data-stu-id="79b0f-105">Visual Basic Language and the .NET Framework</span></span>  
 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]<span data-ttu-id="79b0f-106">metodi vengono utilizzati come funzioni intrinseche del linguaggio.</span><span class="sxs-lookup"><span data-stu-id="79b0f-106"> methods are used as inherent functions of the language.</span></span> <span data-ttu-id="79b0f-107">Essi possono essere utilizzati senza qualifica nel codice.</span><span class="sxs-lookup"><span data-stu-id="79b0f-107">They may be used without qualification in your code.</span></span> <span data-ttu-id="79b0f-108">Nell'esempio seguente viene illustrato un utilizzo tipico di un [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] comando di modifica di stringhe:</span><span class="sxs-lookup"><span data-stu-id="79b0f-108">The following example shows typical use of a [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] string-manipulation command:</span></span>  
  
 [!code-vb[VbVbalrStrings#44](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/types-of-string-manipulation-methods_1.vb)]  
  
 <span data-ttu-id="79b0f-109">In questo esempio, il `Mid` funzione esegue un'operazione diretta su `aString` e assegna il valore a `bString`.</span><span class="sxs-lookup"><span data-stu-id="79b0f-109">In this example, the `Mid` function performs a direct operation on `aString` and assigns the value to `bString`.</span></span>  
  
 <span data-ttu-id="79b0f-110">Per un elenco di metodi di modifica stringa Visual Basic, vedere [String Manipulation Summary](../../../../visual-basic/language-reference/keywords/string-manipulation-summary.md).</span><span class="sxs-lookup"><span data-stu-id="79b0f-110">For a list of Visual Basic string manipulation methods, see [String Manipulation Summary](../../../../visual-basic/language-reference/keywords/string-manipulation-summary.md).</span></span>  
  
### <a name="shared-methods-and-instance-methods"></a><span data-ttu-id="79b0f-111">I metodi condivisi e metodi di istanza</span><span class="sxs-lookup"><span data-stu-id="79b0f-111">Shared Methods and Instance Methods</span></span>  
 <span data-ttu-id="79b0f-112">È inoltre possibile modificare le stringhe con i metodi del `String` classe.</span><span class="sxs-lookup"><span data-stu-id="79b0f-112">You can also manipulate strings with the methods of the `String` class.</span></span> <span data-ttu-id="79b0f-113">Esistono due tipi di metodi in `String`: *condivisa* metodi e *istanza* metodi.</span><span class="sxs-lookup"><span data-stu-id="79b0f-113">There are two types of methods in `String`: *shared* methods and *instance* methods.</span></span>  
  
#### <a name="shared-methods"></a><span data-ttu-id="79b0f-114">Metodi condivisi</span><span class="sxs-lookup"><span data-stu-id="79b0f-114">Shared Methods</span></span>  
 <span data-ttu-id="79b0f-115">Un metodo condiviso è un metodo che deriva dalla `String` classe stessa e non richiede un'istanza di tale classe per funzionare.</span><span class="sxs-lookup"><span data-stu-id="79b0f-115">A shared method is a method that stems from the `String` class itself and does not require an instance of that class to work.</span></span> <span data-ttu-id="79b0f-116">Questi metodi possono essere qualificati con il nome della classe (`String`) anziché con un'istanza di `String` classe.</span><span class="sxs-lookup"><span data-stu-id="79b0f-116">These methods can be qualified with the name of the class (`String`) rather than with an instance of the `String` class.</span></span> <span data-ttu-id="79b0f-117">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="79b0f-117">For example:</span></span>  
  
 [!code-vb[VbVbalrStrings#45](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/types-of-string-manipulation-methods_2.vb)]  
  
 <span data-ttu-id="79b0f-118">Nell'esempio precedente, il <xref:System.String.Copy%2A?displayProperty=nameWithType> è un metodo statico, che agisce su un'espressione fornita e assegna il valore risulta a `bString`.</span><span class="sxs-lookup"><span data-stu-id="79b0f-118">In the preceding example, the <xref:System.String.Copy%2A?displayProperty=nameWithType> method is a static method, which acts upon an expression it is given and assigns the resulting value to `bString`.</span></span>  
  
#### <a name="instance-methods"></a><span data-ttu-id="79b0f-119">Metodi di istanza</span><span class="sxs-lookup"><span data-stu-id="79b0f-119">Instance Methods</span></span>  
 <span data-ttu-id="79b0f-120">Metodi di istanza, invece, hanno origine da una particolare istanza di `String` e deve essere qualificato con il nome dell'istanza.</span><span class="sxs-lookup"><span data-stu-id="79b0f-120">Instance methods, by contrast, stem from a particular instance of `String` and must be qualified with the instance name.</span></span> <span data-ttu-id="79b0f-121">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="79b0f-121">For example:</span></span>  
  
 [!code-vb[VbVbalrStrings#46](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/types-of-string-manipulation-methods_3.vb)]  
  
 <span data-ttu-id="79b0f-122">In questo esempio, il <xref:System.String.Substring%2A?displayProperty=nameWithType> è un metodo di istanza di `String` (vale a dire `aString`).</span><span class="sxs-lookup"><span data-stu-id="79b0f-122">In this example, the <xref:System.String.Substring%2A?displayProperty=nameWithType> method is a method of the instance of `String` (that is, `aString`).</span></span> <span data-ttu-id="79b0f-123">Esegue un'operazione su `aString` e assegna tale valore per `bString`.</span><span class="sxs-lookup"><span data-stu-id="79b0f-123">It performs an operation on `aString` and assigns that value to `bString`.</span></span>  
  
 <span data-ttu-id="79b0f-124">Per ulteriori informazioni, vedere la documentazione per la <xref:System.String> classe.</span><span class="sxs-lookup"><span data-stu-id="79b0f-124">For more information, see the documentation for the <xref:System.String> class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="79b0f-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="79b0f-125">See Also</span></span>  
 [<span data-ttu-id="79b0f-126">Introduzione alle stringhe in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="79b0f-126">Introduction to Strings in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md)
