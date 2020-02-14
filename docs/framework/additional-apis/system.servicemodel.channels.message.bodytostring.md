---
title: Metodo Message. BodyToString (System. ServiceModel. Channels)
ms.date: 11/01/2019
topic_type:
- apiref
api_name:
- System.ServiceModel.Channels.Message.BodyToString
api_location:
- system.servicemodel.dll
api_type:
- Assembly
ms.openlocfilehash: 9f1f852c0bd82299fd40afe66a5f90cd7c0335cf
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/14/2020
ms.locfileid: "77215501"
---
# <a name="messagebodytostring-method"></a>Message. BodyToString, metodo

Converte il corpo del messaggio in una stringa chiamando il metodo <xref:System.ServiceModel.Channels.Message.OnBodyToString%2A?displayProperty=nameWithType>.

```csharp
internal void BodyToString(XmlDictionaryWriter writer);
```

## <a name="parameters"></a>Parametri

- `writer` <xref:System.Xml.XmlDictionaryWriter>\
  Writer utilizzato per convertire il corpo del messaggio in una stringa.

## <a name="remarks"></a>Osservazioni

> [!WARNING]
> Il `Message.BodyToString` metodo è interno e non deve essere usato direttamente nel codice.
>
> Microsoft non supporta l'utilizzo di questo metodo in un'applicazione di produzione in qualsiasi circostanza.

## <a name="requirements"></a>Requisiti

**Spazio dei nomi:** <xref:System.ServiceModel.Channels>

**Assembly:** System. ServiceModel. dll

**Versioni .NET Framework:** Disponibile a partire da 3,0.
