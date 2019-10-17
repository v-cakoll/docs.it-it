---
title: Metodo SqlStreamChars. Dispose (Boolean) (System. Data. SqlTypes)
author: stevestein
ms.author: sstein
ms.date: 12/20/2018
ms.technology: dotnet-data
topic_type:
- apiref
api_name:
- System.Data.SqlTypes.SqlStreamChars.Dispose
api_location:
- System.Data.dll
api_type:
- Assembly
ms.openlocfilehash: 44dc97835b8a7141064e8de4d2d5325c40be5a34
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2019
ms.locfileid: "72395758"
---
# <a name="sqlstreamcharsdisposeboolean-method"></a>Metodo SqlStreamChars. Dispose (Boolean)

Quando sottoposto a override in una classe derivata, rilascia le risorse usate dal flusso. L'assembly che contiene questo metodo ha una relazione friend con SQLAccess. dll. È destinato all'uso da SQL Server. Per gli altri database, utilizzare il meccanismo di hosting fornito da tale database.

```csharp
protected virtual void Dispose (bool disposing);
```

## <a name="parameters"></a>Parametri

`disposing`\
`true` per rilasciare sia le risorse gestite sia quelle non gestite; `false` per rilasciare solo le risorse non gestite.

## <a name="remarks"></a>Note

> [!WARNING]
> Il metodo `SqlStreamChars.Dispose` è privato e non è destinato a essere usato direttamente nel codice.
>
> Microsoft non supporta l'utilizzo di questo metodo in un'applicazione di produzione in qualsiasi circostanza.

## <a name="requirements"></a>Requisiti

**Spazio dei nomi:** <xref:System.Data.SqlTypes>

**Assembly:** System. Data (in System. Data. dll)

**Versioni .NET Framework:** Disponibile a partire da 2,0.
