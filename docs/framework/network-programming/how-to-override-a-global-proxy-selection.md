---
title: "Procedura: Eseguire l'override di una selezione proxy globale"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 0da481a9-b414-4230-beb0-e3ceba882fe5
author: mcleblanc
ms.author: markl
ms.openlocfilehash: 2be271123e34f155a79269d3b810c50fe24a40c6
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/29/2018
ms.locfileid: "47235939"
---
# <a name="how-to-override-a-global-proxy-selection"></a><span data-ttu-id="8019b-102">Procedura: Eseguire l'override di una selezione proxy globale</span><span class="sxs-lookup"><span data-stu-id="8019b-102">How to: Override a Global Proxy Selection</span></span>
<span data-ttu-id="8019b-103">Questo esempio invia un oggetto **WebRequest** a `www.contoso.com` che esegue l'override della selezione del proxy globale con un server proxy denominato `alternateproxy` sulla porta 80.</span><span class="sxs-lookup"><span data-stu-id="8019b-103">This example sends a **WebRequest** to `www.contoso.com` that overrides the global proxy selection with a proxy server named `alternateproxy` on port 80.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8019b-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="8019b-104">Example</span></span>  
  
```csharp  
WebRequest req = WebRequest.Create("http://www.contoso.com/");  
req.Proxy = new WebProxy("http://alternateproxy:80/");  
```  
  
```vb  
Dim req As WebRequest = WebRequest.Create("http://www.contoso.com/")  
req.Proxy = New WebProxy("http://alternateproxy:80/")  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="8019b-105">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="8019b-105">Compiling the Code</span></span>  
 <span data-ttu-id="8019b-106">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="8019b-106">This example requires:</span></span>  
  
-   <span data-ttu-id="8019b-107">[Direttiva `using`](~/docs/csharp/language-reference/keywords/using-directive.md) per lo spazio dei nomi **System.Net**.</span><span class="sxs-lookup"><span data-stu-id="8019b-107">A [`using` directive](~/docs/csharp/language-reference/keywords/using-directive.md) for the **System.Net** namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8019b-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8019b-108">See Also</span></span>  
 [<span data-ttu-id="8019b-109">Uso di protocolli applicativi</span><span class="sxs-lookup"><span data-stu-id="8019b-109">Using Application Protocols</span></span>](../../../docs/framework/network-programming/using-application-protocols.md)  
 [<span data-ttu-id="8019b-110">Accesso a Internet con un proxy</span><span class="sxs-lookup"><span data-stu-id="8019b-110">Accessing the Internet Through a Proxy</span></span>](../../../docs/framework/network-programming/accessing-the-internet-through-a-proxy.md)
