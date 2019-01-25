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
ms.openlocfilehash: f56ce2da5cc1b79fded3788ddb9631d2c8a2fa7f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54693652"
---
# <a name="initialize-function"></a><span data-ttu-id="35dc4-103">Initialize (funzione)</span><span class="sxs-lookup"><span data-stu-id="35dc4-103">Initialize function</span></span>
<span data-ttu-id="35dc4-104">Esegue l'inizializzazione di WMI.</span><span class="sxs-lookup"><span data-stu-id="35dc4-104">Performs WMI initialization.</span></span>  
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="35dc4-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="35dc4-105">Syntax</span></span> 
```  
HRESULT Initialize(
   [in] boolean bAllowIManagementObjectQI
); 
```  
## <a name="parameters"></a><span data-ttu-id="35dc4-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="35dc4-106">Parameters</span></span>

`bAllowIManagementObjectQI`   
<span data-ttu-id="35dc4-107">[in] `true` per indicare che sono consentite le chiamate a QueryInterface sugli oggetti WMI. `false` in caso contrario.</span><span class="sxs-lookup"><span data-stu-id="35dc4-107">[in] `true` to indicate that calls to QueryInterface on WMI objects are allowed; `false` otherwise.</span></span>

## <a name="return-value"></a><span data-ttu-id="35dc4-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="35dc4-108">Return value</span></span>

<span data-ttu-id="35dc4-109">La funzione restituisce sempre `S_OK` (0).</span><span class="sxs-lookup"><span data-stu-id="35dc4-109">The function always returns `S_OK` (0).</span></span>
  
## <a name="requirements"></a><span data-ttu-id="35dc4-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="35dc4-110">Requirements</span></span>  
 <span data-ttu-id="35dc4-111">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="35dc4-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="35dc4-112">**Intestazione:** WMINet_Utils.def</span><span class="sxs-lookup"><span data-stu-id="35dc4-112">**Header:** WMINet_Utils.def</span></span>  
  
 <span data-ttu-id="35dc4-113">**Versioni di .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="35dc4-113">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="35dc4-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="35dc4-114">See also</span></span>
- [<span data-ttu-id="35dc4-115">WMI e contatori delle prestazioni (riferimenti alle API non gestite)</span><span class="sxs-lookup"><span data-stu-id="35dc4-115">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
