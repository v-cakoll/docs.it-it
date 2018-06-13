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
ms.openlocfilehash: 01de35a0cd4d359dfba0375a85fbce017e44b9f8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33455755"
---
# <a name="initialize-function"></a><span data-ttu-id="d9523-103">Initialize (funzione)</span><span class="sxs-lookup"><span data-stu-id="d9523-103">Initialize function</span></span>
<span data-ttu-id="d9523-104">Esegue l'inizializzazione di WMI.</span><span class="sxs-lookup"><span data-stu-id="d9523-104">Performs WMI initialization.</span></span>  
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="d9523-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d9523-105">Syntax</span></span> 
```  
HRESULT Initialize(
   [in] boolean bAllowIManagementObjectQI
); 
```  
## <a name="parameters"></a><span data-ttu-id="d9523-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="d9523-106">Parameters</span></span>

`bAllowIManagementObjectQI`   
<span data-ttu-id="d9523-107">[in] `true` per indicare che sono consentite chiamate a QueryInterface su oggetti WMI; `false` in caso contrario.</span><span class="sxs-lookup"><span data-stu-id="d9523-107">[in] `true` to indicate that calls to QueryInterface on WMI objects are allowed; `false` otherwise.</span></span>

## <a name="return-value"></a><span data-ttu-id="d9523-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="d9523-108">Return value</span></span>

<span data-ttu-id="d9523-109">La funzione restituisce sempre `S_OK` (0).</span><span class="sxs-lookup"><span data-stu-id="d9523-109">The function always returns `S_OK` (0).</span></span>
  
## <a name="requirements"></a><span data-ttu-id="d9523-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="d9523-110">Requirements</span></span>  
 <span data-ttu-id="d9523-111">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d9523-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d9523-112">**Intestazione:** WMINet_Utils.def</span><span class="sxs-lookup"><span data-stu-id="d9523-112">**Header:** WMINet_Utils.def</span></span>  
  
 <span data-ttu-id="d9523-113">**Versioni di .NET framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="d9523-113">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d9523-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d9523-114">See also</span></span>  
[<span data-ttu-id="d9523-115">WMI e i contatori delle prestazioni (riferimenti alle API non gestite)</span><span class="sxs-lookup"><span data-stu-id="d9523-115">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
