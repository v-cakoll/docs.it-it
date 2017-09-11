---
title: Tipi di metodi di manipolazione delle stringhe in Visual Basic | Documenti di Microsoft
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- strings [Visual Basic], manipulating [Visual Basic]
- string manipulation
ms.assetid: 905055cd-7f50-48fb-9eed-b0995af1dc1f
caps.latest.revision: 12
author: dotnet-bot
ms.author: dotnetcontent
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 9c63ad0931ae2f3760576a792795b9fe0ab6a409
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="types-of-string-manipulation-methods-in-visual-basic"></a><span data-ttu-id="cfd0a-102">Tipi di metodi per la gestione delle stringhe in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="cfd0a-102">Types of String Manipulation Methods in Visual Basic</span></span>
<span data-ttu-id="cfd0a-103">Esistono diversi modi per analizzare e modificare le stringhe.</span><span class="sxs-lookup"><span data-stu-id="cfd0a-103">There are several different ways to analyze and manipulate your strings.</span></span> <span data-ttu-id="cfd0a-104">Alcuni metodi fanno parte del [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] language altri sono inerenti la `String` classe.</span><span class="sxs-lookup"><span data-stu-id="cfd0a-104">Some of the methods are a part of the [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] language, and others are inherent in the `String` class.</span></span>  
  
## <a name="visual-basic-language-and-the-net-framework"></a><span data-ttu-id="cfd0a-105">Linguaggio Visual Basic e .NET Framework</span><span class="sxs-lookup"><span data-stu-id="cfd0a-105">Visual Basic Language and the .NET Framework</span></span>  
 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]<span data-ttu-id="cfd0a-106">metodi vengono utilizzati come funzioni intrinseche del linguaggio.</span><span class="sxs-lookup"><span data-stu-id="cfd0a-106"> methods are used as inherent functions of the language.</span></span> <span data-ttu-id="cfd0a-107">Essi possono essere utilizzati senza qualifica nel codice.</span><span class="sxs-lookup"><span data-stu-id="cfd0a-107">They may be used without qualification in your code.</span></span> <span data-ttu-id="cfd0a-108">Nell'esempio seguente viene illustrato l'utilizzo tipico di un [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] comando di modifica di stringhe:</span><span class="sxs-lookup"><span data-stu-id="cfd0a-108">The following example shows typical use of a [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] string-manipulation command:</span></span>  
  
 <span data-ttu-id="cfd0a-109">[!code-vb[VbVbalrStrings&#44;](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/types-of-string-manipulation-methods_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="cfd0a-109">[!code-vb[VbVbalrStrings#44](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/types-of-string-manipulation-methods_1.vb)]</span></span>  
  
 <span data-ttu-id="cfd0a-110">In questo esempio, il `Mid` funzione esegue un'operazione diretta su `aString` e assegna il valore a `bString`.</span><span class="sxs-lookup"><span data-stu-id="cfd0a-110">In this example, the `Mid` function performs a direct operation on `aString` and assigns the value to `bString`.</span></span>  
  
 <span data-ttu-id="cfd0a-111">Per un elenco di metodi di manipolazione di stringhe di Visual Basic, vedere [String Manipulation Summary](../../../../visual-basic/language-reference/keywords/string-manipulation-summary.md).</span><span class="sxs-lookup"><span data-stu-id="cfd0a-111">For a list of Visual Basic string manipulation methods, see [String Manipulation Summary](../../../../visual-basic/language-reference/keywords/string-manipulation-summary.md).</span></span>  
  
### <a name="shared-methods-and-instance-methods"></a><span data-ttu-id="cfd0a-112">Metodi condivisi e metodi di istanza</span><span class="sxs-lookup"><span data-stu-id="cfd0a-112">Shared Methods and Instance Methods</span></span>  
 <span data-ttu-id="cfd0a-113">È inoltre possibile modificare le stringhe con i metodi della `String` classe.</span><span class="sxs-lookup"><span data-stu-id="cfd0a-113">You can also manipulate strings with the methods of the `String` class.</span></span> <span data-ttu-id="cfd0a-114">Esistono due tipi di metodi in `String`: *condivisa* metodi e *istanza* metodi.</span><span class="sxs-lookup"><span data-stu-id="cfd0a-114">There are two types of methods in `String`: *shared* methods and *instance* methods.</span></span>  
  
#### <a name="shared-methods"></a><span data-ttu-id="cfd0a-115">Metodi condivisi</span><span class="sxs-lookup"><span data-stu-id="cfd0a-115">Shared Methods</span></span>  
 <span data-ttu-id="cfd0a-116">Un metodo condiviso è un metodo che deriva dalla `String` classe stessa e non richiede un'istanza di tale classe per funzionare.</span><span class="sxs-lookup"><span data-stu-id="cfd0a-116">A shared method is a method that stems from the `String` class itself and does not require an instance of that class to work.</span></span> <span data-ttu-id="cfd0a-117">Questi metodi possono essere qualificati con il nome della classe (`String`) anziché con un'istanza di `String` (classe).</span><span class="sxs-lookup"><span data-stu-id="cfd0a-117">These methods can be qualified with the name of the class (`String`) rather than with an instance of the `String` class.</span></span> <span data-ttu-id="cfd0a-118">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="cfd0a-118">For example:</span></span>  
  
 <span data-ttu-id="cfd0a-119">[!code-vb[N. VbVbalrStrings&45;](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/types-of-string-manipulation-methods_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="cfd0a-119">[!code-vb[VbVbalrStrings#45](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/types-of-string-manipulation-methods_2.vb)]</span></span>  
  
 <span data-ttu-id="cfd0a-120">Nell'esempio precedente, il <xref:System.String.Copy%2A?displayProperty=fullName>è un metodo statico, che agisce su un'espressione fornita e assegna il valore risulta a `bString`.</xref:System.String.Copy%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="cfd0a-120">In the preceding example, the <xref:System.String.Copy%2A?displayProperty=fullName> method is a static method, which acts upon an expression it is given and assigns the resulting value to `bString`.</span></span>  
  
#### <a name="instance-methods"></a><span data-ttu-id="cfd0a-121">Metodi di istanza</span><span class="sxs-lookup"><span data-stu-id="cfd0a-121">Instance Methods</span></span>  
 <span data-ttu-id="cfd0a-122">Metodi di istanza, invece, hanno origine da una particolare istanza di `String` e deve essere qualificato con il nome dell'istanza.</span><span class="sxs-lookup"><span data-stu-id="cfd0a-122">Instance methods, by contrast, stem from a particular instance of `String` and must be qualified with the instance name.</span></span> <span data-ttu-id="cfd0a-123">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="cfd0a-123">For example:</span></span>  
  
 <span data-ttu-id="cfd0a-124">[!code-vb[VbVbalrStrings n.&46;](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/types-of-string-manipulation-methods_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="cfd0a-124">[!code-vb[VbVbalrStrings#46](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/types-of-string-manipulation-methods_3.vb)]</span></span>  
  
 <span data-ttu-id="cfd0a-125">In questo esempio, il <xref:System.String.Substring%2A?displayProperty=fullName>è un metodo dell'istanza di `String` (vale a dire `aString`).</xref:System.String.Substring%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="cfd0a-125">In this example, the <xref:System.String.Substring%2A?displayProperty=fullName> method is a method of the instance of `String` (that is, `aString`).</span></span> <span data-ttu-id="cfd0a-126">Esegue un'operazione su `aString` e assegna tale valore per `bString`.</span><span class="sxs-lookup"><span data-stu-id="cfd0a-126">It performs an operation on `aString` and assigns that value to `bString`.</span></span>  
  
 <span data-ttu-id="cfd0a-127">Per ulteriori informazioni, vedere la documentazione per la <xref:System.String>classe.</xref:System.String></span><span class="sxs-lookup"><span data-stu-id="cfd0a-127">For more information, see the documentation for the <xref:System.String> class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cfd0a-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cfd0a-128">See Also</span></span>  
 [<span data-ttu-id="cfd0a-129">Introduzione alle stringhe in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="cfd0a-129">Introduction to Strings in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md)
