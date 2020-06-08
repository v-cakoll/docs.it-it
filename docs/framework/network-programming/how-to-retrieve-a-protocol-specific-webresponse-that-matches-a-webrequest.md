---
title: 'Procedura: Recuperare un oggetto WebResponse specifico del protocollo corrispondente a un oggetto WebRequest'
description: Informazioni su come recuperare un oggetto WebResponse specifico del protocollo che corrisponde a una WebRequest nell'.NET Framework.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d8c90785-f16b-42a5-8439-ed2f731b2ba8
ms.openlocfilehash: 15b1912a7bd951df7f3c14eb96251c2bdf237b4f
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84502457"
---
# <a name="how-to-retrieve-a-protocol-specific-webresponse-that-matches-a-webrequest"></a><span data-ttu-id="6a7c9-103">Procedura: Recuperare un oggetto WebResponse specifico del protocollo corrispondente a un oggetto WebRequest</span><span class="sxs-lookup"><span data-stu-id="6a7c9-103">How to: Retrieve a Protocol-Specific WebResponse that Matches a WebRequest</span></span>
<span data-ttu-id="6a7c9-104">Questo esempio mostra come recuperare un oggetto WebResponse specifico del protocollo corrispondente a un oggetto WebRequest.</span><span class="sxs-lookup"><span data-stu-id="6a7c9-104">This example shows how to retrieve a protocol-specific WebResponse that matches a WebRequest.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6a7c9-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="6a7c9-105">Example</span></span>  
  
```csharp  
WebRequest req = WebRequest.Create("http://www.contoso.com/");  
WebResponse resp = req.GetResponse();  
```  
  
```vb  
Dim req As WebRequest = WebRequest.Create("http://www.contoso.com")  
Dim resp As WebResponse = req.GetResponse()  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="6a7c9-106">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="6a7c9-106">Compiling the Code</span></span>  
 <span data-ttu-id="6a7c9-107">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="6a7c9-107">This example requires:</span></span>  
  
- <span data-ttu-id="6a7c9-108">Riferimenti allo spazio dei nomi **System.Net**.</span><span class="sxs-lookup"><span data-stu-id="6a7c9-108">References to the **System.Net** namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6a7c9-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6a7c9-109">See also</span></span>

- [<span data-ttu-id="6a7c9-110">Richiesta di dati</span><span class="sxs-lookup"><span data-stu-id="6a7c9-110">Requesting Data</span></span>](requesting-data.md)
