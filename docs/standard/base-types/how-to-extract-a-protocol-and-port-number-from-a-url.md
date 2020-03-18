---
title: 'Procedura: Estrarre un protocollo e un numero di porta da un URL'
ms.date: 03/30/2017
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
ms.assetid: ab7f62b3-6d2c-4efb-8ac6-28600df5fd5c
ms.openlocfilehash: f2704e3fb5ceb68609a475d52e11030177ad760b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "73138730"
---
# <a name="how-to-extract-a-protocol-and-port-number-from-a-url"></a><span data-ttu-id="27374-102">Procedura: Estrarre un protocollo e un numero di porta da un URL</span><span class="sxs-lookup"><span data-stu-id="27374-102">How to: Extract a Protocol and Port Number from a URL</span></span>
<span data-ttu-id="27374-103">L'esempio seguente estrae un protocollo e un numero di porta da un URL.</span><span class="sxs-lookup"><span data-stu-id="27374-103">The following example extracts a protocol and port number from a URL.</span></span>  
  
## <a name="example"></a><span data-ttu-id="27374-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="27374-104">Example</span></span>  
 <span data-ttu-id="27374-105">L'esempio usa il metodo <xref:System.Text.RegularExpressions.Match.Result%2A?displayProperty=nameWithType> per restituire il protocollo seguito da due punti e dal numero di porta.</span><span class="sxs-lookup"><span data-stu-id="27374-105">The example uses the <xref:System.Text.RegularExpressions.Match.Result%2A?displayProperty=nameWithType> method to return the protocol followed by a colon followed by the port number.</span></span>  
  
 [!code-csharp[RegularExpressions.Examples.Protocol#1](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Examples.Protocol/cs/Example.cs#1)]
 [!code-vb[RegularExpressions.Examples.Protocol#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Examples.Protocol/vb/Example.vb#1)]  
  
 <span data-ttu-id="27374-106">Il modello di espressione regolare `^(?<proto>\w+)://[^/]+?(?<port>:\d+)?/` può essere interpretato come indicato nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="27374-106">The regular expression pattern `^(?<proto>\w+)://[^/]+?(?<port>:\d+)?/` can be interpreted as shown in the following table.</span></span>  
  
|<span data-ttu-id="27374-107">Modello</span><span class="sxs-lookup"><span data-stu-id="27374-107">Pattern</span></span>|<span data-ttu-id="27374-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="27374-108">Description</span></span>|  
|-------------|-----------------|  
|`^`|<span data-ttu-id="27374-109">Iniziare la ricerca della corrispondenza all'inizio della stringa.</span><span class="sxs-lookup"><span data-stu-id="27374-109">Begin the match at the start of the string.</span></span>|  
|`(?<proto>\w+)`|<span data-ttu-id="27374-110">Trova la corrispondenza di uno o più caratteri alfanumerici.</span><span class="sxs-lookup"><span data-stu-id="27374-110">Match one or more word characters.</span></span> <span data-ttu-id="27374-111">Assegnare al gruppo il nome `proto`.</span><span class="sxs-lookup"><span data-stu-id="27374-111">Name this group `proto`.</span></span>|  
|`://`|<span data-ttu-id="27374-112">Trovare la corrispondenza di due punti seguiti da due barre.</span><span class="sxs-lookup"><span data-stu-id="27374-112">Match a colon followed by two slash marks.</span></span>|  
|`[^/]+?`|<span data-ttu-id="27374-113">Trovare la corrispondenza di una o più occorrenze (ma il minor numero possibile) di qualsiasi carattere diverso da una barra.</span><span class="sxs-lookup"><span data-stu-id="27374-113">Match one or more occurrences (but as few as possible) of any character other than a slash mark.</span></span>|  
|`(?<port>:\d+)?`|<span data-ttu-id="27374-114">Trovare la corrispondenza di zero o una occorrenza di due punti seguiti da una o più cifre.</span><span class="sxs-lookup"><span data-stu-id="27374-114">Match zero or one occurrence of a colon followed by one or more digit characters.</span></span> <span data-ttu-id="27374-115">Assegnare al gruppo il nome `port`.</span><span class="sxs-lookup"><span data-stu-id="27374-115">Name this group `port`.</span></span>|  
|`/`|<span data-ttu-id="27374-116">Trovare la corrispondenza di una barra.</span><span class="sxs-lookup"><span data-stu-id="27374-116">Match a slash mark.</span></span>|  
  
 <span data-ttu-id="27374-117">Il metodo <xref:System.Text.RegularExpressions.Match.Result%2A?displayProperty=nameWithType> espande la sequenza di sostituzione `${proto}${port}`, che concatena il valore dei due gruppi denominati acquisiti nel modello di espressione regolare.</span><span class="sxs-lookup"><span data-stu-id="27374-117">The <xref:System.Text.RegularExpressions.Match.Result%2A?displayProperty=nameWithType> method expands the `${proto}${port}` replacement sequence, which concatenates the value of the two named groups captured in the regular expression pattern.</span></span> <span data-ttu-id="27374-118">Si tratta di una pratica alternativa alla concatenazione esplicita delle stringhe recuperate dall'oggetto raccolta restituito dalla proprietà <xref:System.Text.RegularExpressions.Match.Groups%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="27374-118">It is a convenient alternative to explicitly concatenating the strings retrieved from the collection object returned by the <xref:System.Text.RegularExpressions.Match.Groups%2A?displayProperty=nameWithType> property.</span></span>  
  
 <span data-ttu-id="27374-119">L'esempio usa il metodo <xref:System.Text.RegularExpressions.Match.Result%2A?displayProperty=nameWithType> con due sostituzioni, `${proto}` e `${port}`, per includere i gruppi acquisiti nella stringa di output.</span><span class="sxs-lookup"><span data-stu-id="27374-119">The example uses the <xref:System.Text.RegularExpressions.Match.Result%2A?displayProperty=nameWithType> method with two substitutions, `${proto}` and `${port}`, to include the captured groups in the output string.</span></span> <span data-ttu-id="27374-120">È invece possibile recuperare i gruppi acquisiti dall'oggetto <xref:System.Text.RegularExpressions.GroupCollection> della corrispondenza, come mostrato dal codice seguente.</span><span class="sxs-lookup"><span data-stu-id="27374-120">You can retrieve the captured groups from the match's <xref:System.Text.RegularExpressions.GroupCollection> object instead, as the following code shows.</span></span>  
  
 [!code-csharp[RegularExpressions.Examples.Protocol#2](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Examples.Protocol/cs/example2.cs#2)]
 [!code-vb[RegularExpressions.Examples.Protocol#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Examples.Protocol/vb/example2.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="27374-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="27374-121">See also</span></span>

- [<span data-ttu-id="27374-122">Espressioni regolari .NET</span><span class="sxs-lookup"><span data-stu-id="27374-122">.NET Regular Expressions</span></span>](../../../docs/standard/base-types/regular-expressions.md)
