---
title: 'Procedura: Recuperare un oggetto WebResponse specifico del protocollo corrispondente a un oggetto WebRequest'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d8c90785-f16b-42a5-8439-ed2f731b2ba8
ms.openlocfilehash: fee2b725afbceef45b9651a7cd88a61b37952e32
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59087378"
---
# <a name="how-to-retrieve-a-protocol-specific-webresponse-that-matches-a-webrequest"></a><span data-ttu-id="8727d-102">Procedura: Recuperare un oggetto WebResponse specifico del protocollo corrispondente a un oggetto WebRequest</span><span class="sxs-lookup"><span data-stu-id="8727d-102">How to: Retrieve a Protocol-Specific WebResponse that Matches a WebRequest</span></span>
<span data-ttu-id="8727d-103">Questo esempio mostra come recuperare un oggetto WebResponse specifico del protocollo corrispondente a un oggetto WebRequest.</span><span class="sxs-lookup"><span data-stu-id="8727d-103">This example shows how to retrieve a protocol-specific WebResponse that matches a WebRequest.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8727d-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="8727d-104">Example</span></span>  
  
```csharp  
WebRequest req = WebRequest.Create("http://www.contoso.com/");  
WebResponse resp = req.GetResponse();  
```  
  
```vb  
Dim req As WebRequest = WebRequest.Create("http://www.contoso.com")  
Dim resp As WebResponse = req.GetResponse()  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="8727d-105">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="8727d-105">Compiling the Code</span></span>  
 <span data-ttu-id="8727d-106">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="8727d-106">This example requires:</span></span>  
  
-   <span data-ttu-id="8727d-107">Riferimenti allo spazio dei nomi **System.Net**.</span><span class="sxs-lookup"><span data-stu-id="8727d-107">References to the **System.Net** namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8727d-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8727d-108">See also</span></span>

- [<span data-ttu-id="8727d-109">Richiesta di dati</span><span class="sxs-lookup"><span data-stu-id="8727d-109">Requesting Data</span></span>](../../../docs/framework/network-programming/requesting-data.md)
