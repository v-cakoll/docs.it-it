---
title: 'Procedura: Richiedere una pagina Web e recuperare i risultati sotto forma di flusso'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d32b7f35-29d8-4fb7-ad71-d219edc5e359
ms.openlocfilehash: 23c094f0a3f528750c9589dbc99a0ada86236967
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59097200"
---
# <a name="how-to-request-a-web-page-and-retrieve-the-results-as-a-stream"></a>Procedura: Richiedere una pagina Web e recuperare i risultati sotto forma di flusso
Questo esempio mostra come richiedere una pagina Web e recuperare i risultati in un flusso.  
  
## <a name="example"></a>Esempio  
  
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
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 L'esempio presenta i requisiti seguenti:  
  
-   Riferimenti agli spazi dei nomi <xref:System.IO> e <xref:System.Net>.  
  
## <a name="see-also"></a>Vedere anche

- [Richiesta di dati](../../../docs/framework/network-programming/requesting-data.md)
