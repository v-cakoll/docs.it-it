---
title: 'Procedura: Estrarre un protocollo e un numero di porta da un URL'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
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
ms.assetid: ab7f62b3-6d2c-4efb-8ac6-28600df5fd5c
caps.latest.revision: "15"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 10ab05ac8b24c0658be2f27809137c6b0bd4834f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-extract-a-protocol-and-port-number-from-a-url"></a><span data-ttu-id="01361-102">Procedura: Estrarre un protocollo e un numero di porta da un URL</span><span class="sxs-lookup"><span data-stu-id="01361-102">How to: Extract a Protocol and Port Number from a URL</span></span>
<span data-ttu-id="01361-103">L'esempio seguente estrae un protocollo e un numero di porta da un URL.</span><span class="sxs-lookup"><span data-stu-id="01361-103">The following example extracts a protocol and port number from a URL.</span></span>  
  
## <a name="example"></a><span data-ttu-id="01361-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="01361-104">Example</span></span>  
 <span data-ttu-id="01361-105">Nell'esempio viene utilizzato il <xref:System.Text.RegularExpressions.Match.Result%2A?displayProperty=nameWithType> per restituire il protocollo seguito da due punti seguiti dal numero di porta.</span><span class="sxs-lookup"><span data-stu-id="01361-105">The example uses the <xref:System.Text.RegularExpressions.Match.Result%2A?displayProperty=nameWithType> method to return the protocol followed by a colon followed by the port number.</span></span>  
  
 [!code-csharp[RegularExpressions.Examples.Protocol#1](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Examples.Protocol/cs/Example.cs#1)]
 [!code-vb[RegularExpressions.Examples.Protocol#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Examples.Protocol/vb/Example.vb#1)]  
  
 <span data-ttu-id="01361-106">Il modello di espressione regolare `^(?<proto>\w+)://[^/]+?(?<port>:\d+)?/` può essere interpretato come indicato nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="01361-106">The regular expression pattern `^(?<proto>\w+)://[^/]+?(?<port>:\d+)?/` can be interpreted as shown in the following table.</span></span>  
  
|<span data-ttu-id="01361-107">Criterio</span><span class="sxs-lookup"><span data-stu-id="01361-107">Pattern</span></span>|<span data-ttu-id="01361-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="01361-108">Description</span></span>|  
|-------------|-----------------|  
|`^`|<span data-ttu-id="01361-109">Iniziare la ricerca della corrispondenza all'inizio della stringa.</span><span class="sxs-lookup"><span data-stu-id="01361-109">Begin the match at the start of the string.</span></span>|  
|`(?<proto>\w+)`|<span data-ttu-id="01361-110">Trova la corrispondenza di uno o più caratteri alfanumerici.</span><span class="sxs-lookup"><span data-stu-id="01361-110">Match one or more word characters.</span></span> <span data-ttu-id="01361-111">Nome di questo gruppo `proto`.</span><span class="sxs-lookup"><span data-stu-id="01361-111">Name this group `proto`.</span></span>|  
|`://`|<span data-ttu-id="01361-112">Trovare la corrispondenza di due punti seguiti da due barre.</span><span class="sxs-lookup"><span data-stu-id="01361-112">Match a colon followed by two slash marks.</span></span>|  
|`[^/]+?`|<span data-ttu-id="01361-113">Trovare la corrispondenza di una o più occorrenze (ma il minor numero possibile) di qualsiasi carattere diverso da una barra.</span><span class="sxs-lookup"><span data-stu-id="01361-113">Match one or more occurrences (but as few as possible) of any character other than a slash mark.</span></span>|  
|`(?<port>:\d+)?`|<span data-ttu-id="01361-114">Trovare la corrispondenza di zero o una occorrenza di due punti seguiti da una o più cifre.</span><span class="sxs-lookup"><span data-stu-id="01361-114">Match zero or one occurrence of a colon followed by one or more digit characters.</span></span> <span data-ttu-id="01361-115">Nome di questo gruppo `port`.</span><span class="sxs-lookup"><span data-stu-id="01361-115">Name this group `port`.</span></span>|  
|`/`|<span data-ttu-id="01361-116">Trovare la corrispondenza di una barra.</span><span class="sxs-lookup"><span data-stu-id="01361-116">Match a slash mark.</span></span>|  
  
 <span data-ttu-id="01361-117">Il <xref:System.Text.RegularExpressions.Match.Result%2A?displayProperty=nameWithType> metodo espande la `${proto}${port}` sequenza di sostituzione che concatena il valore di due gruppi denominati acquisiti nel modello di espressione regolare.</span><span class="sxs-lookup"><span data-stu-id="01361-117">The <xref:System.Text.RegularExpressions.Match.Result%2A?displayProperty=nameWithType> method expands the `${proto}${port}` replacement sequence, which concatenates the value of the two named groups captured in the regular expression pattern.</span></span> <span data-ttu-id="01361-118">È una valida alternativa in modo esplicito della concatenazione delle stringhe recuperate dall'oggetto della raccolta restituita dal <xref:System.Text.RegularExpressions.Match.Groups%2A?displayProperty=nameWithType> proprietà.</span><span class="sxs-lookup"><span data-stu-id="01361-118">It is a convenient alternative to explicitly concatenating the strings retrieved from the collection object returned by the <xref:System.Text.RegularExpressions.Match.Groups%2A?displayProperty=nameWithType> property.</span></span>  
  
 <span data-ttu-id="01361-119">Nell'esempio viene utilizzato il <xref:System.Text.RegularExpressions.Match.Result%2A?displayProperty=nameWithType> metodo con due sostituzioni, `${proto}` e `${port}`, per includere i gruppi acquisiti nella stringa di output.</span><span class="sxs-lookup"><span data-stu-id="01361-119">The example uses the <xref:System.Text.RegularExpressions.Match.Result%2A?displayProperty=nameWithType> method with two substitutions, `${proto}` and `${port}`, to include the captured groups in the output string.</span></span> <span data-ttu-id="01361-120">È possibile recuperare i gruppi acquisiti della corrispondenza <xref:System.Text.RegularExpressions.GroupCollection> invece, come illustrato nel codice seguente.</span><span class="sxs-lookup"><span data-stu-id="01361-120">You can retrieve the captured groups from the match's <xref:System.Text.RegularExpressions.GroupCollection> object instead, as the following code shows.</span></span>  
  
 [!code-csharp[RegularExpressions.Examples.Protocol#2](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Examples.Protocol/cs/example2.cs#2)]
 [!code-vb[RegularExpressions.Examples.Protocol#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Examples.Protocol/vb/example2.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="01361-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="01361-121">See Also</span></span>  
 [<span data-ttu-id="01361-122">Espressioni regolari di .NET</span><span class="sxs-lookup"><span data-stu-id="01361-122">.NET Regular Expressions</span></span>](../../../docs/standard/base-types/regular-expressions.md)
