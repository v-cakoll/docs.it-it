---
title: "Procedura: Eseguire l'override di una selezione proxy globale"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 0da481a9-b414-4230-beb0-e3ceba882fe5
ms.openlocfilehash: f822aa18b6eecaa1b1302ad6cc6b94f0b016e330
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59127374"
---
# <a name="how-to-override-a-global-proxy-selection"></a>Procedura: Eseguire l'override di una selezione proxy globale
Questo esempio invia un oggetto **WebRequest** a `www.contoso.com` che esegue l'override della selezione del proxy globale con un server proxy denominato `alternateproxy` sulla porta 80.  
  
## <a name="example"></a>Esempio  
  
```csharp  
WebRequest req = WebRequest.Create("http://www.contoso.com/");  
req.Proxy = new WebProxy("http://alternateproxy:80/");  
```  
  
```vb  
Dim req As WebRequest = WebRequest.Create("http://www.contoso.com/")  
req.Proxy = New WebProxy("http://alternateproxy:80/")  
```  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 L'esempio presenta i requisiti seguenti:  
  
-   [Direttiva `using`](~/docs/csharp/language-reference/keywords/using-directive.md) per lo spazio dei nomi **System.Net**.  
  
## <a name="see-also"></a>Vedere anche

- [Uso di protocolli applicativi](../../../docs/framework/network-programming/using-application-protocols.md)
- [Accesso a Internet con un proxy](../../../docs/framework/network-programming/accessing-the-internet-through-a-proxy.md)
