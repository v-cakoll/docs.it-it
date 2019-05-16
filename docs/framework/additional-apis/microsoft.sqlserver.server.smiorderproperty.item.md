---
title: Proprietà SmiOrderProperty.Item (SqlServer)
author: stevestein
ms.author: sstein
ms.date: 12/20/2018
ms.technology: dotnet-data
topic_type:
- apiref
api_name:
- Microsoft.SqlServer.Server.SmiOrderProperty.Item
- Microsoft.SqlServer.Server.SmiOrderProperty.get_Item
api_location:
- System.Data.dll
api_type:
- Assembly
ms.openlocfilehash: e2d8788f610d80c30baf51bff0131f0834d59fcd
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2019
ms.locfileid: "65634581"
---
# <a name="smiorderpropertyitem-property"></a>Proprietà SmiOrderProperty.Item

Ottiene l'ordine delle colonne per l'entità. L'assembly che contiene questa proprietà ha una relazione di tipo friend SQLAccess. Si tratta per l'uso da SQL Server. Per altri database, usare il meccanismo di hosting fornito da tale database.

## <a name="syntax"></a>Sintassi

```csharp
internal SmiColumnOrder Item { get; }
```

## <a name="property-value"></a>Valore della proprietà

L'ordine delle colonne.

## <a name="remarks"></a>Note

> [!WARNING]
> Il `SmiOrderProperty.Item` proprietà sono interna e non deve essere utilizzato direttamente nel codice.
>
> Microsoft non supporta l'uso di questa proprietà in un'applicazione di produzione in alcuna circostanza.

## <a name="requirements"></a>Requisiti

**Spazio dei nomi:** <xref:Microsoft.SqlServer.Server>

**Assembly:** System. Data (in System)

**Versioni di .NET framework:** Disponibile dalla 2.0.
