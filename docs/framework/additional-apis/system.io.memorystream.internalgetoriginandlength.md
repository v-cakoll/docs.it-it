---
title: Metodo MemoryStream. InternalGetOriginAndLength (System.IO)
author: mairaw
ms.author: mairaw
ms.date: 11/19/2019
topic_type:
- apiref
api_name:
- System.IO.MemoryStream.InternalGetOriginAndLength
api_location:
- mscorlib.dll
api_type:
- Assembly
ms.openlocfilehash: d2bfa087fe2fb247f963cfa687c27056363d5696
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2019
ms.locfileid: "74284031"
---
# <a name="memorystreaminternalgetoriginandlength-method"></a>MemoryStream. InternalGetOriginAndLength, metodo

Ottiene i valori interni dell'origine e della lunghezza del flusso di memoria.

```csharp
internal void InternalGetOriginAndLength(out int origin, out int length)
```

## <a name="parameters"></a>Parametri

- `origin` <xref:System.Int32>\
  Quando questo metodo restituisce, l'offset della matrice di byte specificata durante la creazione di un nuovo oggetto <xref:System.IO.MemoryStream>. Contiene 0 se la matrice di byte è stata creata da <xref:System.IO.MemoryStream>.

- `length` <xref:System.Int32>\
  Quando questo metodo restituisce, il numero di byte all'interno del flusso di memoria.

## <a name="remarks"></a>Osservazioni

> [!WARNING]
> Il `MemoryStream.InternalGetOriginAndLength` metodo è interno e non deve essere usato direttamente nel codice.
>
> Microsoft non supporta l'utilizzo di questo metodo in un'applicazione di produzione in qualsiasi circostanza.

## <a name="requirements"></a>Requisiti

**Spazio dei nomi:** <xref:System.IO>

**Assembly:** mscorlib. dll (in mscorlib. dll)

**Versioni .NET Framework:** Disponibile a partire da 2,0.
