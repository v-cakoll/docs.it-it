---
title: 'Procedura: Consentire a un elemento WebRequest di usare un proxy per comunicare con Internet'
description: Informazioni su come creare un'istanza proxy globale per consentire a qualsiasi WebRequest di usare un proxy per comunicare con Internet nel .NET Framework.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 63c0ef2c-44b5-4c54-9804-ba0b9b001ac7
ms.openlocfilehash: 0fc33cea3f5a7fe4669b110e53e71afdb9561c23
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84502535"
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

- [ `using` Direttiva](../../csharp/language-reference/keywords/using-directive.md) C# per lo spazio dei nomi **System.NET** .
- [ `Imports` Istruzione](../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) Visual Basic per lo spazio dei nomi **System.NET** .

## <a name="see-also"></a>Vedere anche

- [Uso di protocolli applicativi](using-application-protocols.md)
- [Accesso a Internet tramite un proxy](accessing-the-internet-through-a-proxy.md)
