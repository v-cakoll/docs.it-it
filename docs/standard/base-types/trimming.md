---
title: Eliminazione di spazi iniziali e finali e rimozione di caratteri dalle stringhe in .NET
description: Informazioni su come tagliare spazi vuoti dall'inizio o dalla fine di una stringa oppure rimuovere un numero qualsiasi di spazi o caratteri da una posizione specificata nella stringa in .NET.
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- strings [.NET Framework], removing characters
- Remove method
- TrimEnd method
- Trim method
- trimming characters
- TrimStart method
- removing characters
ms.assetid: ab248dab-70d4-4413-81c6-542d153fd195
ms.openlocfilehash: 630fe6b51d151d1f1384f2e3cde62750c303d883
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/05/2020
ms.locfileid: "84446893"
---
# <a name="trimming-and-removing-characters-from-strings-in-net"></a><span data-ttu-id="e0cb0-103">Eliminazione di spazi iniziali e finali e rimozione di caratteri dalle stringhe in .NET</span><span class="sxs-lookup"><span data-stu-id="e0cb0-103">Trimming and Removing Characters from Strings in .NET</span></span>
<span data-ttu-id="e0cb0-104">Se si sta analizzando una frase in singole parole, è possibile che si ottengano parole con spazi vuoti alle estremità.</span><span class="sxs-lookup"><span data-stu-id="e0cb0-104">If you are parsing a sentence into individual words, you might end up with words that have blank spaces (also called white spaces) on either end of the word.</span></span> <span data-ttu-id="e0cb0-105">In questo caso è possibile usare uno dei metodi trim della classe **System.String** per rimuovere un numero qualsiasi di spazi o altri caratteri da una posizione specificata nella stringa.</span><span class="sxs-lookup"><span data-stu-id="e0cb0-105">In this situation, you can use one of the trim methods in the **System.String** class to remove any number of spaces or other characters from a specified position in the string.</span></span> <span data-ttu-id="e0cb0-106">La tabella seguente illustra i metodi trim disponibili.</span><span class="sxs-lookup"><span data-stu-id="e0cb0-106">The following table describes the available trim methods.</span></span>  
  
|<span data-ttu-id="e0cb0-107">Nome metodo</span><span class="sxs-lookup"><span data-stu-id="e0cb0-107">Method name</span></span>|<span data-ttu-id="e0cb0-108">Uso</span><span class="sxs-lookup"><span data-stu-id="e0cb0-108">Use</span></span>|  
|-----------------|---------|  
|<xref:System.String.Trim%2A?displayProperty=nameWithType>|<span data-ttu-id="e0cb0-109">Rimuove gli spazi vuoti o i caratteri specificati in una matrice di caratteri all'inizio e alla fine di una stringa.</span><span class="sxs-lookup"><span data-stu-id="e0cb0-109">Removes white spaces or characters specified in an array of characters from the beginning and end of a string.</span></span>|  
|<xref:System.String.TrimEnd%2A?displayProperty=nameWithType>|<span data-ttu-id="e0cb0-110">Rimuove i caratteri specificati in una matrice di caratteri alla fine di una stringa.</span><span class="sxs-lookup"><span data-stu-id="e0cb0-110">Removes characters specified in an array of characters from the end of a string.</span></span>|  
|<xref:System.String.TrimStart%2A?displayProperty=nameWithType>|<span data-ttu-id="e0cb0-111">Rimuove i caratteri specificati in una matrice di caratteri all'inizio di una stringa.</span><span class="sxs-lookup"><span data-stu-id="e0cb0-111">Removes characters specified in an array of characters from the beginning of a string.</span></span>|  
|<xref:System.String.Remove%2A?displayProperty=nameWithType>|<span data-ttu-id="e0cb0-112">Rimuove un numero specificato di caratteri da una posizione di indice specificata in una stringa.</span><span class="sxs-lookup"><span data-stu-id="e0cb0-112">Removes a specified number of characters from a specified index position in a string.</span></span>|  
  
## <a name="trim"></a><span data-ttu-id="e0cb0-113">Trim</span><span class="sxs-lookup"><span data-stu-id="e0cb0-113">Trim</span></span>

 <span data-ttu-id="e0cb0-114">È possibile rimuovere facilmente gli spazi vuoti da entrambe le estremità di una stringa utilizzando il metodo <xref:System.String.Trim%2A?displayProperty=nameWithType>, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="e0cb0-114">You can easily remove white spaces from both ends of a string by using the <xref:System.String.Trim%2A?displayProperty=nameWithType> method, as shown in the following example.</span></span>  
  
 [!code-cpp[Conceptual.String.BasicOps#17](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.string.basicops/cpp/trimming.cpp#17)]
 [!code-csharp[Conceptual.String.BasicOps#17](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.basicops/cs/trimming.cs#17)]
 [!code-vb[Conceptual.String.BasicOps#17](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.basicops/vb/trimming.vb#17)]  
  
 <span data-ttu-id="e0cb0-115">È anche possibile rimuovere i caratteri specificati in una matrice di caratteri all'inizio e alla fine di una stringa.</span><span class="sxs-lookup"><span data-stu-id="e0cb0-115">You can also remove characters that you specify in a character array from the beginning and end of a string.</span></span> <span data-ttu-id="e0cb0-116">Nell'esempio seguente vengono rimossi gli spazi vuoti, i punti e gli asterischi.</span><span class="sxs-lookup"><span data-stu-id="e0cb0-116">The following example removes white-space characters, periods, and asterisks.</span></span>  
  
 [!code-csharp[Conceptual.String.BasicOps#22](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.basicops/cs/trim2.cs#22)]
 [!code-vb[Conceptual.String.BasicOps#22](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.basicops/vb/trim2.vb#22)]  
  
## <a name="trimend"></a><span data-ttu-id="e0cb0-117">TrimEnd</span><span class="sxs-lookup"><span data-stu-id="e0cb0-117">TrimEnd</span></span>

 <span data-ttu-id="e0cb0-118">Il metodo **TrimEnd** rimuove caratteri alla fine di una stringa, creando un nuovo oggetto stringa.</span><span class="sxs-lookup"><span data-stu-id="e0cb0-118">The **String.TrimEnd** method removes characters from the end of a string, creating a new string object.</span></span> <span data-ttu-id="e0cb0-119">Una matrice di caratteri viene passata a questo metodo per specificare i caratteri da rimuovere.</span><span class="sxs-lookup"><span data-stu-id="e0cb0-119">An array of characters is passed to this method to specify the characters to be removed.</span></span> <span data-ttu-id="e0cb0-120">L'ordine degli elementi nella matrice di caratteri non influenza l'operazione di rimozione.</span><span class="sxs-lookup"><span data-stu-id="e0cb0-120">The order of the elements in the character array does not affect the trim operation.</span></span> <span data-ttu-id="e0cb0-121">La rimozione si interrompe quando viene trovato un carattere non specificato nella matrice.</span><span class="sxs-lookup"><span data-stu-id="e0cb0-121">The trim stops when a character not specified in the array is found.</span></span>  
  
 <span data-ttu-id="e0cb0-122">L'esempio seguente rimuove le ultime lettere di una stringa con il metodo **TrimEnd**.</span><span class="sxs-lookup"><span data-stu-id="e0cb0-122">The following example removes the last letters of a string using the **TrimEnd** method.</span></span> <span data-ttu-id="e0cb0-123">In questo esempio la posizione dei caratteri `'r'` e `'W'` viene invertita per indicare che l'ordine dei caratteri nella matrice non è importante.</span><span class="sxs-lookup"><span data-stu-id="e0cb0-123">In this example, the position of the `'r'` character and the `'W'` character are reversed to illustrate that the order of characters in the array does not matter.</span></span> <span data-ttu-id="e0cb0-124">Si noti che questo codice rimuove l'ultima parola di `MyString` e una parte della prima parola.</span><span class="sxs-lookup"><span data-stu-id="e0cb0-124">Notice that this code removes the last word of `MyString` plus part of the first.</span></span>  
  
 [!code-cpp[Conceptual.String.BasicOps#18](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.string.basicops/cpp/trimming.cpp#18)]
 [!code-csharp[Conceptual.String.BasicOps#18](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.basicops/cs/trimming.cs#18)]
 [!code-vb[Conceptual.String.BasicOps#18](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.basicops/vb/trimming.vb#18)]  
  
 <span data-ttu-id="e0cb0-125">Il codice visualizza `He` nella console.</span><span class="sxs-lookup"><span data-stu-id="e0cb0-125">This code displays `He` to the console.</span></span>  
  
 <span data-ttu-id="e0cb0-126">L'esempio seguente rimuove l'ultima parola di una stringa con il metodo **TrimEnd**.</span><span class="sxs-lookup"><span data-stu-id="e0cb0-126">The following example removes the last word of a string using the **TrimEnd** method.</span></span> <span data-ttu-id="e0cb0-127">In questo codice la parola `Hello` è seguita da una virgola: dato che la virgola non è specificata nella matrice di caratteri da tagliare, l'operazione di taglio termina in corrispondenza della virgola.</span><span class="sxs-lookup"><span data-stu-id="e0cb0-127">In this code, a comma follows the word `Hello` and, because the comma is not specified in the array of characters to trim, the trim ends at the comma.</span></span>  
  
 [!code-cpp[Conceptual.String.BasicOps#19](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.string.basicops/cpp/trimming.cpp#19)]
 [!code-csharp[Conceptual.String.BasicOps#19](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.basicops/cs/trimming.cs#19)]
 [!code-vb[Conceptual.String.BasicOps#19](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.basicops/vb/trimming.vb#19)]  
  
 <span data-ttu-id="e0cb0-128">Il codice visualizza `Hello,` nella console.</span><span class="sxs-lookup"><span data-stu-id="e0cb0-128">This code displays `Hello,` to the console.</span></span>  
  
## <a name="trimstart"></a><span data-ttu-id="e0cb0-129">TrimStart</span><span class="sxs-lookup"><span data-stu-id="e0cb0-129">TrimStart</span></span>

 <span data-ttu-id="e0cb0-130">Il metodo **String.TrimStart** è simile al metodo **String.TrimEnd** ma crea una nuova stringa rimuovendo caratteri dall'inizio di un oggetto stringa esistente.</span><span class="sxs-lookup"><span data-stu-id="e0cb0-130">The **String.TrimStart** method is similar to the **String.TrimEnd** method except that it creates a new string by removing characters from the beginning of an existing string object.</span></span> <span data-ttu-id="e0cb0-131">Una matrice di caratteri viene passata al metodo **TrimStart** per specificare i caratteri da rimuovere.</span><span class="sxs-lookup"><span data-stu-id="e0cb0-131">An array of characters is passed to the **TrimStart** method to specify the characters to be removed.</span></span> <span data-ttu-id="e0cb0-132">Come per il metodo **TrimEnd**, l'ordine degli elementi nella matrice di caratteri non è importante per l'operazione di rimozione.</span><span class="sxs-lookup"><span data-stu-id="e0cb0-132">As with the **TrimEnd** method, the order of the elements in the character array does not affect the trim operation.</span></span> <span data-ttu-id="e0cb0-133">La rimozione si interrompe quando viene trovato un carattere non specificato nella matrice.</span><span class="sxs-lookup"><span data-stu-id="e0cb0-133">The trim stops when a character not specified in the array is found.</span></span>  
  
 <span data-ttu-id="e0cb0-134">L'esempio seguente rimuove la prima parola di una stringa.</span><span class="sxs-lookup"><span data-stu-id="e0cb0-134">The following example removes the first word of a string.</span></span> <span data-ttu-id="e0cb0-135">In questo esempio la posizione dei caratteri `'l'` e `'H'` viene invertita per indicare che l'ordine dei caratteri nella matrice non è importante.</span><span class="sxs-lookup"><span data-stu-id="e0cb0-135">In this example, the position of the `'l'` character and the `'H'` character are reversed to illustrate that the order of characters in the array does not matter.</span></span>  
  
 [!code-cpp[Conceptual.String.BasicOps#20](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.string.basicops/cpp/trimming.cpp#20)]
 [!code-csharp[Conceptual.String.BasicOps#20](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.basicops/cs/trimming.cs#20)]
 [!code-vb[Conceptual.String.BasicOps#20](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.basicops/vb/trimming.vb#20)]  
  
 <span data-ttu-id="e0cb0-136">Il codice visualizza `World!` nella console.</span><span class="sxs-lookup"><span data-stu-id="e0cb0-136">This code displays `World!` to the console.</span></span>  
  
## <a name="remove"></a><span data-ttu-id="e0cb0-137">Rimuovi</span><span class="sxs-lookup"><span data-stu-id="e0cb0-137">Remove</span></span>

 <span data-ttu-id="e0cb0-138">Tramite il metodo <xref:System.String.Remove%2A?displayProperty=nameWithType> viene rimosso un numero specificato di caratteri a partire da una posizione specificata in una stringa esistente.</span><span class="sxs-lookup"><span data-stu-id="e0cb0-138">The <xref:System.String.Remove%2A?displayProperty=nameWithType> method removes a specified number of characters that begin at a specified position in an existing string.</span></span> <span data-ttu-id="e0cb0-139">Questo metodo presuppone un indice a base zero.</span><span class="sxs-lookup"><span data-stu-id="e0cb0-139">This method assumes a zero-based index.</span></span>  
  
 <span data-ttu-id="e0cb0-140">L'esempio seguente rimuove dieci caratteri da una stringa a partire dalla posizione cinque di un indice a base zero della stringa.</span><span class="sxs-lookup"><span data-stu-id="e0cb0-140">The following example removes ten characters from a string beginning at position five of a zero-based index of the string.</span></span>  
  
 [!code-cpp[Conceptual.String.BasicOps#21](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.string.basicops/cpp/trimming.cpp#21)]
 [!code-csharp[Conceptual.String.BasicOps#21](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.basicops/cs/trimming.cs#21)]
 [!code-vb[Conceptual.String.BasicOps#21](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.basicops/vb/trimming.vb#21)]  
  
## <a name="replace"></a><span data-ttu-id="e0cb0-141">Replace</span><span class="sxs-lookup"><span data-stu-id="e0cb0-141">Replace</span></span>

 <span data-ttu-id="e0cb0-142">È anche possibile rimuovere da una stringa una sottostringa o un carattere specificato chiamando il metodo <xref:System.String.Replace%28System.String%2CSystem.String%29?displayProperty=nameWithType> e specificando, in sostituzione, una stringa vuota (<xref:System.String.Empty?displayProperty=nameWithType>).</span><span class="sxs-lookup"><span data-stu-id="e0cb0-142">You can also remove a specified character or substring from a string by calling the <xref:System.String.Replace%28System.String%2CSystem.String%29?displayProperty=nameWithType> method and specifying an empty string (<xref:System.String.Empty?displayProperty=nameWithType>) as the replacement.</span></span> <span data-ttu-id="e0cb0-143">Nell'esempio seguente vengono rimosse tutte le virgole da una stringa.</span><span class="sxs-lookup"><span data-stu-id="e0cb0-143">The following example removes all commas from a string.</span></span>  
  
 [!code-csharp[Conceptual.String.BasicOps#23](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.basicops/cs/replace1.cs#23)]
 [!code-vb[Conceptual.String.BasicOps#23](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.basicops/vb/replace1.vb#23)]  
  
## <a name="see-also"></a><span data-ttu-id="e0cb0-144">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e0cb0-144">See also</span></span>

- [<span data-ttu-id="e0cb0-145">Operazioni di base sulle stringhe</span><span class="sxs-lookup"><span data-stu-id="e0cb0-145">Basic String Operations</span></span>](basic-string-operations.md)
