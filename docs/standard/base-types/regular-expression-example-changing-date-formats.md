---
title: 'Esempio di espressione regolare: modifica dei formati di data'
ms.date: 06/30/2020
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- searching with regular expressions, examples
- parsing text with regular expressions, examples
- regular expressions, examples
- .NET Framework regular expressions, examples
- regular expressions [.NET Framework], examples
- pattern-matching with regular expressions, examples
ms.assetid: 5fcc75a5-09d7-45ae-a4c0-9ad6085ac83d
ms.openlocfilehash: 3b657ac6c88a1ee846f7f1d2156a18fd34621808
ms.sourcegitcommit: c23d9666ec75b91741da43ee3d91c317d68c7327
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85803950"
---
# <a name="regular-expression-example-changing-date-formats"></a><span data-ttu-id="66e40-102">Esempio di espressione regolare: modifica dei formati di data</span><span class="sxs-lookup"><span data-stu-id="66e40-102">Regular Expression Example: Changing Date Formats</span></span>
<span data-ttu-id="66e40-103">Nell'esempio di codice seguente viene usato il <xref:System.Text.RegularExpressions.Regex.Replace%2A?displayProperty=nameWithType> metodo per sostituire le date con formato *mm* / *GG* / *AA* con date nel formato *GG* - *mm* - *AA*.</span><span class="sxs-lookup"><span data-stu-id="66e40-103">The following code example uses the <xref:System.Text.RegularExpressions.Regex.Replace%2A?displayProperty=nameWithType> method to replace dates that have the form *mm*/*dd*/*yy* with dates that have the form *dd*-*mm*-*yy*.</span></span>  

[!INCLUDE [regex](../../../includes/regex.md)]

## <a name="example"></a><span data-ttu-id="66e40-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="66e40-104">Example</span></span>  
 [!code-csharp[RegularExpressions.Examples.ChangeDateFormats#1](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Examples.ChangeDateFormats/cs/Example_ChangeDateFormats1.cs#1)]
 [!code-vb[RegularExpressions.Examples.ChangeDateFormats#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Examples.ChangeDateFormats/vb/Example_ChangeDateFormats1.vb#1)]  
  
 <span data-ttu-id="66e40-105">Il codice seguente illustra come il metodo `MDYToDMY` può essere chiamato in un'applicazione.</span><span class="sxs-lookup"><span data-stu-id="66e40-105">The following code shows how the `MDYToDMY` method can be called in an application.</span></span>  
  
 [!code-csharp[RegularExpressions.Examples.ChangeDateFormats#2](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Examples.ChangeDateFormats/cs/Example_ChangeDateFormats1.cs#2)]
 [!code-vb[RegularExpressions.Examples.ChangeDateFormats#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Examples.ChangeDateFormats/vb/Example_ChangeDateFormats1.vb#2)]  
  
## <a name="comments"></a><span data-ttu-id="66e40-106">Commenti</span><span class="sxs-lookup"><span data-stu-id="66e40-106">Comments</span></span>  
 <span data-ttu-id="66e40-107">Il criterio di ricerca di espressioni regolari `\b(?<month>\d{1,2})/(?<day>\d{1,2})/(?<year>\d{2,4})\b` è interpretato nel modo illustrato nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="66e40-107">The regular expression pattern  `\b(?<month>\d{1,2})/(?<day>\d{1,2})/(?<year>\d{2,4})\b` is interpreted as shown in the following table.</span></span>  
  
|<span data-ttu-id="66e40-108">Modello</span><span class="sxs-lookup"><span data-stu-id="66e40-108">Pattern</span></span>|<span data-ttu-id="66e40-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="66e40-109">Description</span></span>|  
|-------------|-----------------|  
|`\b`|<span data-ttu-id="66e40-110">Inizia la corrispondenza sul confine di parola.</span><span class="sxs-lookup"><span data-stu-id="66e40-110">Begin the match at a word boundary.</span></span>|  
|`(?<month>\d{1,2})`|<span data-ttu-id="66e40-111">Trova la corrispondenza con una o due cifre decimali.</span><span class="sxs-lookup"><span data-stu-id="66e40-111">Match one or two decimal digits.</span></span> <span data-ttu-id="66e40-112">Equivale al gruppo acquisito `month`.</span><span class="sxs-lookup"><span data-stu-id="66e40-112">This is the `month` captured group.</span></span>|  
|`/`|<span data-ttu-id="66e40-113">Corrisponde alla barra.</span><span class="sxs-lookup"><span data-stu-id="66e40-113">Match the slash mark.</span></span>|  
|`(?<day>\d{1,2})`|<span data-ttu-id="66e40-114">Trova la corrispondenza con una o due cifre decimali.</span><span class="sxs-lookup"><span data-stu-id="66e40-114">Match one or two decimal digits.</span></span> <span data-ttu-id="66e40-115">Equivale al gruppo acquisito `day`.</span><span class="sxs-lookup"><span data-stu-id="66e40-115">This is the `day` captured group.</span></span>|  
|`/`|<span data-ttu-id="66e40-116">Corrisponde alla barra.</span><span class="sxs-lookup"><span data-stu-id="66e40-116">Match the slash mark.</span></span>|  
|`(?<year>\d{2,4})`|<span data-ttu-id="66e40-117">Corrisponde a due - quattro cifre decimali.</span><span class="sxs-lookup"><span data-stu-id="66e40-117">Match from two to four decimal digits.</span></span> <span data-ttu-id="66e40-118">Equivale al gruppo acquisito `year`.</span><span class="sxs-lookup"><span data-stu-id="66e40-118">This is the `year` captured group.</span></span>|  
|`\b`|<span data-ttu-id="66e40-119">Termina la corrispondenza sul confine di parola.</span><span class="sxs-lookup"><span data-stu-id="66e40-119">End the match at a word boundary.</span></span>|  
  
 <span data-ttu-id="66e40-120">Il modello `${day}-${month}-${year}` definisce la stringa di sostituzione come illustrato nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="66e40-120">The pattern `${day}-${month}-${year}` defines the replacement string as shown in the following table.</span></span>  
  
|<span data-ttu-id="66e40-121">Modello</span><span class="sxs-lookup"><span data-stu-id="66e40-121">Pattern</span></span>|<span data-ttu-id="66e40-122">Descrizione</span><span class="sxs-lookup"><span data-stu-id="66e40-122">Description</span></span>|  
|-------------|-----------------|  
|`$(day)`|<span data-ttu-id="66e40-123">Aggiunge la stringa acquisita dal gruppo di acquisizione `day`.</span><span class="sxs-lookup"><span data-stu-id="66e40-123">Add the string captured by the `day` capturing group.</span></span>|  
|`-`|<span data-ttu-id="66e40-124">Aggiunge un trattino.</span><span class="sxs-lookup"><span data-stu-id="66e40-124">Add a hyphen.</span></span>|  
|`$(month)`|<span data-ttu-id="66e40-125">Aggiunge la stringa acquisita dal gruppo di acquisizione `month`.</span><span class="sxs-lookup"><span data-stu-id="66e40-125">Add the string captured by the `month` capturing group.</span></span>|  
|`-`|<span data-ttu-id="66e40-126">Aggiunge un trattino.</span><span class="sxs-lookup"><span data-stu-id="66e40-126">Add a hyphen.</span></span>|  
|`$(year)`|<span data-ttu-id="66e40-127">Aggiunge la stringa acquisita dal gruppo di acquisizione `year`.</span><span class="sxs-lookup"><span data-stu-id="66e40-127">Add the string captured by the `year` capturing group.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="66e40-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="66e40-128">See also</span></span>

- [<span data-ttu-id="66e40-129">Espressioni regolari .NET</span><span class="sxs-lookup"><span data-stu-id="66e40-129">.NET Regular Expressions</span></span>](regular-expressions.md)
