---
title: 'Procedura: Consentire a un elemento WebRequest di usare un proxy per comunicare con Internet'
description: Informazioni su come creare un'istanza proxy globale per consentire a qualsiasi WebRequest di usare un proxy per comunicare con Internet nel .NET Framework.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 63c0ef2c-44b5-4c54-9804-ba0b9b001ac7
ms.openlocfilehash: 0fc33cea3f5a7fe4669b110e53e71afdb9561c23
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84502535"
---
# <a name="how-to-enable-a-webrequest-to-use-a-proxy-to-communicate-with-the-internet"></a><span data-ttu-id="a89ef-103">Procedura: Consentire a un elemento WebRequest di usare un proxy per comunicare con Internet</span><span class="sxs-lookup"><span data-stu-id="a89ef-103">How to: Enable a WebRequest to Use a Proxy to Communicate With the Internet</span></span>

<span data-ttu-id="a89ef-104">Questo esempio crea un'istanza del proxy globale che consentirà a qualsiasi <xref:System.Net.WebRequest> di usare un proxy per comunicare con Internet.</span><span class="sxs-lookup"><span data-stu-id="a89ef-104">This example creates a global proxy instance that will enable any <xref:System.Net.WebRequest> to use a proxy to communicate with the Internet.</span></span> <span data-ttu-id="a89ef-105">Nell'esempio si presuppone che il server proxy sia denominato `webproxy` e che comunichi sulla porta 80, ovvero la porta HTTP standard.</span><span class="sxs-lookup"><span data-stu-id="a89ef-105">The example assumes that the proxy server is named `webproxy` and that it communicates on port 80, the standard HTTP port.</span></span>

## <a name="example"></a><span data-ttu-id="a89ef-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="a89ef-106">Example</span></span>

```csharp
var proxyObject = new WebProxy("http://webproxy:80/");
GlobalProxySelection.Select = proxyObject;
```

```vb
Dim proxyObject As New WebProxy("http://webproxy:80/")
GlobalProxySelection.Select = proxyObject
```

## <a name="compiling-the-code"></a><span data-ttu-id="a89ef-107">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="a89ef-107">Compiling the Code</span></span>

<span data-ttu-id="a89ef-108">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="a89ef-108">This example requires:</span></span>

- <span data-ttu-id="a89ef-109">[ `using` Direttiva](../../csharp/language-reference/keywords/using-directive.md) C# per lo spazio dei nomi **System.NET** .</span><span class="sxs-lookup"><span data-stu-id="a89ef-109">A C# [`using` directive](../../csharp/language-reference/keywords/using-directive.md) for the **System.Net** namespace.</span></span>
- <span data-ttu-id="a89ef-110">[ `Imports` Istruzione](../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) Visual Basic per lo spazio dei nomi **System.NET** .</span><span class="sxs-lookup"><span data-stu-id="a89ef-110">A Visual Basic [`Imports` statement](../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) for the **System.Net** namespace.</span></span>

## <a name="see-also"></a><span data-ttu-id="a89ef-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a89ef-111">See also</span></span>

- [<span data-ttu-id="a89ef-112">Uso di protocolli applicativi</span><span class="sxs-lookup"><span data-stu-id="a89ef-112">Using Application Protocols</span></span>](using-application-protocols.md)
- [<span data-ttu-id="a89ef-113">Accesso a Internet tramite un proxy</span><span class="sxs-lookup"><span data-stu-id="a89ef-113">Accessing the Internet Through a Proxy</span></span>](accessing-the-internet-through-a-proxy.md)
