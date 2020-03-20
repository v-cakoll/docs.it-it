---
title: 'Procedura: Eseguire il cast di tipo di un oggetto WebRequest per accedere a proprietà specifiche del protocollo'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d9a8eae2-7454-46f9-b43b-c98477c5bcde
ms.openlocfilehash: d38a40aa1e6e3db769aedfc440077721cdfaf06d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "79180752"
---
# <a name="how-to-typecast-a-webrequest-to-access-protocol-specific-properties"></a><span data-ttu-id="5dcd0-102">Procedura: Eseguire il cast di tipo di un oggetto WebRequest per accedere a proprietà specifiche del protocollo</span><span class="sxs-lookup"><span data-stu-id="5dcd0-102">How to: Typecast a WebRequest to Access Protocol Specific Properties</span></span>
<span data-ttu-id="5dcd0-103">Questo esempio mostra come eseguire il cast di tipo di un oggetto WebRequest in modo da poter accedere a proprietà specifiche del protocollo.</span><span class="sxs-lookup"><span data-stu-id="5dcd0-103">This example shows how to typecast a WebRequest so that you can access protocol specific properties.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5dcd0-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="5dcd0-104">Example</span></span>  
  
```csharp  
HttpWebRequest httpreq =
   (HttpWebRequest) WebRequest.Create("http://www.contoso.com/");  
```  
  
```vb  
Dim httpreq As HttpWebRequest = _  
   CType(WebRequest.Create("http://www.contoso.com/"), HttpWebRequest)  
```  
  
## <a name="see-also"></a><span data-ttu-id="5dcd0-105">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5dcd0-105">See also</span></span>

- [<span data-ttu-id="5dcd0-106">programmazione di protocolli di collegamento</span><span class="sxs-lookup"><span data-stu-id="5dcd0-106">Programming Pluggable Protocols</span></span>](programming-pluggable-protocols.md)
