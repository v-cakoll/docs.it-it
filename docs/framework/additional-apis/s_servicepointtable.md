---
title: Campo ServicePointManager.s_ServicePointTable
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
author: rpetrusha
ms.author: mairaw
ms.openlocfilehash: 840d068d282e3ba35df5aee6a11ff96d9e6bfdbd
ms.sourcegitcommit: 621a5f6df00152006160987395b93b5b55f7ffcd
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/29/2019
ms.locfileid: "66301382"
---
# <a name="servicepointmanagersservicepointtable-field"></a>ServicePointManager.s\_ServicePointTable campo

`ServicePointManager.s_ServicePointTable` è un <xref:System.Collections.Hashtable> che contiene l'elenco di connessioni HTTP attive (<xref:System.Net.ServicePoint>s) nel <xref:System.AppDomain>.

## <a name="syntax"></a>Sintassi
  
```csharp  
private static Hashtable s_ServicePointTable
```

> [!WARNING]
> Il `ServicePointManager.s_ServicePointTable` campo è privato e non deve essere utilizzato direttamente nel codice.
> 
> Microsoft non supporta l'uso di questo campo in un'applicazione di produzione in alcuna circostanza.

## <a name="requirements"></a>Requisiti

**Spazio dei nomi:** <xref:System.Net>

**Assembly:** Sistema (in System. dll)

**Versioni di .NET framework:** Disponibile dalla 2.0.
