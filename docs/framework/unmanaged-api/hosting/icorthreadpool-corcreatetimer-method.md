---
title: Metodo ICorThreadpool::CorCreateTimer
ms.date: 03/30/2017
api_name:
- ICorThreadpool.CorCreateTimer
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorCreateTimer
helpviewer_keywords:
- CorCreateTimer method [.NET Framework hosting]
- ICorThreadpool::CorCreateTimer method [.NET Framework hosting]
ms.assetid: 0d56ef25-30f1-4499-8a1f-76e7654ec614
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7dfa1dd15f38263ffdfef594ab030867b3fed1de
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33436777"
---
# <a name="icorthreadpoolcorcreatetimer-method"></a><span data-ttu-id="1c93b-102">Metodo ICorThreadpool::CorCreateTimer</span><span class="sxs-lookup"><span data-stu-id="1c93b-102">ICorThreadpool::CorCreateTimer Method</span></span>
<span data-ttu-id="1c93b-103">Questo metodo supporta l'infrastruttura .NET Framework e non può essere utilizzato direttamente dal codice.</span><span class="sxs-lookup"><span data-stu-id="1c93b-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1c93b-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1c93b-104">Syntax</span></span>  
  
```  
HRESULT CorCreateTimer (  
    [in]  HANDLE*             phNewTimer,  
    [in]  WAITORTIMERCALLBACK Callback,  
    [in]  PVOID               Parameter,  
    [in]  DWORD               DueTime,  
    [in]  DWORD               Period,  
    [out] BOOL*               result  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="1c93b-105">Requisiti</span><span class="sxs-lookup"><span data-stu-id="1c93b-105">Requirements</span></span>  
 <span data-ttu-id="1c93b-106">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1c93b-106">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1c93b-107">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="1c93b-107">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="1c93b-108">**Libreria:** inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="1c93b-108">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1c93b-109">**Versioni di .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1c93b-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1c93b-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1c93b-110">See Also</span></span>  
 [<span data-ttu-id="1c93b-111">Interfaccia ICorThreadpool</span><span class="sxs-lookup"><span data-stu-id="1c93b-111">ICorThreadpool Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorthreadpool-interface.md)
