---
title: 'Procedura: Richiedere una pagina Web e recuperare i risultati sotto forma di flusso'
description: Questo esempio illustra come richiedere una pagina Web e recuperare i risultati in un flusso nel .NET Framework.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d32b7f35-29d8-4fb7-ad71-d219edc5e359
ms.openlocfilehash: bd57f9af6be29c783d044e785ebb36aaa8592df2
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84502483"
---
# <a name="how-to-request-a-web-page-and-retrieve-the-results-as-a-stream"></a><span data-ttu-id="b25a2-103">Procedura: Richiedere una pagina Web e recuperare i risultati sotto forma di flusso</span><span class="sxs-lookup"><span data-stu-id="b25a2-103">How to: Request a Web Page and Retrieve the Results as a Stream</span></span>

<span data-ttu-id="b25a2-104">Questo esempio mostra come richiedere una pagina Web e recuperare i risultati in un flusso.</span><span class="sxs-lookup"><span data-stu-id="b25a2-104">This example shows how to request a Web page and retrieve the results in a stream.</span></span>
  
## <a name="example"></a><span data-ttu-id="b25a2-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="b25a2-105">Example</span></span>

```csharp
var myClient = new WebClient();
Stream response = myClient.OpenRead("https://docs.microsoft.com/dotnet/");
// The stream data is used here.
response.Close();
```

```vb
Dim myClient As New WebClient()
Dim response As Stream = myClient.OpenRead("https://docs.microsoft.com/dotnet/")
' The stream data is used here.
response.Close()
```

## <a name="compiling-the-code"></a><span data-ttu-id="b25a2-106">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="b25a2-106">Compiling the Code</span></span>

 <span data-ttu-id="b25a2-107">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="b25a2-107">This example requires:</span></span>

- <span data-ttu-id="b25a2-108">Riferimenti agli spazi dei nomi <xref:System.IO> e <xref:System.Net>.</span><span class="sxs-lookup"><span data-stu-id="b25a2-108">References to the <xref:System.IO> and <xref:System.Net> namespaces.</span></span>

## <a name="see-also"></a><span data-ttu-id="b25a2-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b25a2-109">See also</span></span>

- [<span data-ttu-id="b25a2-110">Richiesta di dati</span><span class="sxs-lookup"><span data-stu-id="b25a2-110">Requesting Data</span></span>](requesting-data.md)
