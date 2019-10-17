---
title: Proprietà SqlStreamChars. IsNull (System. Data. SqlTypes)
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
ms.openlocfilehash: d80f653724b3ef0a1cadb69a5f72b1d9455597d6
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2019
ms.locfileid: "72395739"
---
# <a name="sqlstreamcharsisnull-property"></a>Proprietà SqlStreamChars. IsNull

Sottoposta a override in una classe derivata, ottiene un valore che indica se il flusso è `null`. L'assembly che contiene questa proprietà ha una relazione friend con SQLAccess. dll. È destinato all'uso da SQL Server. Per gli altri database, utilizzare il meccanismo di hosting fornito da tale database.

## <a name="syntax"></a>Sintassi

```csharp
public abstract bool IsNull { get; }
```

## <a name="property-value"></a>Valore proprietà

<xref:System.Boolean>\
`true` se il flusso è `null`; in caso contrario, `false`.

## <a name="remarks"></a>Note

> [!WARNING]
> La proprietà `SqlStreamChars.IsNull` è privata e non può essere utilizzata direttamente nel codice.
>
> Microsoft non supporta l'utilizzo di questa proprietà in un'applicazione di produzione in qualsiasi circostanza.

## <a name="requirements"></a>Requisiti

**Spazio dei nomi:** <xref:System.Data.SqlTypes>

**Assembly:** System. Data (in System. Data. dll)

**Versioni .NET Framework:** Disponibile a partire da 2,0.
