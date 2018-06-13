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
author: guardrex
ms.author: mairaw
ms.openlocfilehash: 5450a0cb3e5bd39a86365b16d372c7e573a43496
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33351758"
---
# <a name="servicepointmanagersservicepointtable-field"></a>ServicePointManager.s\_ServicePointTable campo

`ServicePointManager.s_ServicePointTable` è un <xref:System.Collections.Hashtable> che contiene l'elenco delle connessioni HTTP attive (<xref:System.Net.ServicePoint>s) nei <xref:System.AppDomain>.

## <a name="syntax"></a>Sintassi
  
```csharp  
private static Hashtable s_ServicePointTable
```

> [!WARNING]
> Il `ServicePointManager.s_ServicePointTable` campo è privato e non ha significato essere utilizzato direttamente nel codice.
> 
> Microsoft non supporta l'utilizzo di questo campo in un'applicazione di produzione in qualsiasi circostanza.

## <a name="requirements"></a>Requisiti

**Namespace:** <xref:System.Net>

**Assembly:** System (System. dll)

**Versioni di .NET framework:** disponibile dalla 2.0.
