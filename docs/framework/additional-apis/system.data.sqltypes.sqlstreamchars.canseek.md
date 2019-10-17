---
title: Proprietà SqlStreamChars. CanSeek (System. Data. SqlTypes)
author: stevestein
ms.author: sstein
ms.date: 12/19/2018
ms.technology: dotnet-data
topic_type:
- apiref
api_name:
- System.Data.SqlTypes.SqlStreamChars.CanSeek
- System.Data.SqlTypes.SqlStreamChars.get_CanSeek
api_location:
- System.Data.dll
api_type:
- Assembly
ms.openlocfilehash: eb32978f62b7d46f0abf715e2bca347592c0fda8
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2019
ms.locfileid: "72395770"
---
# <a name="sqlstreamcharscanseek-property"></a>Proprietà SqlStreamChars. CanSeek

Sottoposta a override in una classe derivata, ottiene un valore che indica se il vapore corrente supporta l'operazione di ricerca. L'assembly che contiene questa proprietà ha una relazione friend con SQLAccess. dll. È destinato all'uso da SQL Server. Per gli altri database, utilizzare il meccanismo di hosting fornito da tale database.

```csharp
public abstract bool CanSeek { get; }
```

## <a name="property-value"></a>Valore proprietà

<xref:System.Boolean>\
`true` se il vapore corrente supporta l'operazione di ricerca; in caso contrario, `false`.

## <a name="remarks"></a>Note

> [!WARNING]
> La proprietà `SqlStreamChars.CanSeek` è privata e non può essere utilizzata direttamente nel codice.
>
> Microsoft non supporta l'utilizzo di questa proprietà in un'applicazione di produzione in qualsiasi circostanza.

## <a name="requirements"></a>Requisiti

**Spazio dei nomi:** <xref:System.Data.SqlTypes>

**Assembly:** System. Data (in System. Data. dll)

**Versioni .NET Framework:** Disponibile a partire da 2,0.
