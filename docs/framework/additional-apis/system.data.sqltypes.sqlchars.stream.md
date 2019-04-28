---
title: Proprietà SqlChars.Stream (System.Data.SqlTypes)
author: stevestein
ms.author: sstein
ms.date: 12/19/2018
ms.technology: dotnet-data
topic_type:
- apiref
api_name:
- System.Data.SqlTypes.SqlChars.Stream
- System.Data.SqlTypes.SqlChars.get_Stream
- System.Data.SqlTypes.SqlChars.set_Stream
api_location:
- System.Data.dll
api_type:
- Assembly
ms.openlocfilehash: 4858d9f8878e5b56a0811edf92a2faa729775156
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61675201"
---
# <a name="sqlcharsstream-property"></a>SqlChars.Stream Property

Ottiene o imposta il flusso di caratteri. L'assembly che contiene questa proprietà ha una relazione di tipo friend SQLAccess. Si tratta per l'uso da SQL Server. Per altri database, usare il meccanismo di hosting fornito da tale database.

```csharp
internal SqlStreamChars Stream { get; set; }
```

## <a name="property-value"></a>Valore della proprietà

`System.Data.SqlTypes.SqlStreamChars`\
Il flusso di caratteri.

## <a name="remarks"></a>Note

> [!WARNING]
> Il `SqlChars.Stream` proprietà sono interna e non deve essere utilizzato direttamente nel codice.
>
> Microsoft non supporta l'uso di questa proprietà in un'applicazione di produzione in alcuna circostanza.

## <a name="requirements"></a>Requisiti

**Spazio dei nomi:** <xref:System.Data.SqlTypes>

**Assembly:** System. Data (in System)

**Versioni di .NET framework:** Disponibile dalla 2.0.