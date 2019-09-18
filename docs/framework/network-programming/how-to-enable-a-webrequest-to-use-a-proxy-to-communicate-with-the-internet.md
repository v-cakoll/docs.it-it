---
title: 'Procedura: Consentire a un elemento WebRequest di usare un proxy per comunicare con Internet'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 63c0ef2c-44b5-4c54-9804-ba0b9b001ac7
ms.openlocfilehash: d569603fe22e5d8c8f59d21c2777c7c1bfcd531d
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/17/2019
ms.locfileid: "71048288"
---
# <a name="how-to-enable-a-webrequest-to-use-a-proxy-to-communicate-with-the-internet"></a>Procedura: Consentire a un elemento WebRequest di usare un proxy per comunicare con Internet
Questo esempio crea un'istanza del proxy globale che consentirà a qualsiasi <xref:System.Net.WebRequest> di usare un proxy per comunicare con Internet. Nell'esempio si presuppone che il server proxy sia denominato `webproxy` e che comunichi sulla porta 80, ovvero la porta HTTP standard.  
  
## <a name="example"></a>Esempio  
  
```csharp  
WebProxy proxyObject = new WebProxy("http://webproxy:80/");  
GlobalProxySelection.Select = proxyObject;  
```  
  
```vb  
Dim proxyObject As WebProxy = New WebProxy("http://webproxy:80/")  
GlobalProxySelection.Select = proxyObject  
```  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 L'esempio presenta i requisiti seguenti:  
  
- [Direttiva `using`](../../csharp/language-reference/keywords/using-directive.md) per lo spazio dei nomi **System.Net**.  
  
## <a name="see-also"></a>Vedere anche

- [Uso di protocolli applicativi](using-application-protocols.md)
- [Accesso a Internet con un proxy](accessing-the-internet-through-a-proxy.md)
