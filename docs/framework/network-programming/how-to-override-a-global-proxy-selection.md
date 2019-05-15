---
title: "Procedura: Eseguire l'override di una selezione proxy globale"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 0da481a9-b414-4230-beb0-e3ceba882fe5
ms.openlocfilehash: 2389ea01a980f80c7723f9b481ede2e1fe915b28
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64624533"
---
# <a name="how-to-override-a-global-proxy-selection"></a><span data-ttu-id="e7357-102">Procedura: Eseguire l'override di una selezione proxy globale</span><span class="sxs-lookup"><span data-stu-id="e7357-102">How to: Override a Global Proxy Selection</span></span>
<span data-ttu-id="e7357-103">Questo esempio invia un oggetto **WebRequest** a `www.contoso.com` che esegue l'override della selezione del proxy globale con un server proxy denominato `alternateproxy` sulla porta 80.</span><span class="sxs-lookup"><span data-stu-id="e7357-103">This example sends a **WebRequest** to `www.contoso.com` that overrides the global proxy selection with a proxy server named `alternateproxy` on port 80.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e7357-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="e7357-104">Example</span></span>  
  
```csharp  
WebRequest req = WebRequest.Create("http://www.contoso.com/");  
req.Proxy = new WebProxy("http://alternateproxy:80/");  
```  
  
```vb  
Dim req As WebRequest = WebRequest.Create("http://www.contoso.com/")  
req.Proxy = New WebProxy("http://alternateproxy:80/")  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="e7357-105">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="e7357-105">Compiling the Code</span></span>  
 <span data-ttu-id="e7357-106">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="e7357-106">This example requires:</span></span>  
  
- <span data-ttu-id="e7357-107">[Direttiva `using`](~/docs/csharp/language-reference/keywords/using-directive.md) per lo spazio dei nomi **System.Net**.</span><span class="sxs-lookup"><span data-stu-id="e7357-107">A [`using` directive](~/docs/csharp/language-reference/keywords/using-directive.md) for the **System.Net** namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e7357-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e7357-108">See also</span></span>

- [<span data-ttu-id="e7357-109">Uso di protocolli applicativi</span><span class="sxs-lookup"><span data-stu-id="e7357-109">Using Application Protocols</span></span>](../../../docs/framework/network-programming/using-application-protocols.md)
- [<span data-ttu-id="e7357-110">Accesso a Internet con un proxy</span><span class="sxs-lookup"><span data-stu-id="e7357-110">Accessing the Internet Through a Proxy</span></span>](../../../docs/framework/network-programming/accessing-the-internet-through-a-proxy.md)
