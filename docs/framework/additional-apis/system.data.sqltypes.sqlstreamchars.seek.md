---
title: Metodo SqlStreamChars.Seek (Int64, SeekOrigin) (System.Data.SqlTypes)
author: stevestein
ms.author: sstein
ms.date: 12/20/2018
ms.technology: dotnet-data
topic_type:
- apiref
api_name:
- System.Data.SqlTypes.SqlStreamChars.Seek
api_location:
- System.Data.dll
api_type:
- Assembly
ms.openlocfilehash: 6f802428a73f229e948099788ec21f07efbfab76
ms.sourcegitcommit: d938c39afb9216db377d0f0ecdaa53936a851059
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/29/2019
ms.locfileid: "58634518"
---
# <a name="sqlstreamcharsseekint64-seekorigin-method"></a>Metodo SqlStreamChars.Seek (Int64, SeekOrigin)

Quando ne viene eseguito l'override in una classe derivata, imposta la posizione all'interno del flusso corrente. L'assembly contenente questo metodo ha una relazione di tipo friend SQLAccess. Si tratta per l'uso da SQL Server. Per altri database, usare il meccanismo di hosting fornito da tale database.

```csharp
public abstract long Seek (long offset, System.IO.SeekOrigin origin);
```

## <a name="parameters"></a>Parametri

`offset`\
Offset dei byte rispetto a `origin`.

`origin`\
Uno dei valori di enumerazione che indica il punto di riferimento da cui ottenere la nuova posizione.

## <a name="returns"></a>Valore restituito

<xref:System.Int32>\
Nuova posizione all'interno del flusso corrente.

## <a name="remarks"></a>Note

> [!WARNING]
> Il `SqlStreamChars.Seek` metodo è privato e non deve essere utilizzato direttamente nel codice.
>
> Microsoft non supporta l'uso di questo campo in un'applicazione di produzione in alcuna circostanza.

## <a name="requirements"></a>Requisiti

**Spazio dei nomi:** <xref:System.Data.SqlTypes>

**Assembly:** System. Data (in System)

**Versioni di .NET framework:** Disponibile dalla 2.0.