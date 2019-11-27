---
title: Metodo Message. WriteStartHeaders (System. ServiceModel. Channels)
author: mairaw
ms.author: mairaw
ms.date: 11/01/2019
topic_type:
- apiref
api_name:
- System.ServiceModel.Channels.Message.WriteStartHeaders
api_location:
- system.servicemodel.dll
api_type:
- Assembly
ms.openlocfilehash: a2c82ee4029c7af0396219f5ded8c999fd01d65b
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74451178"
---
# <a name="messagewritestartheaders-method"></a>Message. WriteStartHeaders, metodo

Scrive l'intestazione iniziale in un file XML chiamando il metodo <xref:System.ServiceModel.Channels.Message.OnWriteStartHeaders%2A?displayProperty=nameWithType>.

```csharp
internal void WriteStartHeaders(XmlDictionaryWriter writer)
```

## <a name="parameters"></a>Parametri

- `writer` <xref:System.Xml.XmlDictionaryWriter>\
  Writer utilizzato per scrivere l'intestazione iniziale in un file XML.

## <a name="remarks"></a>Osservazioni

> [!WARNING]
> Il `Message.WriteStartHeaders` metodo è interno e non deve essere usato direttamente nel codice.
>
> Microsoft non supporta l'utilizzo di questo metodo in un'applicazione di produzione in qualsiasi circostanza.

## <a name="requirements"></a>Requisiti

**Spazio dei nomi:** <xref:System.ServiceModel.Channels>

**Assembly:** System. ServiceModel. dll

**Versioni .NET Framework:** Disponibile a partire da 3,0.
