---
title: ServicePointManager.s_ServicePointTable Campo
ms.date: 05/01/2017
topic_type:
- apiref
api_name:
- System.Net.ServicePointManager.s_ServicePointTable
api_location:
- System.dll
api_type:
- Assembly
ms.assetid: 24459679-291c-401a-9def-e42b29466fcf
ms.openlocfilehash: 6a56ecd6fc85005f5987c3c2ad0d1680ca63c398
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79155813"
---
# <a name="servicepointmanagers_servicepointtable-field"></a>ServicePointManager.s\_Campo ServicePointTable

`ServicePointManager.s_ServicePointTable`è <xref:System.Collections.Hashtable> un che contiene l'elenco<xref:System.Net.ServicePoint>delle connessioni <xref:System.AppDomain>HTTP attive ( s) nel file .

## <a name="syntax"></a>Sintassi
  
```csharp  
private static Hashtable s_ServicePointTable
```

> [!WARNING]
> Il `ServicePointManager.s_ServicePointTable` campo è privato e non deve essere utilizzato direttamente nel codice.
>
> Microsoft non supporta in nessun caso l'utilizzo di questo campo in un'applicazione di produzione.

## <a name="requirements"></a>Requisiti

**Spazio dei nomi:**<xref:System.Net>

**Assemblaggio:** Sistema (in System.dll)

Versioni di **.NET Framework:** Disponibile dalla 2.0.
