---
title: Initialize (funzione) (riferimenti alle API non gestite)
description: La funzione di inizializzazione esegue l'inizializzazione di WMI.
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: reference
api_name: Initialize
api_location: WMINet_Utils.dll
api_type: DLLExport
f1_keywords: Initialize
helpviewer_keywords: Initialize function [.NET WMI and performance counters]
topic_type: Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d62d959c5dfeac237abb20b86df87ae07a077dbd
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="initialize-function"></a><span data-ttu-id="f610c-103">Initialize (funzione)</span><span class="sxs-lookup"><span data-stu-id="f610c-103">Initialize function</span></span>
<span data-ttu-id="f610c-104">Esegue l'inizializzazione di WMI.</span><span class="sxs-lookup"><span data-stu-id="f610c-104">Performs WMI initialization.</span></span>  
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="f610c-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f610c-105">Syntax</span></span> 
```  
HRESULT Initialize(
   [in] boolean bAllowIManagementObjectQI
); 
```  
## <a name="parameters"></a><span data-ttu-id="f610c-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="f610c-106">Parameters</span></span>

`bAllowIManagementObjectQI`   
<span data-ttu-id="f610c-107">[in] `true` per indicare che sono consentite chiamate a QueryInterface su oggetti WMI; `false` in caso contrario.</span><span class="sxs-lookup"><span data-stu-id="f610c-107">[in] `true` to indicate that calls to QueryInterface on WMI objects are allowed; `false` otherwise.</span></span>

## <a name="return-value"></a><span data-ttu-id="f610c-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="f610c-108">Return value</span></span>

<span data-ttu-id="f610c-109">La funzione restituisce sempre `S_OK` (0).</span><span class="sxs-lookup"><span data-stu-id="f610c-109">The function always returns `S_OK` (0).</span></span>
  
## <a name="requirements"></a><span data-ttu-id="f610c-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f610c-110">Requirements</span></span>  
 <span data-ttu-id="f610c-111">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f610c-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f610c-112">**Intestazione:** WMINet_Utils.def</span><span class="sxs-lookup"><span data-stu-id="f610c-112">**Header:** WMINet_Utils.def</span></span>  
  
 <span data-ttu-id="f610c-113">**Versioni di .NET framework:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="f610c-113">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f610c-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f610c-114">See also</span></span>  
[<span data-ttu-id="f610c-115">WMI e i contatori delle prestazioni (riferimenti alle API non gestite)</span><span class="sxs-lookup"><span data-stu-id="f610c-115">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
