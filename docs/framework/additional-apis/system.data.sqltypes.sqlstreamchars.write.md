---
title: Metodo SqlStreamChars.Write (Char [], Int32, Int32) (System.Data.SqlTypes)
author: stevestein
ms.author: sstein
ms.date: 12/20/2018
ms.technology: dotnet-data
topic_type:
- apiref
api_name:
- System.Data.SqlTypes.SqlStreamChars.Write
api_location:
- System.Data.dll
api_type:
- Assembly
ms.openlocfilehash: 4084c7161eaa91d78eab32f1c14624e0032cdfcf
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61705909"
---
# <a name="sqlstreamcharswritechar-int32-int32-method"></a>Metodo SqlStreamChars.Write (Char [], Int32, Int32)

Quando sottoposto a override in una classe derivata, scrive una sequenza di caratteri nel flusso corrente e fa avanzare la posizione corrente all'interno di questo flusso del numero di caratteri scritti. L'assembly contenente questo metodo ha una relazione di tipo friend SQLAccess. Si tratta per l'uso da SQL Server. Per altri database, usare il meccanismo di hosting fornito da tale database.

```csharp
public abstract void Write (char[] buffer, int offset, int count);
```

## <a name="parameters"></a>Parametri

`buffer`  
Matrice di caratteri da scrivere.

`offset`  
Un offset relativo all'origine.

`count`  
Il numero di caratteri da scrivere nel flusso corrente.

## <a name="remarks"></a>Note

> [!WARNING]
> Il `SqlStreamChars.Write` metodo è privato e non deve essere utilizzato direttamente nel codice.
>
> Microsoft non supporta l'uso di questo campo in un'applicazione di produzione in alcuna circostanza.

## <a name="requirements"></a>Requisiti

**Spazio dei nomi:** <xref:System.Data.SqlTypes>

**Assembly:** System. Data (in System)

**Versioni di .NET framework:** Disponibile dalla 2.0.
