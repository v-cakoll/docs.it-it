---
title: Proprietà SqlStreamChars. length (System. Data. SqlTypes)
author: stevestein
ms.author: sstein
ms.date: 12/19/2018
ms.technology: dotnet-data
topic_type:
- apiref
api_name:
- System.Data.SqlTypes.SqlStreamChars.Length
- System.Data.SqlTypes.SqlStreamChars.get_Length
api_location:
- System.Data.dll
api_type:
- Assembly
ms.openlocfilehash: 2171b10d1c0eb7bcad894cc44c5103bdab18b0a5
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2019
ms.locfileid: "72395613"
---
# <a name="sqlstreamcharslength-property"></a>Proprietà SqlStreamChars. length

Quando sottoposto a override in una classe derivata, ottiene la lunghezza del flusso corrente. L'assembly che contiene questa proprietà ha una relazione friend con SQLAccess. dll. È destinato all'uso da SQL Server. Per gli altri database, utilizzare il meccanismo di hosting fornito da tale database.

## <a name="syntax"></a>Sintassi

```csharp
public abstract long Length { get; }
```

## <a name="property-value"></a>Valore proprietà

<xref:System.Int64>\
Lunghezza del flusso.

## <a name="remarks"></a>Note

> [!WARNING]
> La proprietà `SqlStreamChars.Length` è privata e non può essere utilizzata direttamente nel codice.
>
> Microsoft non supporta l'utilizzo di questa proprietà in un'applicazione di produzione in qualsiasi circostanza.

## <a name="requirements"></a>Requisiti

**Spazio dei nomi:** <xref:System.Data.SqlTypes>

**Assembly:** System. Data (in System. Data. dll)

**Versioni .NET Framework:** Disponibile a partire da 2,0.
