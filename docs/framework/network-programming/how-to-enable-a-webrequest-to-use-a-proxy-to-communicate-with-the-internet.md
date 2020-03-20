---
title: 'Procedura: Consentire a un elemento WebRequest di usare un proxy per comunicare con Internet'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 63c0ef2c-44b5-4c54-9804-ba0b9b001ac7
ms.openlocfilehash: 8b38973e4cb2c83ce32b8a08e54d828a8eeef879
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "73039543"
---
# <a name="how-to-enable-a-webrequest-to-use-a-proxy-to-communicate-with-the-internet"></a>Procedura: Consentire a un elemento WebRequest di usare un proxy per comunicare con Internet

Questo esempio crea un'istanza del proxy globale che consentirà a qualsiasi <xref:System.Net.WebRequest> di usare un proxy per comunicare con Internet. Nell'esempio si presuppone che il server proxy sia denominato `webproxy` e che comunichi sulla porta 80, ovvero la porta HTTP standard.

## <a name="example"></a>Esempio

```csharp
var proxyObject = new WebProxy("http://webproxy:80/");
GlobalProxySelection.Select = proxyObject;
```

```vb
Dim proxyObject As New WebProxy("http://webproxy:80/")
GlobalProxySelection.Select = proxyObject
```

## <a name="compiling-the-code"></a>Compilazione del codice

L'esempio presenta i requisiti seguenti:

- Una [ `using` direttiva](../../csharp/language-reference/keywords/using-directive.md) di C per lo spazio dei nomi **System.Net.**
- [ `Imports` Un'istruzione](../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) di Visual Basic per lo spazio dei nomi **System.Net.**

## <a name="see-also"></a>Vedere anche

- [Uso di protocolli applicativi](using-application-protocols.md)
- [Accesso a Internet tramite un proxy](accessing-the-internet-through-a-proxy.md)
