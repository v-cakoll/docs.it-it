---
title: Proprietà SqlStreamChars.IsNull (System.Data.SqlTypes)
author: stevestein
ms.author: sstein
ms.date: 12/19/2018
ms.technology: dotnet-data
topic_type:
- apiref
api_name:
- System.Data.SqlTypes.SqlStreamChars.IsNull
- System.Data.SqlTypes.SqlStreamChars.get_IsNull
api_location:
- System.Data.dll
api_type:
- Assembly
ms.openlocfilehash: ec00b0afa1597c3ae6488c12fe5a0667dad70e2d
ms.sourcegitcommit: d938c39afb9216db377d0f0ecdaa53936a851059
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/29/2019
ms.locfileid: "58634336"
---
# <a name="sqlstreamcharsisnull-property"></a>Proprietà SqlStreamChars.IsNull

Quando sottoposto a override in una classe derivata, ottiene un valore che indica se il flusso è `null`. L'assembly che contiene questa proprietà ha una relazione di tipo friend SQLAccess. Si tratta per l'uso da SQL Server. Per altri database, usare il meccanismo di hosting fornito da tale database.

## <a name="syntax"></a>Sintassi

```csharp
public abstract bool IsNull { get; }
```

## <a name="property-value"></a>Valore della proprietà

<xref:System.Boolean>\
`true` Se il flusso `null`; in caso contrario, `false`.

## <a name="remarks"></a>Note

> [!WARNING]
> Il `SqlStreamChars.IsNull` proprietà è privato e non deve essere utilizzato direttamente nel codice.
>
> Microsoft non supporta l'uso di questo campo in un'applicazione di produzione in alcuna circostanza.

## <a name="requirements"></a>Requisiti

**Spazio dei nomi:** <xref:System.Data.SqlTypes>

**Assembly:** System. Data (in System)

**Versioni di .NET framework:** Disponibile dalla 2.0.