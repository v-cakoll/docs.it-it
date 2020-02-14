---
title: Metodo Message. WriteStartHeaders (System. ServiceModel. Channels)
ms.date: 11/01/2019
topic_type:
- apiref
api_name:
- System.ServiceModel.Channels.Message.WriteStartHeaders
api_location:
- system.servicemodel.dll
api_type:
- Assembly
ms.openlocfilehash: c826e6a3b976e5705e9815586441e8a25b64f76e
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/14/2020
ms.locfileid: "77214869"
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
