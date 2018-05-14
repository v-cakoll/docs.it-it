---
title: "Procedura: Eseguire l'override di una selezione proxy globale"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 0da481a9-b414-4230-beb0-e3ceba882fe5
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: c10cff979a18d8e07a1e7089f96157e4c38f040e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-override-a-global-proxy-selection"></a>Procedura: Eseguire l'override di una selezione proxy globale
Questo esempio invia un oggetto **WebRequest** a www.contoso.com che esegue l'override della selezione del proxy globale con un server proxy denominato `alternateproxy` sulla porta 80.  
  
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
  
-   Riferimenti allo spazio dei nomi **System.Net**.  
  
## <a name="see-also"></a>Vedere anche  
 [Uso di protocolli applicativi](../../../docs/framework/network-programming/using-application-protocols.md)  
 [Accesso a Internet con un proxy](../../../docs/framework/network-programming/accessing-the-internet-through-a-proxy.md)
