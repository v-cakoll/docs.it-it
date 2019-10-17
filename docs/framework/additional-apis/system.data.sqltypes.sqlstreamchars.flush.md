---
title: Metodo SqlStreamChars. Flush (System. Data. SqlTypes)
author: stevestein
ms.author: sstein
ms.date: 12/20/2018
ms.technology: dotnet-data
topic_type:
- apiref
api_name:
- System.Data.SqlTypes.SqlStreamChars.Flush
api_location:
- System.Data.dll
api_type:
- Assembly
ms.openlocfilehash: 38ade5ce38cfe5003b2d06c0d8bb2db1a20bc05b
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2019
ms.locfileid: "72395621"
---
# <a name="sqlstreamcharsflush-method"></a>Metodo SqlStreamChars. Flush

Quando ne viene eseguito l'override in una classe derivata, cancella tutti i buffer del flusso e determina la scrittura dei dati memorizzati nel buffer nel dispositivo sottostante. L'assembly che contiene questo metodo ha una relazione friend con SQLAccess. dll. È destinato all'uso da SQL Server. Per gli altri database, utilizzare il meccanismo di hosting fornito da tale database.

## <a name="syntax"></a>Sintassi

```csharp
public abstract void Flush ();
```

## <a name="remarks"></a>Note

> [!WARNING]
> Il metodo `SqlStreamChars.Flush` è privato e non è destinato a essere usato direttamente nel codice.
>
> Microsoft non supporta l'utilizzo di questo metodo in un'applicazione di produzione in qualsiasi circostanza.

## <a name="requirements"></a>Requisiti

**Spazio dei nomi:** <xref:System.Data.SqlTypes>

**Assembly:** System. Data (in System. Data. dll)

**Versioni .NET Framework:** Disponibile a partire da 2,0.
