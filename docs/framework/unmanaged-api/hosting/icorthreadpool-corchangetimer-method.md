---
title: Metodo ICorThreadpool::CorChangeTimer
ms.date: 03/30/2017
api_name:
- ICorThreadpool.CorChangeTimer
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorChangeTimer
helpviewer_keywords:
- CorChangeTimer method [.NET Framework hosting]
- ICorThreadpool::CorChangeTimer method [.NET Framework hosting]
ms.assetid: 82b03a59-5a87-43ed-9b75-e04b256e1a46
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b56a0cc1e6c110c1e201a365dc333e700686a4a2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33436871"
---
# <a name="icorthreadpoolcorchangetimer-method"></a><span data-ttu-id="e4146-102">Metodo ICorThreadpool::CorChangeTimer</span><span class="sxs-lookup"><span data-stu-id="e4146-102">ICorThreadpool::CorChangeTimer Method</span></span>
<span data-ttu-id="e4146-103">Questo metodo supporta l'infrastruttura .NET Framework e non può essere utilizzato direttamente dal codice.</span><span class="sxs-lookup"><span data-stu-id="e4146-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e4146-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e4146-104">Syntax</span></span>  
  
```  
HRESULT CorChangeTimer (  
    [in]  HANDLE Timer,   
    [in]  ULONG  DueTime,   
    [in]  ULONG  Period,  
    [out] BOOL*  result  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="e4146-105">Requisiti</span><span class="sxs-lookup"><span data-stu-id="e4146-105">Requirements</span></span>  
 <span data-ttu-id="e4146-106">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e4146-106">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e4146-107">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="e4146-107">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e4146-108">**Libreria:** inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="e4146-108">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e4146-109">**Versioni di .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e4146-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e4146-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e4146-110">See Also</span></span>  
 [<span data-ttu-id="e4146-111">Interfaccia ICorThreadpool</span><span class="sxs-lookup"><span data-stu-id="e4146-111">ICorThreadpool Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorthreadpool-interface.md)
