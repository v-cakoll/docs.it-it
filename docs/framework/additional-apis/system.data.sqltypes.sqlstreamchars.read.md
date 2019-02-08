---
title: Metodo SqlStreamChars.Read (Char [], Int32, Int32) (System.Data.SqlTypes)
author: stevestein
ms.author: sstein
ms.date: 12/20/2018
ms.technology:
- dotnet-data
topic_type:
- apiref
api_name:
- System.Data.SqlTypes.SqlStreamChars.Read
api_location:
- System.Data.dll
api_type:
- Assembly
ms.openlocfilehash: da891ac1fcff0247a690770665ef1f3e487497b8
ms.sourcegitcommit: 3500c4845f96a91a438a02ef2c6b4eef45a5e2af
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/07/2019
ms.locfileid: "55825368"
---
# <a name="sqlstreamcharsreadchar-int32-int32-method"></a>Metodo SqlStreamChars.Read (Char [], Int32, Int32)

Quando sottoposto a override in una classe derivata, legge il successivo set di caratteri dal flusso di input. L'assembly contenente questo metodo ha una relazione di tipo friend SQLAccess. Si tratta per l'uso da SQL Server. Per altri database, usare il meccanismo di hosting fornito da tale database.

```csharp
public abstract int Read (char[] buffer, int offset, int count);
```

## <a name="parameters"></a>Parametri

`buffer`\
Matrice di caratteri da leggere.

`offset`\
Un offset relativo all'origine.

`count`\
Il numero di caratteri da leggere dal flusso corrente.

## <a name="returns"></a>Valore restituito

<xref:System.Int32>\
Numero complessivo di caratteri letti nel buffer.

## <a name="remarks"></a>Note

> [!WARNING]
> Il `SqlStreamChars.Read` metodo è privato e non deve essere utilizzato direttamente nel codice.
>
> Microsoft non supporta l'uso di questo campo in un'applicazione di produzione in alcuna circostanza.

## <a name="requirements"></a>Requisiti

**Spazio dei nomi:** <xref:System.Data.SqlTypes>

**Assembly:** System. Data (in System)

**Versioni di .NET framework:** Disponibile dalla 2.0.