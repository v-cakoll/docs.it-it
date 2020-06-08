---
title: "Procedura: Eseguire l'override di una selezione proxy globale"
description: Seguire questo esempio per eseguire l'override della selezione del proxy globale inviando una WebRequest a un URL, che sostituisce la selezione con un server proxy.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 0da481a9-b414-4230-beb0-e3ceba882fe5
ms.openlocfilehash: 91f64775e2f401be9b740fe9e4c41e1087eb9617
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84502509"
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
  
- [ `using` Direttiva](../../csharp/language-reference/keywords/using-directive.md) per lo spazio dei nomi **System.NET** .  
  
## <a name="see-also"></a>Vedere anche

- [Uso di protocolli applicativi](using-application-protocols.md)
- [Accesso a Internet tramite un proxy](accessing-the-internet-through-a-proxy.md)
