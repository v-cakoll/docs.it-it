---
title: 'Procedura: Recuperare un oggetto WebResponse specifico del protocollo corrispondente a un oggetto WebRequest'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d8c90785-f16b-42a5-8439-ed2f731b2ba8
ms.openlocfilehash: f1da226fb62c55f37183404765430c094f1cd63f
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2018
ms.locfileid: "50188274"
---
# <a name="how-to-retrieve-a-protocol-specific-webresponse-that-matches-a-webrequest"></a><span data-ttu-id="bda23-102">Procedura: Recuperare un oggetto WebResponse specifico del protocollo corrispondente a un oggetto WebRequest</span><span class="sxs-lookup"><span data-stu-id="bda23-102">How to: Retrieve a Protocol-Specific WebResponse that Matches a WebRequest</span></span>
<span data-ttu-id="bda23-103">Questo esempio mostra come recuperare un oggetto WebResponse specifico del protocollo corrispondente a un oggetto WebRequest.</span><span class="sxs-lookup"><span data-stu-id="bda23-103">This example shows how to retrieve a protocol-specific WebResponse that matches a WebRequest.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bda23-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="bda23-104">Example</span></span>  
  
```csharp  
WebRequest req = WebRequest.Create("http://www.contoso.com/");  
WebResponse resp = req.GetResponse();  
```  
  
```vb  
Dim req As WebRequest = WebRequest.Create("http://www.contoso.com")  
Dim resp As WebResponse = req.GetResponse()  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="bda23-105">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="bda23-105">Compiling the Code</span></span>  
 <span data-ttu-id="bda23-106">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="bda23-106">This example requires:</span></span>  
  
-   <span data-ttu-id="bda23-107">Riferimenti allo spazio dei nomi **System.Net**.</span><span class="sxs-lookup"><span data-stu-id="bda23-107">References to the **System.Net** namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bda23-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bda23-108">See Also</span></span>  
 [<span data-ttu-id="bda23-109">Richiesta di dati</span><span class="sxs-lookup"><span data-stu-id="bda23-109">Requesting Data</span></span>](../../../docs/framework/network-programming/requesting-data.md)
