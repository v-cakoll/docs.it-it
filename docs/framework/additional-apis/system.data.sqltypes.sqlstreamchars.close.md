---
title: Metodo SqlStreamChars. Close (System. Data. SqlTypes)
author: stevestein
ms.author: sstein
ms.date: 12/20/2018
ms.technology: dotnet-data
topic_type:
- apiref
api_name:
- System.Data.SqlTypes.SqlStreamChars.Close
api_location:
- System.Data.dll
api_type:
- Assembly
ms.openlocfilehash: c33c60842d181be7011528ca7550f3d09f291f43
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2019
ms.locfileid: "72395627"
---
# <a name="sqlstreamcharsclose-method"></a>Metodo SqlStreamChars. Close

Chiude il flusso corrente e rilascia tutte le risorse di sistema associate al flusso. L'assembly che contiene questo metodo ha una relazione friend con SQLAccess. dll. È destinato all'uso da SQL Server. Per gli altri database, utilizzare il meccanismo di hosting fornito da tale database.

```csharp
public virtual void Close ();
```

## <a name="remarks"></a>Note

> [!WARNING]
> Il metodo `SqlStreamChars.Close` è privato e non è destinato a essere usato direttamente nel codice.
>
> Microsoft non supporta l'utilizzo di questo metodo in un'applicazione di produzione in qualsiasi circostanza.

## <a name="requirements"></a>Requisiti

**Spazio dei nomi:** <xref:System.Data.SqlTypes>

**Assembly:** System. Data (in System. Data. dll)

**Versioni .NET Framework:** Disponibile a partire da 2,0.
