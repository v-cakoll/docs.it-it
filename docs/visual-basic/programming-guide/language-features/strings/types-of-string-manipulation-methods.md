---
title: Tipi di metodi per la gestione delle stringhe
ms.date: 07/20/2015
helpviewer_keywords:
- strings [Visual Basic], manipulating [Visual Basic]
- string manipulation
ms.assetid: 905055cd-7f50-48fb-9eed-b0995af1dc1f
ms.openlocfilehash: aba9af9c699cf8d07862c5d2967902bec1623500
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84363759"
---
# <a name="types-of-string-manipulation-methods-in-visual-basic"></a><span data-ttu-id="cb587-102">Tipi di metodi per la gestione delle stringhe in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="cb587-102">Types of String Manipulation Methods in Visual Basic</span></span>
<span data-ttu-id="cb587-103">Esistono diversi modi per analizzare e modificare le stringhe.</span><span class="sxs-lookup"><span data-stu-id="cb587-103">There are several different ways to analyze and manipulate your strings.</span></span> <span data-ttu-id="cb587-104">Alcuni dei metodi fanno parte del linguaggio Visual Basic e altri sono intrinseci nella `String` classe.</span><span class="sxs-lookup"><span data-stu-id="cb587-104">Some of the methods are a part of the Visual Basic language, and others are inherent in the `String` class.</span></span>  
  
## <a name="visual-basic-language-and-the-net-framework"></a><span data-ttu-id="cb587-105">Lingua Visual Basic e .NET Framework</span><span class="sxs-lookup"><span data-stu-id="cb587-105">Visual Basic Language and the .NET Framework</span></span>  
 <span data-ttu-id="cb587-106">Visual Basic metodi vengono utilizzati come funzioni intrinseche del linguaggio.</span><span class="sxs-lookup"><span data-stu-id="cb587-106">Visual Basic methods are used as inherent functions of the language.</span></span> <span data-ttu-id="cb587-107">Possono essere usati senza qualificazione nel codice.</span><span class="sxs-lookup"><span data-stu-id="cb587-107">They may be used without qualification in your code.</span></span> <span data-ttu-id="cb587-108">Nell'esempio seguente viene illustrato l'uso tipico di un Visual Basic comando di manipolazione delle stringhe:</span><span class="sxs-lookup"><span data-stu-id="cb587-108">The following example shows typical use of a Visual Basic string-manipulation command:</span></span>  
  
 [!code-vb[VbVbalrStrings#44](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#44)]  
  
 <span data-ttu-id="cb587-109">In questo esempio, la `Mid` funzione esegue un'operazione diretta su `aString` e assegna il valore a `bString` .</span><span class="sxs-lookup"><span data-stu-id="cb587-109">In this example, the `Mid` function performs a direct operation on `aString` and assigns the value to `bString`.</span></span>  
  
 <span data-ttu-id="cb587-110">Per un elenco dei metodi di modifica delle stringhe Visual Basic, vedere [Riepilogo della modifica delle stringhe](../../../language-reference/keywords/string-manipulation-summary.md).</span><span class="sxs-lookup"><span data-stu-id="cb587-110">For a list of Visual Basic string manipulation methods, see [String Manipulation Summary](../../../language-reference/keywords/string-manipulation-summary.md).</span></span>  
  
### <a name="shared-methods-and-instance-methods"></a><span data-ttu-id="cb587-111">Metodi condivisi e metodi di istanza</span><span class="sxs-lookup"><span data-stu-id="cb587-111">Shared Methods and Instance Methods</span></span>  
 <span data-ttu-id="cb587-112">È anche possibile modificare le stringhe con i metodi della `String` classe.</span><span class="sxs-lookup"><span data-stu-id="cb587-112">You can also manipulate strings with the methods of the `String` class.</span></span> <span data-ttu-id="cb587-113">In sono disponibili due tipi di metodi `String` : metodi *condivisi* e metodi di *istanza* .</span><span class="sxs-lookup"><span data-stu-id="cb587-113">There are two types of methods in `String`: *shared* methods and *instance* methods.</span></span>  
  
#### <a name="shared-methods"></a><span data-ttu-id="cb587-114">Metodi condivisi</span><span class="sxs-lookup"><span data-stu-id="cb587-114">Shared Methods</span></span>  
 <span data-ttu-id="cb587-115">Un metodo condiviso è un metodo che deriva dalla `String` classe stessa e non richiede l'uso di un'istanza di tale classe.</span><span class="sxs-lookup"><span data-stu-id="cb587-115">A shared method is a method that stems from the `String` class itself and does not require an instance of that class to work.</span></span> <span data-ttu-id="cb587-116">Questi metodi possono essere qualificati con il nome della classe ( `String` ) anziché con un'istanza della `String` classe.</span><span class="sxs-lookup"><span data-stu-id="cb587-116">These methods can be qualified with the name of the class (`String`) rather than with an instance of the `String` class.</span></span> <span data-ttu-id="cb587-117">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="cb587-117">For example:</span></span>  
  
 [!code-vb[VbVbalrStrings#45](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#45)]  
  
 <span data-ttu-id="cb587-118">Nell'esempio precedente, il <xref:System.String.Copy%2A?displayProperty=nameWithType> metodo è un metodo statico che agisce su un'espressione a cui viene assegnato e che assegna il valore risultante a `bString` .</span><span class="sxs-lookup"><span data-stu-id="cb587-118">In the preceding example, the <xref:System.String.Copy%2A?displayProperty=nameWithType> method is a static method, which acts upon an expression it is given and assigns the resulting value to `bString`.</span></span>  
  
#### <a name="instance-methods"></a><span data-ttu-id="cb587-119">Metodi di istanza</span><span class="sxs-lookup"><span data-stu-id="cb587-119">Instance Methods</span></span>  
 <span data-ttu-id="cb587-120">I metodi di istanza, al contrario, derivano da una particolare istanza di `String` e devono essere qualificati con il nome dell'istanza.</span><span class="sxs-lookup"><span data-stu-id="cb587-120">Instance methods, by contrast, stem from a particular instance of `String` and must be qualified with the instance name.</span></span> <span data-ttu-id="cb587-121">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="cb587-121">For example:</span></span>  
  
 [!code-vb[VbVbalrStrings#46](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#46)]  
  
 <span data-ttu-id="cb587-122">In questo esempio, il <xref:System.String.Substring%2A?displayProperty=nameWithType> metodo è un metodo dell'istanza di `String` (ovvero `aString` ).</span><span class="sxs-lookup"><span data-stu-id="cb587-122">In this example, the <xref:System.String.Substring%2A?displayProperty=nameWithType> method is a method of the instance of `String` (that is, `aString`).</span></span> <span data-ttu-id="cb587-123">Esegue un'operazione su `aString` e assegna tale valore a `bString` .</span><span class="sxs-lookup"><span data-stu-id="cb587-123">It performs an operation on `aString` and assigns that value to `bString`.</span></span>  
  
 <span data-ttu-id="cb587-124">Per ulteriori informazioni, vedere la documentazione relativa alla <xref:System.String> classe.</span><span class="sxs-lookup"><span data-stu-id="cb587-124">For more information, see the documentation for the <xref:System.String> class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cb587-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cb587-125">See also</span></span>

- [<span data-ttu-id="cb587-126">Introduzione alle stringhe in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="cb587-126">Introduction to Strings in Visual Basic</span></span>](introduction-to-strings.md)
