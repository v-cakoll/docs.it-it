---
title: 'Procedura: Richiedere una pagina Web e recuperare i risultati sotto forma di flusso'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: d32b7f35-29d8-4fb7-ad71-d219edc5e359
caps.latest.revision: "12"
author: mcleblanc
ms.author: markl
manager: markl
ms.workload: dotnet
ms.openlocfilehash: 35b46bcfdbf99b311d5d0c0f8bf81f6cc7961afb
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
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
 [Richiesta di dati](../../../docs/framework/network-programming/requesting-data.md)
