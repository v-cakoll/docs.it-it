---
title: 'Procedura: Richiedere una pagina Web e recuperare i risultati sotto forma di flusso'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d32b7f35-29d8-4fb7-ad71-d219edc5e359
ms.openlocfilehash: 65bda268cd77959dbcd786c365d0a30c324b89ce
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "71393104"
---
# <a name="how-to-request-a-web-page-and-retrieve-the-results-as-a-stream"></a><span data-ttu-id="cd019-102">Procedura: Richiedere una pagina Web e recuperare i risultati sotto forma di flusso</span><span class="sxs-lookup"><span data-stu-id="cd019-102">How to: Request a Web Page and Retrieve the Results as a Stream</span></span>

<span data-ttu-id="cd019-103">Questo esempio mostra come richiedere una pagina Web e recuperare i risultati in un flusso.</span><span class="sxs-lookup"><span data-stu-id="cd019-103">This example shows how to request a Web page and retrieve the results in a stream.</span></span>
  
## <a name="example"></a><span data-ttu-id="cd019-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="cd019-104">Example</span></span>

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

## <a name="compiling-the-code"></a><span data-ttu-id="cd019-105">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="cd019-105">Compiling the Code</span></span>

 <span data-ttu-id="cd019-106">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="cd019-106">This example requires:</span></span>

- <span data-ttu-id="cd019-107">Riferimenti agli spazi dei nomi <xref:System.IO> e <xref:System.Net>.</span><span class="sxs-lookup"><span data-stu-id="cd019-107">References to the <xref:System.IO> and <xref:System.Net> namespaces.</span></span>

## <a name="see-also"></a><span data-ttu-id="cd019-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cd019-108">See also</span></span>

- [<span data-ttu-id="cd019-109">Richiesta di dati</span><span class="sxs-lookup"><span data-stu-id="cd019-109">Requesting Data</span></span>](requesting-data.md)
