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
# <a name="servicepointmanagers_servicepointtable-field"></a><span data-ttu-id="9581e-102">ServicePointManager.s\_Campo ServicePointTable</span><span class="sxs-lookup"><span data-stu-id="9581e-102">ServicePointManager.s\_ServicePointTable Field</span></span>

<span data-ttu-id="9581e-103">`ServicePointManager.s_ServicePointTable`è <xref:System.Collections.Hashtable> un che contiene l'elenco<xref:System.Net.ServicePoint>delle connessioni <xref:System.AppDomain>HTTP attive ( s) nel file .</span><span class="sxs-lookup"><span data-stu-id="9581e-103">`ServicePointManager.s_ServicePointTable` is a <xref:System.Collections.Hashtable> that contains the list of active HTTP connections (<xref:System.Net.ServicePoint>s) in the <xref:System.AppDomain>.</span></span>

## <a name="syntax"></a><span data-ttu-id="9581e-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9581e-104">Syntax</span></span>
  
```csharp  
private static Hashtable s_ServicePointTable
```

> [!WARNING]
> <span data-ttu-id="9581e-105">Il `ServicePointManager.s_ServicePointTable` campo è privato e non deve essere utilizzato direttamente nel codice.</span><span class="sxs-lookup"><span data-stu-id="9581e-105">The `ServicePointManager.s_ServicePointTable` field is private and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="9581e-106">Microsoft non supporta in nessun caso l'utilizzo di questo campo in un'applicazione di produzione.</span><span class="sxs-lookup"><span data-stu-id="9581e-106">Microsoft does not support the use of this field in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="9581e-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="9581e-107">Requirements</span></span>

<span data-ttu-id="9581e-108">**Spazio dei nomi:**<xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="9581e-108">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="9581e-109">**Assemblaggio:** Sistema (in System.dll)</span><span class="sxs-lookup"><span data-stu-id="9581e-109">**Assembly:** System (in System.dll)</span></span>

<span data-ttu-id="9581e-110">Versioni di **.NET Framework:** Disponibile dalla 2.0.</span><span class="sxs-lookup"><span data-stu-id="9581e-110">**.NET Framework versions:** Available since 2.0.</span></span>
