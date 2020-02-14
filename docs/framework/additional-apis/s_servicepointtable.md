---
title: ServicePointManager. s_ServicePointTable campo
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
ms.openlocfilehash: 272a0c113fd70d804c763ba0e7e6e9a4a4ee04ce
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/14/2020
ms.locfileid: "77214914"
---
# <a name="servicepointmanagers_servicepointtable-field"></a><span data-ttu-id="2c306-102">Campo ServicePointTable di ServicePointManager. s\_</span><span class="sxs-lookup"><span data-stu-id="2c306-102">ServicePointManager.s\_ServicePointTable Field</span></span>

<span data-ttu-id="2c306-103">`ServicePointManager.s_ServicePointTable` è un <xref:System.Collections.Hashtable> che contiene l'elenco di connessioni HTTP attive (<xref:System.Net.ServicePoint>s) nell'<xref:System.AppDomain>.</span><span class="sxs-lookup"><span data-stu-id="2c306-103">`ServicePointManager.s_ServicePointTable` is a <xref:System.Collections.Hashtable> that contains the list of active HTTP connections (<xref:System.Net.ServicePoint>s) in the <xref:System.AppDomain>.</span></span>

## <a name="syntax"></a><span data-ttu-id="2c306-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2c306-104">Syntax</span></span>
  
```csharp  
private static Hashtable s_ServicePointTable
```

> [!WARNING]
> <span data-ttu-id="2c306-105">Il campo `ServicePointManager.s_ServicePointTable` è privato e non è destinato a essere usato direttamente nel codice.</span><span class="sxs-lookup"><span data-stu-id="2c306-105">The `ServicePointManager.s_ServicePointTable` field is private and is not meant to be used directly in your code.</span></span>
> 
> <span data-ttu-id="2c306-106">Microsoft non supporta l'utilizzo di questo campo in un'applicazione di produzione in qualsiasi circostanza.</span><span class="sxs-lookup"><span data-stu-id="2c306-106">Microsoft does not support the use of this field in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="2c306-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="2c306-107">Requirements</span></span>

<span data-ttu-id="2c306-108">**Spazio dei nomi:** <xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="2c306-108">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="2c306-109">**Assembly:** System (in System. dll)</span><span class="sxs-lookup"><span data-stu-id="2c306-109">**Assembly:** System (in System.dll)</span></span>

<span data-ttu-id="2c306-110">**Versioni .NET Framework:** Disponibile a partire da 2,0.</span><span class="sxs-lookup"><span data-stu-id="2c306-110">**.NET Framework versions:** Available since 2.0.</span></span>
