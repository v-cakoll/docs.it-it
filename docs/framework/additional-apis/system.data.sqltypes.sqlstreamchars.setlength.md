---
title: Metodo SqlStreamChars. selength (Int64) (System. Data. SqlTypes)
author: stevestein
ms.author: sstein
ms.date: 12/20/2018
ms.technology: dotnet-data
topic_type:
- apiref
api_name:
- System.Data.SqlTypes.SqlStreamChars.SetLength
api_location:
- System.Data.dll
api_type:
- Assembly
ms.openlocfilehash: 291d6e9395581f2370dafc728521a314d54a686d
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2019
ms.locfileid: "72395729"
---
# <a name="sqlstreamcharssetlengthint64-method"></a>Metodo SqlStreamChars. selength (Int64)

Quando sottoposto a override in una classe derivata, rilascia le risorse usate dal flusso. L'assembly che contiene questo metodo ha una relazione friend con SQLAccess. dll. È destinato all'uso da SQL Server. Per gli altri database, utilizzare il meccanismo di hosting fornito da tale database.

```csharp
public abstract void SetLength (long value);
```

## <a name="parameters"></a>Parametri

`value`\
Lunghezza desiderata del flusso corrente in byte.

## <a name="remarks"></a>Note

> [!WARNING]
> Il metodo `SqlStreamChars.SetLength` è privato e non è destinato a essere usato direttamente nel codice.
>
> Microsoft non supporta l'utilizzo di questo metodo in un'applicazione di produzione in qualsiasi circostanza.

## <a name="requirements"></a>Requisiti

**Spazio dei nomi:** <xref:System.Data.SqlTypes>

**Assembly:** System. Data (in System. Data. dll)

**Versioni .NET Framework:** Disponibile a partire da 2,0.
