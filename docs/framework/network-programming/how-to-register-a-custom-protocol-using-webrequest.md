---
title: 'Procedura: Registrare un protocollo personalizzato con WebRequest'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 98ddbdb9-66b1-4080-92ad-51f5c447fcf8
ms.openlocfilehash: d2056bee6c8847989556799511dfaea326dcdac1
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54669042"
---
# <a name="how-to-register-a-custom-protocol-using-webrequest"></a>Procedura: Registrare un protocollo personalizzato con WebRequest
Questo esempio illustra come registrare una classe specifica di un protocollo definita altrove. In questo esempio, `CustomWebRequestCreator` è l'oggetto implementato dall'utente che implementa il metodo **Create** che restituisce l'oggetto `CustomWebRequest`. Nell'esempio di codice si presuppone che sia stato scritto il codice `CustomWebRequest` che implementa il protocollo personalizzato.  
  
## <a name="example"></a>Esempio  
  
```csharp  
WebRequest.RegisterPrefix("custom", new CustomWebRequestCreator());  
WebRequest req = WebRequest.Create("custom://customHost.contoso.com/");  
```  
  
```vb  
WebRequest.RegisterPrefix("custom", New CustomWebRequestCreator())  
Dim req As WebRequest = WebRequest.Create("custom://customHost.contoso.com/")  
```  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 L'esempio presenta i requisiti seguenti:  
  
 Riferimenti allo spazio dei nomi <xref:System.Net>.  
  
## <a name="see-also"></a>Vedere anche
- [Programmazione di protocolli di collegamento](../../../docs/framework/network-programming/programming-pluggable-protocols.md)
