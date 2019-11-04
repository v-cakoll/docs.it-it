---
title: 'Mitigazione: Verifica della presenza dei due punti nel percorso'
ms.date: 03/30/2017
ms.assetid: a0bb52de-d279-419d-8f23-4b12d1a3f36e
ms.openlocfilehash: e88643fea3bd507289436f41880a2de34117884f
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/03/2019
ms.locfileid: "73457905"
---
# <a name="mitigation-path-colon-checks"></a><span data-ttu-id="7d39b-102">Mitigazione: Verifica della presenza dei due punti nel percorso</span><span class="sxs-lookup"><span data-stu-id="7d39b-102">Mitigation: Path Colon Checks</span></span>
<span data-ttu-id="7d39b-103">A partire dalle applicazioni destinate a .NET Framework 4.6.2, sono state apportate alcune modifiche per supportare i percorsi in precedenza non supportati, sia in termini di lunghezza che di formato.</span><span class="sxs-lookup"><span data-stu-id="7d39b-103">Starting with apps that target the .NET Framework 4.6.2, a number of changes were made to support previously unsupported paths (both in terms of length and format).</span></span> <span data-ttu-id="7d39b-104">In particolare, i controlli per la sintassi del separatore dell'unità appropriata (due punti) sono stati resi più corretti.</span><span class="sxs-lookup"><span data-stu-id="7d39b-104">In particular, checks for the proper drive separator syntax (the colon) were made more correct.</span></span>  
  
## <a name="impact"></a><span data-ttu-id="7d39b-105">Impatto</span><span class="sxs-lookup"><span data-stu-id="7d39b-105">Impact</span></span>  
 <span data-ttu-id="7d39b-106">Queste modifiche bloccano alcuni percorsi URI supportati in precedenza dai metodi <xref:System.IO.Path.GetDirectoryName%2A?displayProperty=nameWithType> e <xref:System.IO.Path.GetPathRoot%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="7d39b-106">These changes block some URI paths the <xref:System.IO.Path.GetDirectoryName%2A?displayProperty=nameWithType> and <xref:System.IO.Path.GetPathRoot%2A?displayProperty=nameWithType> methods previously supported.</span></span>  
  
## <a name="mitigation"></a><span data-ttu-id="7d39b-107">Attenuazione</span><span class="sxs-lookup"><span data-stu-id="7d39b-107">Mitigation</span></span>  
 <span data-ttu-id="7d39b-108">Per risolvere il problema di un percorso in precedenza accettabile che non è più supportato dai metodi <xref:System.IO.Path.GetDirectoryName%2A?displayProperty=nameWithType> e <xref:System.IO.Path.GetPathRoot%2A?displayProperty=nameWithType>, è possibile eseguire queste operazioni:</span><span class="sxs-lookup"><span data-stu-id="7d39b-108">To work around the problem of a previously acceptable path that is no longer supported by the <xref:System.IO.Path.GetDirectoryName%2A?displayProperty=nameWithType> and <xref:System.IO.Path.GetPathRoot%2A?displayProperty=nameWithType> methods, you can do the following:</span></span>  
  
- <span data-ttu-id="7d39b-109">Rimuovere manualmente lo schema da un URL.</span><span class="sxs-lookup"><span data-stu-id="7d39b-109">Manually remove the scheme from a URL.</span></span> <span data-ttu-id="7d39b-110">Ad esempio, rimuovere `file://` da un URL.</span><span class="sxs-lookup"><span data-stu-id="7d39b-110">For example, remove `file://` from a URL.</span></span>  
  
- <span data-ttu-id="7d39b-111">Passare l'URI a un costruttore <xref:System.Uri> e recuperare il valore della proprietà <xref:System.Uri.LocalPath%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="7d39b-111">Pass the URI to a <xref:System.Uri> constructor,  and retrieve the value of the <xref:System.Uri.LocalPath%2A?displayProperty=nameWithType> property.</span></span>  
  
- <span data-ttu-id="7d39b-112">Rifiutare esplicitamente la normalizzazione del nuovo percorso impostando il commutatore `Switch.System.IO.UseLegacyPathHandling`<xref:System.AppContext> su `true`.</span><span class="sxs-lookup"><span data-stu-id="7d39b-112">Opt out of the new path normalization by setting the `Switch.System.IO.UseLegacyPathHandling`<xref:System.AppContext> switch to `true`.</span></span>  
  
    ```xml  
    <runtime>  
        <AppContextSwitchOverrides value="Switch.System.IO.UseLegacyPathHandling=true" />    
    </runtime>  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="7d39b-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7d39b-113">See also</span></span>

- [<span data-ttu-id="7d39b-114">Compatibilità delle applicazioni</span><span class="sxs-lookup"><span data-stu-id="7d39b-114">Application compatibility</span></span>](application-compatibility.md)
