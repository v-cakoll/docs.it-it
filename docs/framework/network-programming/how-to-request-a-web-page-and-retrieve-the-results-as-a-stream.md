---
title: 'Procedura: Richiedere una pagina Web e recuperare i risultati sotto forma di flusso'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d32b7f35-29d8-4fb7-ad71-d219edc5e359
ms.openlocfilehash: 23c094f0a3f528750c9589dbc99a0ada86236967
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59097200"
---
# <a name="how-to-request-a-web-page-and-retrieve-the-results-as-a-stream"></a><span data-ttu-id="a4af2-102">Procedura: Richiedere una pagina Web e recuperare i risultati sotto forma di flusso</span><span class="sxs-lookup"><span data-stu-id="a4af2-102">How to: Request a Web Page and Retrieve the Results as a Stream</span></span>
<span data-ttu-id="a4af2-103">Questo esempio mostra come richiedere una pagina Web e recuperare i risultati in un flusso.</span><span class="sxs-lookup"><span data-stu-id="a4af2-103">This example shows how to request a Web page and retrieve the results in a stream.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a4af2-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="a4af2-104">Example</span></span>  
  
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
  
## <a name="compiling-the-code"></a><span data-ttu-id="a4af2-105">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="a4af2-105">Compiling the Code</span></span>  
 <span data-ttu-id="a4af2-106">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="a4af2-106">This example requires:</span></span>  
  
-   <span data-ttu-id="a4af2-107">Riferimenti agli spazi dei nomi <xref:System.IO> e <xref:System.Net>.</span><span class="sxs-lookup"><span data-stu-id="a4af2-107">References to the <xref:System.IO> and <xref:System.Net> namespaces.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a4af2-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a4af2-108">See also</span></span>

- [<span data-ttu-id="a4af2-109">Richiesta di dati</span><span class="sxs-lookup"><span data-stu-id="a4af2-109">Requesting Data</span></span>](../../../docs/framework/network-programming/requesting-data.md)
