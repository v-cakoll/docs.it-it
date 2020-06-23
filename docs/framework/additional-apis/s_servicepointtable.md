---
title: ServicePointManager. s_ServicePointTable campo
description: Leggere le informazioni sul campo ServicePointManager. s_ServicePointTable in .NET. Questo campo della tabella hash contiene le connessioni HTTP attive (ServicePoints) in AppDomain.
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
ms.openlocfilehash: 9462ae10125dd37706f786a1f2cef78e62fbabcc
ms.sourcegitcommit: 45c8eed045779b70a47b23169897459d0323dc89
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/18/2020
ms.locfileid: "84989537"
---
# <a name="servicepointmanagers_servicepointtable-field"></a><span data-ttu-id="6b97c-104">Campo ServicePointTable di ServicePointManager. s \_</span><span class="sxs-lookup"><span data-stu-id="6b97c-104">ServicePointManager.s\_ServicePointTable Field</span></span>

<span data-ttu-id="6b97c-105">`ServicePointManager.s_ServicePointTable`è un oggetto <xref:System.Collections.Hashtable> che contiene l'elenco di connessioni HTTP attive <xref:System.Net.ServicePoint> nell'oggetto <xref:System.AppDomain> .</span><span class="sxs-lookup"><span data-stu-id="6b97c-105">`ServicePointManager.s_ServicePointTable` is a <xref:System.Collections.Hashtable> that contains the list of active HTTP connections (<xref:System.Net.ServicePoint>s) in the <xref:System.AppDomain>.</span></span>

## <a name="syntax"></a><span data-ttu-id="6b97c-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6b97c-106">Syntax</span></span>
  
```csharp  
private static Hashtable s_ServicePointTable
```

> [!WARNING]
> <span data-ttu-id="6b97c-107">Il `ServicePointManager.s_ServicePointTable` campo è privato e non è destinato a essere usato direttamente nel codice.</span><span class="sxs-lookup"><span data-stu-id="6b97c-107">The `ServicePointManager.s_ServicePointTable` field is private and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="6b97c-108">Microsoft non supporta l'utilizzo di questo campo in un'applicazione di produzione in qualsiasi circostanza.</span><span class="sxs-lookup"><span data-stu-id="6b97c-108">Microsoft does not support the use of this field in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="6b97c-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="6b97c-109">Requirements</span></span>

<span data-ttu-id="6b97c-110">**Spazio dei nomi:** <xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="6b97c-110">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="6b97c-111">**Assembly:** Sistema (in System.dll)</span><span class="sxs-lookup"><span data-stu-id="6b97c-111">**Assembly:** System (in System.dll)</span></span>

<span data-ttu-id="6b97c-112">**Versioni .NET Framework:** Disponibile a partire da 2,0.</span><span class="sxs-lookup"><span data-stu-id="6b97c-112">**.NET Framework versions:** Available since 2.0.</span></span>
