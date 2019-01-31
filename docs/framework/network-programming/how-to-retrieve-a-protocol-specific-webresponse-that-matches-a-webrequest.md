---
title: 'Procedura: Recuperare un oggetto WebResponse specifico del protocollo corrispondente a un oggetto WebRequest'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d8c90785-f16b-42a5-8439-ed2f731b2ba8
ms.openlocfilehash: 3b3b523d6248b3c61a0994728b035bc6f02d5cf1
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54745349"
---
# <a name="how-to-retrieve-a-protocol-specific-webresponse-that-matches-a-webrequest"></a><span data-ttu-id="d03ea-102">Procedura: Recuperare un oggetto WebResponse specifico del protocollo corrispondente a un oggetto WebRequest</span><span class="sxs-lookup"><span data-stu-id="d03ea-102">How to: Retrieve a Protocol-Specific WebResponse that Matches a WebRequest</span></span>
<span data-ttu-id="d03ea-103">Questo esempio mostra come recuperare un oggetto WebResponse specifico del protocollo corrispondente a un oggetto WebRequest.</span><span class="sxs-lookup"><span data-stu-id="d03ea-103">This example shows how to retrieve a protocol-specific WebResponse that matches a WebRequest.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d03ea-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="d03ea-104">Example</span></span>  
  
```csharp  
WebRequest req = WebRequest.Create("http://www.contoso.com/");  
WebResponse resp = req.GetResponse();  
```  
  
```vb  
Dim req As WebRequest = WebRequest.Create("http://www.contoso.com")  
Dim resp As WebResponse = req.GetResponse()  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="d03ea-105">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="d03ea-105">Compiling the Code</span></span>  
 <span data-ttu-id="d03ea-106">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="d03ea-106">This example requires:</span></span>  
  
-   <span data-ttu-id="d03ea-107">Riferimenti allo spazio dei nomi **System.Net**.</span><span class="sxs-lookup"><span data-stu-id="d03ea-107">References to the **System.Net** namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d03ea-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d03ea-108">See also</span></span>
- [<span data-ttu-id="d03ea-109">Richiesta di dati</span><span class="sxs-lookup"><span data-stu-id="d03ea-109">Requesting Data</span></span>](../../../docs/framework/network-programming/requesting-data.md)
