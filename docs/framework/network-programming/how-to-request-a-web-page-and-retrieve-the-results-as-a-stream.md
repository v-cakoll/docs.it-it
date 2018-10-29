---
title: 'Procedura: Richiedere una pagina Web e recuperare i risultati sotto forma di flusso'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d32b7f35-29d8-4fb7-ad71-d219edc5e359
ms.openlocfilehash: 6481e923c8daabfcfa94adc45d7d4172e47a779a
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/28/2018
ms.locfileid: "50199071"
---
# <a name="how-to-request-a-web-page-and-retrieve-the-results-as-a-stream"></a><span data-ttu-id="30aa5-102">Procedura: Richiedere una pagina Web e recuperare i risultati sotto forma di flusso</span><span class="sxs-lookup"><span data-stu-id="30aa5-102">How to: Request a Web Page and Retrieve the Results as a Stream</span></span>
<span data-ttu-id="30aa5-103">Questo esempio mostra come richiedere una pagina Web e recuperare i risultati in un flusso.</span><span class="sxs-lookup"><span data-stu-id="30aa5-103">This example shows how to request a Web page and retrieve the results in a stream.</span></span>  
  
## <a name="example"></a><span data-ttu-id="30aa5-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="30aa5-104">Example</span></span>  
  
```csharp  
WebClient myClient = new WebClient();  
Stream response = myClient.OpenRead("http://www.contoso.com/index.htm");  
// The stream data is used here.  
response.Close();  
```  
  
```vb  
Dim myClient As WebClient = New WebClient()  
Dim response As Stream = myClient.OpenRead("http://www.contoso.com/index.htm")  
' The stream data is used here.  
response.Close()  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="30aa5-105">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="30aa5-105">Compiling the Code</span></span>  
 <span data-ttu-id="30aa5-106">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="30aa5-106">This example requires:</span></span>  
  
-   <span data-ttu-id="30aa5-107">Riferimenti agli spazi dei nomi <xref:System.IO> e <xref:System.Net>.</span><span class="sxs-lookup"><span data-stu-id="30aa5-107">References to the <xref:System.IO> and <xref:System.Net> namespaces.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="30aa5-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="30aa5-108">See Also</span></span>  
 [<span data-ttu-id="30aa5-109">Richiesta di dati</span><span class="sxs-lookup"><span data-stu-id="30aa5-109">Requesting Data</span></span>](../../../docs/framework/network-programming/requesting-data.md)
