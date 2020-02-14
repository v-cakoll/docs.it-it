---
title: Metodo MemoryStream. InternalGetOriginAndLength (System.IO)
ms.date: 11/19/2019
topic_type:
- apiref
api_name:
- System.IO.MemoryStream.InternalGetOriginAndLength
api_location:
- mscorlib.dll
api_type:
- Assembly
ms.openlocfilehash: d82b5080e9fbd5fc6603f1cddae996c75a06d3a3
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/14/2020
ms.locfileid: "77215471"
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
