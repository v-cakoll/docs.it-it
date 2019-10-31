---
title: ServicePointManager. s_ServicePointTable, campo
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 68445f4a290b9f4fe2696e35cda391b6c0ee8f85
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73120006"
---
# <a name="servicepointmanagers_servicepointtable-field"></a><span data-ttu-id="afe7e-102">Campo ServicePointTable di ServicePointManager. s\_</span><span class="sxs-lookup"><span data-stu-id="afe7e-102">ServicePointManager.s\_ServicePointTable Field</span></span>

<span data-ttu-id="afe7e-103">`ServicePointManager.s_ServicePointTable` è un <xref:System.Collections.Hashtable> che contiene l'elenco di connessioni HTTP attive (<xref:System.Net.ServicePoint>s) nell'<xref:System.AppDomain>.</span><span class="sxs-lookup"><span data-stu-id="afe7e-103">`ServicePointManager.s_ServicePointTable` is a <xref:System.Collections.Hashtable> that contains the list of active HTTP connections (<xref:System.Net.ServicePoint>s) in the <xref:System.AppDomain>.</span></span>

## <a name="syntax"></a><span data-ttu-id="afe7e-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="afe7e-104">Syntax</span></span>
  
```csharp  
private static Hashtable s_ServicePointTable
```

> [!WARNING]
> <span data-ttu-id="afe7e-105">Il campo `ServicePointManager.s_ServicePointTable` è privato e non è destinato a essere usato direttamente nel codice.</span><span class="sxs-lookup"><span data-stu-id="afe7e-105">The `ServicePointManager.s_ServicePointTable` field is private and is not meant to be used directly in your code.</span></span>
> 
> <span data-ttu-id="afe7e-106">Microsoft non supporta l'utilizzo di questo campo in un'applicazione di produzione in qualsiasi circostanza.</span><span class="sxs-lookup"><span data-stu-id="afe7e-106">Microsoft does not support the use of this field in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="afe7e-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="afe7e-107">Requirements</span></span>

<span data-ttu-id="afe7e-108">**Spazio dei nomi:** <xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="afe7e-108">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="afe7e-109">**Assembly:** System (in System. dll)</span><span class="sxs-lookup"><span data-stu-id="afe7e-109">**Assembly:** System (in System.dll)</span></span>

<span data-ttu-id="afe7e-110">**Versioni .NET Framework:** Disponibile a partire da 2,0.</span><span class="sxs-lookup"><span data-stu-id="afe7e-110">**.NET Framework versions:** Available since 2.0.</span></span>
