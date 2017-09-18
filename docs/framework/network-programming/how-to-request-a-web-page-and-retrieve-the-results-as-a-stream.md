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
- VB
- CSharp
- C++
- jsharp
ms.assetid: d32b7f35-29d8-4fb7-ad71-d219edc5e359
caps.latest.revision: 12
author: mcleblanc
ms.author: markl
manager: markl
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: ec19e46289131ec137081c610c1a8194ad22611f
ms.contentlocale: it-it
ms.lasthandoff: 08/21/2017

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

