---
title: 'Procedura: modificare il contenuto delle stringhe (Guida per programmatori C#)'
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- strings [C#], modifying
ms.assetid: b6c20bba-ce22-43d7-ad1b-5ce65f714055
caps.latest.revision: 16
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
ms.openlocfilehash: 114b6fdabd235d7e57947e77b672352e28aff11e
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-modify-string-contents-c-programming-guide"></a><span data-ttu-id="09d8b-102">Procedura: modificare il contenuto delle stringhe (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="09d8b-102">How to: Modify String Contents (C# Programming Guide)</span></span>
<span data-ttu-id="09d8b-103">Poiché le stringhe sono *non modificabili*, non è possibile (senza usare codice unsafe) modificare il valore di un oggetto stringa dopo che è stato creato.</span><span class="sxs-lookup"><span data-stu-id="09d8b-103">Because strings are *immutable*, it is not possible (without using unsafe code) to modify the value of a string object after it has been created.</span></span> <span data-ttu-id="09d8b-104">Ci sono tuttavia molti modi per modificare il valore di una stringa e archiviare il risultato in un nuovo oggetto stringa.</span><span class="sxs-lookup"><span data-stu-id="09d8b-104">However, there are many ways to modify the value of a string and store the result in a new string object.</span></span> <span data-ttu-id="09d8b-105">La classe <xref:System.String?displayProperty=fullName> fornisce metodi che operano su una stringa di input e restituiscono un nuovo oggetto stringa.</span><span class="sxs-lookup"><span data-stu-id="09d8b-105">The <xref:System.String?displayProperty=fullName> class provides methods that operate on an input string and return a new string object.</span></span> <span data-ttu-id="09d8b-106">In molti casi, è possibile assegnare il nuovo oggetto alla variabile che conteneva la stringa originale.</span><span class="sxs-lookup"><span data-stu-id="09d8b-106">In many cases, you can assign the new object to the variable that held the original string.</span></span> <span data-ttu-id="09d8b-107">La classe <xref:System.Text.RegularExpressions.Regex?displayProperty=fullName> fornisce metodi aggiuntivi che funzionano in modo simile.</span><span class="sxs-lookup"><span data-stu-id="09d8b-107">The <xref:System.Text.RegularExpressions.Regex?displayProperty=fullName> class provides additional methods that work in a similar manner.</span></span> <span data-ttu-id="09d8b-108">La classe <xref:System.Text.StringBuilder?displayProperty=fullName> fornisce un buffer di caratteri che è possibile modificare "sul posto".</span><span class="sxs-lookup"><span data-stu-id="09d8b-108">The <xref:System.Text.StringBuilder?displayProperty=fullName> class provides a character buffer that you can modify "in-place."</span></span> <span data-ttu-id="09d8b-109">Chiamare il metodo <xref:System.Text.StringBuilder.ToString%2A?displayProperty=fullName> per creare un nuovo oggetto stringa che include il contenuto corrente del buffer.</span><span class="sxs-lookup"><span data-stu-id="09d8b-109">You call the <xref:System.Text.StringBuilder.ToString%2A?displayProperty=fullName> method to create a new string object that contains the current contents of the buffer.</span></span>  
  
## <a name="example"></a><span data-ttu-id="09d8b-110">Esempio</span><span class="sxs-lookup"><span data-stu-id="09d8b-110">Example</span></span>  
 <span data-ttu-id="09d8b-111">L'esempio seguente mostra vari modi per sostituire o rimuovere sottostringhe in una stringa specifica.</span><span class="sxs-lookup"><span data-stu-id="09d8b-111">The following example shows various ways to replace or remove substrings in a specified string.</span></span>  
  
 <span data-ttu-id="09d8b-112">[!code-cs[csProgGuideStrings#28](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-modify-string-contents_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="09d8b-112">[!code-cs[csProgGuideStrings#28](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-modify-string-contents_1.cs)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="09d8b-113">Esempio</span><span class="sxs-lookup"><span data-stu-id="09d8b-113">Example</span></span>  
 <span data-ttu-id="09d8b-114">Per accedere ai singoli caratteri in una stringa tramite una notazione di matrice, è possibile usare l'oggetto <xref:System.Text.StringBuilder>, che esegue l'overload dell'operatore `[]` per fornire l'accesso al buffer di caratteri interno.</span><span class="sxs-lookup"><span data-stu-id="09d8b-114">To access the individual characters in a string by using array notation, you can use the <xref:System.Text.StringBuilder> object, which overloads the `[]` operator to provide access to its internal character buffer.</span></span> <span data-ttu-id="09d8b-115">È anche possibile convertire la stringa in una matrice di caratteri tramite il metodo <xref:System.String.ToCharArray%2A>.</span><span class="sxs-lookup"><span data-stu-id="09d8b-115">You can also convert the string to an array of chars by using the <xref:System.String.ToCharArray%2A> method.</span></span> <span data-ttu-id="09d8b-116">L'esempio seguente usa `ToCharArray` per creare la matrice.</span><span class="sxs-lookup"><span data-stu-id="09d8b-116">The following example uses `ToCharArray` to create the array.</span></span> <span data-ttu-id="09d8b-117">Alcuni elementi della matrice vengono quindi modificati.</span><span class="sxs-lookup"><span data-stu-id="09d8b-117">Some elements of this array are then modified.</span></span> <span data-ttu-id="09d8b-118">Viene quindi chiamato un costruttore di stringhe che accetta una matrice di caratteri come parametro di input per creare una nuova stringa.</span><span class="sxs-lookup"><span data-stu-id="09d8b-118">A string constructor that takes a char array as an input parameter is then called to create a new string.</span></span>  
  
 <span data-ttu-id="09d8b-119">[!code-cs[csProgGuideStrings#24](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-modify-string-contents_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="09d8b-119">[!code-cs[csProgGuideStrings#24](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-modify-string-contents_2.cs)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="09d8b-120">Esempio</span><span class="sxs-lookup"><span data-stu-id="09d8b-120">Example</span></span>  
 <span data-ttu-id="09d8b-121">L'esempio seguente viene fornito per quelle situazioni molto rare in cui si potrebbe volere modificare una stringa sul posto usando codice unsafe, in modo simile alle matrici di caratteri di tipo C.</span><span class="sxs-lookup"><span data-stu-id="09d8b-121">The following example is provided for those very rare situations in which you may want to modify a string in-place by using unsafe code in a manner similar to C-style char arrays.</span></span> <span data-ttu-id="09d8b-122">L'esempio mostra come accedere ai singoli caratteri "sul posto" usando la parola chiave fixed.</span><span class="sxs-lookup"><span data-stu-id="09d8b-122">The example shows how to access the individual characters "in-place" by using the fixed keyword.</span></span> <span data-ttu-id="09d8b-123">Mostra anche un possibile effetto collaterale delle operazioni con codice unsafe sulle stringhe, legato al modo in cui il compilatore C# archivia (inserisce) le stringhe internamente.</span><span class="sxs-lookup"><span data-stu-id="09d8b-123">It also demonstrates one possible side effect of unsafe operations on strings that results from the way that the C# compiler stores (interns) strings internally.</span></span> <span data-ttu-id="09d8b-124">In generale, non è consigliabile usare questa tecnica a meno che non sia assolutamente necessario.</span><span class="sxs-lookup"><span data-stu-id="09d8b-124">In general, you should not use this technique unless it is absolutely necessary.</span></span>  
  
 <span data-ttu-id="09d8b-125">[!code-cs[csProgGuideStrings#29](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-modify-string-contents_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="09d8b-125">[!code-cs[csProgGuideStrings#29](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-modify-string-contents_3.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="09d8b-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="09d8b-126">See Also</span></span>  
 <span data-ttu-id="09d8b-127">[Guida per programmatori C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="09d8b-127">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="09d8b-128">Stringhe</span><span class="sxs-lookup"><span data-stu-id="09d8b-128">Strings</span></span>](../../../csharp/programming-guide/strings/index.md)

