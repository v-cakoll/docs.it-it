---
title: Proprietà SmiOrderProperty.Item (SqlServer)
author: stevestein
ms.author: sstein
ms.date: 12/20/2018
ms.technology:
- dotnet-data
topic_type:
- apiref
api_name:
- Microsoft.SqlServer.Server.SmiOrderProperty.Item
- Microsoft.SqlServer.Server.SmiOrderProperty.get_Item
api_location:
- System.Data.dll
api_type:
- Assembly
ms.openlocfilehash: cb2f6cb956f9571f9bd2ba7f86d79c5df6e72a15
ms.sourcegitcommit: 3500c4845f96a91a438a02ef2c6b4eef45a5e2af
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/07/2019
ms.locfileid: "55827734"
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