---
title: Serializzazione selettiva
description: Questo articolo illustra come contrassegnare i campi con l'attributo non serializzato, che impedisce la serializzazione del campo.
ms.date: 08/07/2017
dev_langs:
- CSharp
helpviewer_keywords:
- serialization, selective serialization
- binary serialization, selective serialization
ms.assetid: 39c56635-95d2-4afd-aff1-b022e7649bb3
ms.openlocfilehash: 74113979f0ebe77319ae308c2a669e91d8cb4209
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "84278415"
---
# <a name="selective-serialization"></a>Serializzazione selettiva
Una classe spesso contiene campi che non devono essere serializzati. Ad esempio, si prenda in considerazione una classe che archivia un ID del thread in una variabile membro. Quando la classe viene deserializzata, il thread archivia l'ID nel caso in cui la classe serializzata non sia più in esecuzione. La serializzazione di questo valore non ha quindi senso. È possibile evitare che le variabili membro vengano serializzate contrassegnandole con l'attributo [NonSerialized](xref:System.NonSerializedAttribute) come riportato di seguito.  
  
```csharp  
[Serializable]  
public class MyObject
{  
  public int n1;  
  [NonSerialized] public int n2;  
  public String str;  
}  
```

Se possibile, rendere non serializzabili gli oggetti che possono contenere dati sensibili alla sicurezza. Se l'oggetto deve essere serializzato, applicare l'attributo `NonSerialized` ai campi specifici che archiviano dati sensibili. Se non si escludono questi campi dalla serializzazione, è necessario essere consapevoli che i dati archiviati sono esposti a qualsiasi codice con le autorizzazioni per la serializzazione. Per altre informazioni sulla scrittura di codice di serializzazione sicuro, vedere [Sicurezza e serializzazione](../../framework/misc/security-and-serialization.md).

[!INCLUDE [binary-serialization-warning](../../../includes/binary-serialization-warning.md)]
  
## <a name="see-also"></a>Vedi anche

- [Serializzazione binaria](binary-serialization.md)
- [Serializzazione SOAP e XML](xml-and-soap-serialization.md)
- [Sicurezza e serializzazione](../../framework/misc/security-and-serialization.md)
