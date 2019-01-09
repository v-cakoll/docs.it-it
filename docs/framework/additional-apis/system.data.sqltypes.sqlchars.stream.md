---
title: Proprietà SqlChars.Stream (System.Data.SqlTypes)
author: douglaslMS
ms.author: douglasl
ms.date: 12/19/2018
ms.technology:
- dotnet-data
api_name:
- System.Data.SqlTypes.SqlChars.Stream
- System.Data.SqlTypes.SqlChars.get_Stream
- System.Data.SqlTypes.SqlChars.set_Stream
api_location:
- System.Data.dll
api_type:
- Assembly
ms.openlocfilehash: f8b6f4f3a92f1d78e434263c6a7897641867c412
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/09/2019
ms.locfileid: "54152604"
---
# <a name="sqlcharsstream-property"></a>Proprietà SqlChars.Stream

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