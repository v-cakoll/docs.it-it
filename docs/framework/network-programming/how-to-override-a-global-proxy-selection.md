---
title: "Procedura: Eseguire l'override di una selezione proxy globale"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 0da481a9-b414-4230-beb0-e3ceba882fe5
ms.openlocfilehash: 44845fb67aac4ff9ab9dda8cf4934153c8c4f23c
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/17/2019
ms.locfileid: "71048265"
---
# <a name="how-to-override-a-global-proxy-selection"></a><span data-ttu-id="db835-102">Procedura: Eseguire l'override di una selezione proxy globale</span><span class="sxs-lookup"><span data-stu-id="db835-102">How to: Override a Global Proxy Selection</span></span>
<span data-ttu-id="db835-103">Questo esempio invia un oggetto **WebRequest** a `www.contoso.com` che esegue l'override della selezione del proxy globale con un server proxy denominato `alternateproxy` sulla porta 80.</span><span class="sxs-lookup"><span data-stu-id="db835-103">This example sends a **WebRequest** to `www.contoso.com` that overrides the global proxy selection with a proxy server named `alternateproxy` on port 80.</span></span>  
  
## <a name="example"></a><span data-ttu-id="db835-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="db835-104">Example</span></span>  
  
```csharp  
WebRequest req = WebRequest.Create("http://www.contoso.com/");  
req.Proxy = new WebProxy("http://alternateproxy:80/");  
```  
  
```vb  
Dim req As WebRequest = WebRequest.Create("http://www.contoso.com/")  
req.Proxy = New WebProxy("http://alternateproxy:80/")  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="db835-105">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="db835-105">Compiling the Code</span></span>  
 <span data-ttu-id="db835-106">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="db835-106">This example requires:</span></span>  
  
- <span data-ttu-id="db835-107">[Direttiva `using`](../../csharp/language-reference/keywords/using-directive.md) per lo spazio dei nomi **System.Net**.</span><span class="sxs-lookup"><span data-stu-id="db835-107">A [`using` directive](../../csharp/language-reference/keywords/using-directive.md) for the **System.Net** namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="db835-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="db835-108">See also</span></span>

- [<span data-ttu-id="db835-109">Uso di protocolli applicativi</span><span class="sxs-lookup"><span data-stu-id="db835-109">Using Application Protocols</span></span>](using-application-protocols.md)
- [<span data-ttu-id="db835-110">Accesso a Internet con un proxy</span><span class="sxs-lookup"><span data-stu-id="db835-110">Accessing the Internet Through a Proxy</span></span>](accessing-the-internet-through-a-proxy.md)
