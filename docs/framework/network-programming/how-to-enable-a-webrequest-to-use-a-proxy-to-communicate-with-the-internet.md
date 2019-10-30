---
title: 'Procedura: Consentire a un elemento WebRequest di usare un proxy per comunicare con Internet'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 63c0ef2c-44b5-4c54-9804-ba0b9b001ac7
ms.openlocfilehash: 8b38973e4cb2c83ce32b8a08e54d828a8eeef879
ms.sourcegitcommit: ad800f019ac976cb669e635fb0ea49db740e6890
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/29/2019
ms.locfileid: "73039543"
---
# <a name="how-to-enable-a-webrequest-to-use-a-proxy-to-communicate-with-the-internet"></a><span data-ttu-id="4f62b-102">Procedura: Consentire a un elemento WebRequest di usare un proxy per comunicare con Internet</span><span class="sxs-lookup"><span data-stu-id="4f62b-102">How to: Enable a WebRequest to Use a Proxy to Communicate With the Internet</span></span>

<span data-ttu-id="4f62b-103">Questo esempio crea un'istanza del proxy globale che consentirà a qualsiasi <xref:System.Net.WebRequest> di usare un proxy per comunicare con Internet.</span><span class="sxs-lookup"><span data-stu-id="4f62b-103">This example creates a global proxy instance that will enable any <xref:System.Net.WebRequest> to use a proxy to communicate with the Internet.</span></span> <span data-ttu-id="4f62b-104">Nell'esempio si presuppone che il server proxy sia denominato `webproxy` e che comunichi sulla porta 80, ovvero la porta HTTP standard.</span><span class="sxs-lookup"><span data-stu-id="4f62b-104">The example assumes that the proxy server is named `webproxy` and that it communicates on port 80, the standard HTTP port.</span></span>

## <a name="example"></a><span data-ttu-id="4f62b-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="4f62b-105">Example</span></span>

```csharp
var proxyObject = new WebProxy("http://webproxy:80/");
GlobalProxySelection.Select = proxyObject;
```

```vb
Dim proxyObject As New WebProxy("http://webproxy:80/")
GlobalProxySelection.Select = proxyObject
```

## <a name="compiling-the-code"></a><span data-ttu-id="4f62b-106">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="4f62b-106">Compiling the Code</span></span>

<span data-ttu-id="4f62b-107">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="4f62b-107">This example requires:</span></span>

- <span data-ttu-id="4f62b-108">C# [Direttiva`using`](../../csharp/language-reference/keywords/using-directive.md) per lo spazio dei nomi **System.NET** .</span><span class="sxs-lookup"><span data-stu-id="4f62b-108">A C# [`using` directive](../../csharp/language-reference/keywords/using-directive.md) for the **System.Net** namespace.</span></span>
- <span data-ttu-id="4f62b-109">Visual Basic [`Imports` istruzione](../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) per lo spazio dei nomi **System.NET** .</span><span class="sxs-lookup"><span data-stu-id="4f62b-109">A Visual Basic [`Imports` statement](../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) for the **System.Net** namespace.</span></span>

## <a name="see-also"></a><span data-ttu-id="4f62b-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4f62b-110">See also</span></span>

- [<span data-ttu-id="4f62b-111">Uso di protocolli applicativi</span><span class="sxs-lookup"><span data-stu-id="4f62b-111">Using Application Protocols</span></span>](using-application-protocols.md)
- [<span data-ttu-id="4f62b-112">Accesso a Internet con un proxy</span><span class="sxs-lookup"><span data-stu-id="4f62b-112">Accessing the Internet Through a Proxy</span></span>](accessing-the-internet-through-a-proxy.md)
