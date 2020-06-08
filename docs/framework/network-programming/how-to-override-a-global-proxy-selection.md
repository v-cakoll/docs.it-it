---
title: "Procedura: Eseguire l'override di una selezione proxy globale"
description: Seguire questo esempio per eseguire l'override della selezione del proxy globale inviando una WebRequest a un URL, che sostituisce la selezione con un server proxy.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 0da481a9-b414-4230-beb0-e3ceba882fe5
ms.openlocfilehash: 91f64775e2f401be9b740fe9e4c41e1087eb9617
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84502509"
---
# <a name="how-to-override-a-global-proxy-selection"></a><span data-ttu-id="aa7e4-103">Procedura: Eseguire l'override di una selezione proxy globale</span><span class="sxs-lookup"><span data-stu-id="aa7e4-103">How to: Override a Global Proxy Selection</span></span>
<span data-ttu-id="aa7e4-104">Questo esempio invia un oggetto **WebRequest** a `www.contoso.com` che esegue l'override della selezione del proxy globale con un server proxy denominato `alternateproxy` sulla porta 80.</span><span class="sxs-lookup"><span data-stu-id="aa7e4-104">This example sends a **WebRequest** to `www.contoso.com` that overrides the global proxy selection with a proxy server named `alternateproxy` on port 80.</span></span>  
  
## <a name="example"></a><span data-ttu-id="aa7e4-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="aa7e4-105">Example</span></span>  
  
```csharp  
WebRequest req = WebRequest.Create("http://www.contoso.com/");  
req.Proxy = new WebProxy("http://alternateproxy:80/");  
```  
  
```vb  
Dim req As WebRequest = WebRequest.Create("http://www.contoso.com/")  
req.Proxy = New WebProxy("http://alternateproxy:80/")  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="aa7e4-106">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="aa7e4-106">Compiling the Code</span></span>  
 <span data-ttu-id="aa7e4-107">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="aa7e4-107">This example requires:</span></span>  
  
- <span data-ttu-id="aa7e4-108">[ `using` Direttiva](../../csharp/language-reference/keywords/using-directive.md) per lo spazio dei nomi **System.NET** .</span><span class="sxs-lookup"><span data-stu-id="aa7e4-108">A [`using` directive](../../csharp/language-reference/keywords/using-directive.md) for the **System.Net** namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aa7e4-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="aa7e4-109">See also</span></span>

- [<span data-ttu-id="aa7e4-110">Uso di protocolli applicativi</span><span class="sxs-lookup"><span data-stu-id="aa7e4-110">Using Application Protocols</span></span>](using-application-protocols.md)
- [<span data-ttu-id="aa7e4-111">Accesso a Internet tramite un proxy</span><span class="sxs-lookup"><span data-stu-id="aa7e4-111">Accessing the Internet Through a Proxy</span></span>](accessing-the-internet-through-a-proxy.md)
