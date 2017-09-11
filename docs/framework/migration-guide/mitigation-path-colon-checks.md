---
title: 'Mitigazione: Verifica della presenza dei due punti nel percorso'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-bcl
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a0bb52de-d279-419d-8f23-4b12d1a3f36e
caps.latest.revision: 5
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 8eb6864213aa4420f7a4373b9abbf173880f035f
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="mitigation-path-colon-checks"></a><span data-ttu-id="4bcec-102">Mitigazione: Verifica della presenza dei due punti nel percorso</span><span class="sxs-lookup"><span data-stu-id="4bcec-102">Mitigation: Path Colon Checks</span></span>
<span data-ttu-id="4bcec-103">A partire dalle applicazioni dedicate a [!INCLUDE[net_v462](../../../includes/net-v462-md.md)], sono state apportate alcune modifiche per supportare i percorsi in precedenza non supportati (entrambi in termini di lunghezza e il formato).</span><span class="sxs-lookup"><span data-stu-id="4bcec-103">Starting with apps that target the [!INCLUDE[net_v462](../../../includes/net-v462-md.md)], a number of changes were made to support previously unsupported paths (both in terms of length and format).</span></span> <span data-ttu-id="4bcec-104">In particolare, i controlli per la sintassi del separatore dell'unità appropriata (due punti) sono stati resi più corretti.</span><span class="sxs-lookup"><span data-stu-id="4bcec-104">In particular, checks for the proper drive separator syntax (the colon) were made more correct.</span></span>  
  
## <a name="impact"></a><span data-ttu-id="4bcec-105">Impatto</span><span class="sxs-lookup"><span data-stu-id="4bcec-105">Impact</span></span>  
 <span data-ttu-id="4bcec-106">Queste modifiche bloccano alcuni percorsi URI supportati in precedenza dai metodi <xref:System.IO.Path.GetDirectoryName%2A?displayProperty=fullName> e <xref:System.IO.Path.GetPathRoot%2A?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="4bcec-106">These changes block some URI paths the <xref:System.IO.Path.GetDirectoryName%2A?displayProperty=fullName> and <xref:System.IO.Path.GetPathRoot%2A?displayProperty=fullName> methods previously supported.</span></span>  
  
## <a name="mitigation"></a><span data-ttu-id="4bcec-107">Attenuazione</span><span class="sxs-lookup"><span data-stu-id="4bcec-107">Mitigation</span></span>  
 <span data-ttu-id="4bcec-108">Per risolvere il problema di un percorso in precedenza accettabile che non è più supportato dai metodi <xref:System.IO.Path.GetDirectoryName%2A?displayProperty=fullName> e <xref:System.IO.Path.GetPathRoot%2A?displayProperty=fullName>, è possibile eseguire queste operazioni:</span><span class="sxs-lookup"><span data-stu-id="4bcec-108">To work around the problem of a previously acceptable path that is no longer supported by the <xref:System.IO.Path.GetDirectoryName%2A?displayProperty=fullName> and <xref:System.IO.Path.GetPathRoot%2A?displayProperty=fullName> methods, you can do the following:</span></span>  
  
-   <span data-ttu-id="4bcec-109">Rimuovere manualmente lo schema da un URL.</span><span class="sxs-lookup"><span data-stu-id="4bcec-109">Manually remove the scheme from a URL.</span></span> <span data-ttu-id="4bcec-110">Ad esempio, rimuovere `file://` da un URL.</span><span class="sxs-lookup"><span data-stu-id="4bcec-110">For example, remove `file://` from a URL.</span></span>  
  
-   <span data-ttu-id="4bcec-111">Passare l'URI a un costruttore <xref:System.Uri> e recuperare il valore della proprietà <xref:System.Uri.LocalPath%2A?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="4bcec-111">Pass the URI to a <xref:System.Uri> constructor,  and retrieve the value of the <xref:System.Uri.LocalPath%2A?displayProperty=fullName> property.</span></span>  
  
-   <span data-ttu-id="4bcec-112">Rifiutare esplicitamente la normalizzazione del nuovo percorso impostando il commutatore `Switch.System.IO.UseLegacyPathHandling`<xref:System.AppContext> su `true`.</span><span class="sxs-lookup"><span data-stu-id="4bcec-112">Opt out of the new path normalization by setting the `Switch.System.IO.UseLegacyPathHandling`<xref:System.AppContext> switch to `true`.</span></span>  
  
    ```xml  
    <runtime>  
        <AppContextSwitchOverrides value="Switch.System.IO.UseLegacyPathHandling=true" />    
    </runtime>  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="4bcec-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4bcec-113">See Also</span></span>  
 [<span data-ttu-id="4bcec-114">Modifiche di reindirizzamento</span><span class="sxs-lookup"><span data-stu-id="4bcec-114">Retargeting Changes</span></span>](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-6-2.md)

