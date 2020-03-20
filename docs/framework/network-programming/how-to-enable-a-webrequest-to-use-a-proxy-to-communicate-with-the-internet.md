---
title: 'Procedura: Consentire a un elemento WebRequest di usare un proxy per comunicare con Internet'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 63c0ef2c-44b5-4c54-9804-ba0b9b001ac7
ms.openlocfilehash: 8b38973e4cb2c83ce32b8a08e54d828a8eeef879
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "73039543"
---
# <a name="how-to-enable-a-webrequest-to-use-a-proxy-to-communicate-with-the-internet"></a><span data-ttu-id="edd7f-102">Procedura: Consentire a un elemento WebRequest di usare un proxy per comunicare con Internet</span><span class="sxs-lookup"><span data-stu-id="edd7f-102">How to: Enable a WebRequest to Use a Proxy to Communicate With the Internet</span></span>

<span data-ttu-id="edd7f-103">Questo esempio crea un'istanza del proxy globale che consentirà a qualsiasi <xref:System.Net.WebRequest> di usare un proxy per comunicare con Internet.</span><span class="sxs-lookup"><span data-stu-id="edd7f-103">This example creates a global proxy instance that will enable any <xref:System.Net.WebRequest> to use a proxy to communicate with the Internet.</span></span> <span data-ttu-id="edd7f-104">Nell'esempio si presuppone che il server proxy sia denominato `webproxy` e che comunichi sulla porta 80, ovvero la porta HTTP standard.</span><span class="sxs-lookup"><span data-stu-id="edd7f-104">The example assumes that the proxy server is named `webproxy` and that it communicates on port 80, the standard HTTP port.</span></span>

## <a name="example"></a><span data-ttu-id="edd7f-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="edd7f-105">Example</span></span>

```csharp
var proxyObject = new WebProxy("http://webproxy:80/");
GlobalProxySelection.Select = proxyObject;
```

```vb
Dim proxyObject As New WebProxy("http://webproxy:80/")
GlobalProxySelection.Select = proxyObject
```

## <a name="compiling-the-code"></a><span data-ttu-id="edd7f-106">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="edd7f-106">Compiling the Code</span></span>

<span data-ttu-id="edd7f-107">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="edd7f-107">This example requires:</span></span>

- <span data-ttu-id="edd7f-108">Una [ `using` direttiva](../../csharp/language-reference/keywords/using-directive.md) di C per lo spazio dei nomi **System.Net.**</span><span class="sxs-lookup"><span data-stu-id="edd7f-108">A C# [`using` directive](../../csharp/language-reference/keywords/using-directive.md) for the **System.Net** namespace.</span></span>
- <span data-ttu-id="edd7f-109">[ `Imports` Un'istruzione](../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) di Visual Basic per lo spazio dei nomi **System.Net.**</span><span class="sxs-lookup"><span data-stu-id="edd7f-109">A Visual Basic [`Imports` statement](../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) for the **System.Net** namespace.</span></span>

## <a name="see-also"></a><span data-ttu-id="edd7f-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="edd7f-110">See also</span></span>

- [<span data-ttu-id="edd7f-111">Uso di protocolli applicativi</span><span class="sxs-lookup"><span data-stu-id="edd7f-111">Using Application Protocols</span></span>](using-application-protocols.md)
- [<span data-ttu-id="edd7f-112">Accesso a Internet tramite un proxy</span><span class="sxs-lookup"><span data-stu-id="edd7f-112">Accessing the Internet Through a Proxy</span></span>](accessing-the-internet-through-a-proxy.md)
