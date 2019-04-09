---
title: Initialize (funzione) (riferimenti alle API non gestite)
description: La funzione di inizializzazione esegue l'inizializzazione di WMI.
ms.date: 11/06/2017
api_name:
- Initialize
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- Initialize
helpviewer_keywords:
- Initialize function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ca8e87157a7adf45f35608aeba1067f2d66c8972
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59081606"
---
# <a name="initialize-function"></a><span data-ttu-id="9e7d9-103">Initialize (funzione)</span><span class="sxs-lookup"><span data-stu-id="9e7d9-103">Initialize function</span></span>
<span data-ttu-id="9e7d9-104">Esegue l'inizializzazione di WMI.</span><span class="sxs-lookup"><span data-stu-id="9e7d9-104">Performs WMI initialization.</span></span>  
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="9e7d9-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9e7d9-105">Syntax</span></span> 
```  
HRESULT Initialize(
   [in] boolean bAllowIManagementObjectQI
); 
```  
## <a name="parameters"></a><span data-ttu-id="9e7d9-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="9e7d9-106">Parameters</span></span>

`bAllowIManagementObjectQI`   
<span data-ttu-id="9e7d9-107">[in] `true` per indicare che sono consentite le chiamate a QueryInterface sugli oggetti WMI. `false` in caso contrario.</span><span class="sxs-lookup"><span data-stu-id="9e7d9-107">[in] `true` to indicate that calls to QueryInterface on WMI objects are allowed; `false` otherwise.</span></span>

## <a name="return-value"></a><span data-ttu-id="9e7d9-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="9e7d9-108">Return value</span></span>

<span data-ttu-id="9e7d9-109">La funzione restituisce sempre `S_OK` (0).</span><span class="sxs-lookup"><span data-stu-id="9e7d9-109">The function always returns `S_OK` (0).</span></span>
  
## <a name="requirements"></a><span data-ttu-id="9e7d9-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="9e7d9-110">Requirements</span></span>  
 <span data-ttu-id="9e7d9-111">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9e7d9-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9e7d9-112">**Intestazione:** WMINet_Utils.def</span><span class="sxs-lookup"><span data-stu-id="9e7d9-112">**Header:** WMINet_Utils.def</span></span>  
  
 **<span data-ttu-id="9e7d9-113">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="9e7d9-113">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a><span data-ttu-id="9e7d9-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9e7d9-114">See also</span></span>

- [<span data-ttu-id="9e7d9-115">WMI e contatori delle prestazioni (riferimenti alle API non gestite)</span><span class="sxs-lookup"><span data-stu-id="9e7d9-115">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
