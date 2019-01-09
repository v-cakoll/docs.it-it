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
ms.openlocfilehash: ebcf5c3f13b3bd30a8e091be09ae546eee1eaffe
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/09/2019
ms.locfileid: "54147447"
---
# <a name="servicepointmanagersservicepointtable-field"></a><span data-ttu-id="6139b-102">ServicePointManager.s\_ServicePointTable campo</span><span class="sxs-lookup"><span data-stu-id="6139b-102">ServicePointManager.s\_ServicePointTable Field</span></span>

<span data-ttu-id="6139b-103">`ServicePointManager.s_ServicePointTable` è un <xref:System.Collections.Hashtable> che contiene l'elenco di connessioni HTTP attive (<xref:System.Net.ServicePoint>s) nel <xref:System.AppDomain>.</span><span class="sxs-lookup"><span data-stu-id="6139b-103">`ServicePointManager.s_ServicePointTable` is a <xref:System.Collections.Hashtable> that contains the list of active HTTP connections (<xref:System.Net.ServicePoint>s) in the <xref:System.AppDomain>.</span></span>

## <a name="syntax"></a><span data-ttu-id="6139b-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6139b-104">Syntax</span></span>
  
```csharp  
private static Hashtable s_ServicePointTable
```

> [!WARNING]
> <span data-ttu-id="6139b-105">Il `ServicePointManager.s_ServicePointTable` campo è privato e non deve essere utilizzato direttamente nel codice.</span><span class="sxs-lookup"><span data-stu-id="6139b-105">The `ServicePointManager.s_ServicePointTable` field is private and is not meant to be used directly in your code.</span></span>
> 
> <span data-ttu-id="6139b-106">Microsoft non supporta l'uso di questo campo in un'applicazione di produzione in alcuna circostanza.</span><span class="sxs-lookup"><span data-stu-id="6139b-106">Microsoft does not support the use of this field in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="6139b-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="6139b-107">Requirements</span></span>

<span data-ttu-id="6139b-108">**Spazio dei nomi:** <xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="6139b-108">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="6139b-109">**Assembly:** Sistema (in System. dll)</span><span class="sxs-lookup"><span data-stu-id="6139b-109">**Assembly:** System (in System.dll)</span></span>

<span data-ttu-id="6139b-110">**Versioni di .NET framework:** Disponibile dalla 2.0.</span><span class="sxs-lookup"><span data-stu-id="6139b-110">**.NET Framework versions:** Available since 2.0.</span></span>
