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
# <a name="servicepointmanagersservicepointtable-field"></a><span data-ttu-id="7b21e-102">ServicePointManager.s\_ServicePointTable campo</span><span class="sxs-lookup"><span data-stu-id="7b21e-102">ServicePointManager.s\_ServicePointTable Field</span></span>

<span data-ttu-id="7b21e-103">`ServicePointManager.s_ServicePointTable` è un <xref:System.Collections.Hashtable> che contiene l'elenco delle connessioni HTTP attive (<xref:System.Net.ServicePoint>s) nei <xref:System.AppDomain>.</span><span class="sxs-lookup"><span data-stu-id="7b21e-103">`ServicePointManager.s_ServicePointTable` is a <xref:System.Collections.Hashtable> that contains the list of active HTTP connections (<xref:System.Net.ServicePoint>s) in the <xref:System.AppDomain>.</span></span>

## <a name="syntax"></a><span data-ttu-id="7b21e-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7b21e-104">Syntax</span></span>
  
```csharp  
private static Hashtable s_ServicePointTable
```

> [!WARNING]
> <span data-ttu-id="7b21e-105">Il `ServicePointManager.s_ServicePointTable` campo è privato e non ha significato essere utilizzato direttamente nel codice.</span><span class="sxs-lookup"><span data-stu-id="7b21e-105">The `ServicePointManager.s_ServicePointTable` field is private and not meant to be used directly in your code.</span></span>
> 
> <span data-ttu-id="7b21e-106">Microsoft non supporta l'utilizzo di questo campo in un'applicazione di produzione in qualsiasi circostanza.</span><span class="sxs-lookup"><span data-stu-id="7b21e-106">Microsoft does not support the use of this field in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="7b21e-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="7b21e-107">Requirements</span></span>

<span data-ttu-id="7b21e-108">**Namespace:** <xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="7b21e-108">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="7b21e-109">**Assembly:** System (System. dll)</span><span class="sxs-lookup"><span data-stu-id="7b21e-109">**Assembly:** System (in System.dll)</span></span>

<span data-ttu-id="7b21e-110">**Versioni di .NET framework:** disponibile dalla 2.0.</span><span class="sxs-lookup"><span data-stu-id="7b21e-110">**.NET Framework versions:** Available since 2.0.</span></span>
