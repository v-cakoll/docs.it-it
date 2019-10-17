---
title: Metodo SqlStreamChars. Seek (Int64, SeekOrigin) (System. Data. SqlTypes)
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
ms.openlocfilehash: db8aba0a86c140ba62af8056011226532d415951
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2019
ms.locfileid: "72395588"
---
# <a name="sqlstreamcharsseekint64-seekorigin-method"></a>Metodo SqlStreamChars. Seek (Int64, SeekOrigin)

Quando ne viene eseguito l'override in una classe derivata, imposta la posizione all'interno del flusso corrente. L'assembly che contiene questo metodo ha una relazione friend con SQLAccess. dll. È destinato all'uso da SQL Server. Per gli altri database, utilizzare il meccanismo di hosting fornito da tale database.

```csharp
public abstract long Seek (long offset, System.IO.SeekOrigin origin);
```

## <a name="parameters"></a>Parametri

`offset`\
Offset di byte relativo a `origin`.

`origin`\
Uno dei valori di enumerazione che indica il punto di riferimento dal quale ottenere la nuova posizione.

## <a name="returns"></a>Valore restituito

<xref:System.Int32>\
Nuova posizione all'interno del flusso corrente.

## <a name="remarks"></a>Note

> [!WARNING]
> Il metodo `SqlStreamChars.Seek` è privato e non è destinato a essere usato direttamente nel codice.
>
> Microsoft non supporta l'utilizzo di questo metodo in un'applicazione di produzione in qualsiasi circostanza.

## <a name="requirements"></a>Requisiti

**Spazio dei nomi:** <xref:System.Data.SqlTypes>

**Assembly:** System. Data (in System. Data. dll)

**Versioni .NET Framework:** Disponibile a partire da 2,0.
