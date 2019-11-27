---
title: Metodo Message. BodyToString (System. ServiceModel. Channels)
author: mairaw
ms.author: mairaw
ms.date: 11/01/2019
topic_type:
- apiref
api_name:
- System.ServiceModel.Channels.Message.BodyToString
api_location:
- system.servicemodel.dll
api_type:
- Assembly
ms.openlocfilehash: 7b0b56bfda1c0c37f43f95e9684d3b4042c1b97c
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74451206"
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
