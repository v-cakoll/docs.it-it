---
title: 'Procedura: Consentire a un elemento WebRequest di usare un proxy per comunicare con Internet'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 63c0ef2c-44b5-4c54-9804-ba0b9b001ac7
ms.openlocfilehash: 09a50794995b9157504ceff8dd578d709bfee020
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2018
ms.locfileid: "50190442"
---
# <a name="how-to-enable-a-webrequest-to-use-a-proxy-to-communicate-with-the-internet"></a><span data-ttu-id="e3e73-102">Procedura: Consentire a un elemento WebRequest di usare un proxy per comunicare con Internet</span><span class="sxs-lookup"><span data-stu-id="e3e73-102">How to: Enable a WebRequest to Use a Proxy to Communicate With the Internet</span></span>
<span data-ttu-id="e3e73-103">Questo esempio crea un'istanza del proxy globale che consentirà a qualsiasi <xref:System.Net.WebRequest> di usare un proxy per comunicare con Internet.</span><span class="sxs-lookup"><span data-stu-id="e3e73-103">This example creates a global proxy instance that will enable any <xref:System.Net.WebRequest> to use a proxy to communicate with the Internet.</span></span> <span data-ttu-id="e3e73-104">Nell'esempio si presuppone che il server proxy sia denominato `webproxy` e che comunichi sulla porta 80, ovvero la porta HTTP standard.</span><span class="sxs-lookup"><span data-stu-id="e3e73-104">The example assumes that the proxy server is named `webproxy` and that it communicates on port 80, the standard HTTP port.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e3e73-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="e3e73-105">Example</span></span>  
  
```csharp  
WebProxy proxyObject = new WebProxy("http://webproxy:80/");  
GlobalProxySelection.Select = proxyObject;  
```  
  
```vb  
Dim proxyObject As WebProxy = New WebProxy("http://webproxy:80/")  
GlobalProxySelection.Select = proxyObject  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="e3e73-106">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="e3e73-106">Compiling the Code</span></span>  
 <span data-ttu-id="e3e73-107">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="e3e73-107">This example requires:</span></span>  
  
-   <span data-ttu-id="e3e73-108">Riferimenti allo spazio dei nomi **System.Net**.</span><span class="sxs-lookup"><span data-stu-id="e3e73-108">References to the **System.Net** namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e3e73-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e3e73-109">See Also</span></span>  
 [<span data-ttu-id="e3e73-110">Uso di protocolli applicativi</span><span class="sxs-lookup"><span data-stu-id="e3e73-110">Using Application Protocols</span></span>](../../../docs/framework/network-programming/using-application-protocols.md)  
 [<span data-ttu-id="e3e73-111">Accesso a Internet con un proxy</span><span class="sxs-lookup"><span data-stu-id="e3e73-111">Accessing the Internet Through a Proxy</span></span>](../../../docs/framework/network-programming/accessing-the-internet-through-a-proxy.md)
