---
title: Campo ServicePointManager.s_ServicePointTable
ms.date: 05/01/2017
ms.prod: .net-framework
ms.technology: 
ms.topic: reference
topic_type: apiref
api_name: System.Net.ServicePointManager.s_ServicePointTable
api_location: System.dll
api_type: Assembly
ms.assetid: 24459679-291c-401a-9def-e42b29466fcf
author: guardrex
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 8dfdbab78d8efab13487575218820f8b0455248d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="servicepointmanagersservicepointtable-field"></a>ServicePointManager.s\_ServicePointTable campo

`ServicePointManager.s_ServicePointTable`è un <xref:System.Collections.Hashtable> che contiene l'elenco di connessioni HTTP attive (<xref:System.Net.ServicePoint>s) nei <xref:System.AppDomain>.

## <a name="syntax"></a>Sintassi
  
```csharp  
private static Hashtable s_ServicePointTable
```

> [!WARNING]
> Il `ServicePointManager.s_ServicePointTable` campo è privato e non ha significato essere utilizzato direttamente nel codice.
> 
> Microsoft non supporta l'utilizzo di questo campo in un'applicazione di produzione in qualsiasi circostanza.

## <a name="requirements"></a>Requisiti

**Namespace:**<xref:System.Net>

**Assembly:** System (System. dll)

**Versioni di .NET framework:** disponibile dalla 2.0.
