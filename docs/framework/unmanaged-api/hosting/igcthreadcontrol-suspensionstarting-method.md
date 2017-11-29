---
title: Metodo IGCThreadControl::SuspensionStarting
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IGCThreadControl.SuspensionStarting
api_location: mscoree.dll
api_type: COM
f1_keywords: SuspensionStarting
helpviewer_keywords:
- IGCThreadControl::SuspensionStarting method [.NET Framework hosting]
- SuspensionStarting method, IGCThreadControl interface [.NET Framework hosting]
ms.assetid: 0af312af-98e9-415e-b182-42e80a1aee51
topic_type: apiref
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: d9d5f403c2880d0079a89c6de5c2ad9aa4f8d9fa
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="igcthreadcontrolsuspensionstarting-method"></a><span data-ttu-id="a160e-102">Metodo IGCThreadControl::SuspensionStarting</span><span class="sxs-lookup"><span data-stu-id="a160e-102">IGCThreadControl::SuspensionStarting Method</span></span>
<span data-ttu-id="a160e-103">Notifica all'host che il runtime sta avviando una sospensione di thread per una garbage collection o un'altra sospensione.</span><span class="sxs-lookup"><span data-stu-id="a160e-103">Notifies the host that the runtime is beginning a thread suspension for a garbage collection or other suspension.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a160e-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a160e-104">Syntax</span></span>  
  
```  
HRESULT SuspensionStarting ( );  
```  
  
## <a name="remarks"></a><span data-ttu-id="a160e-105">Note</span><span class="sxs-lookup"><span data-stu-id="a160e-105">Remarks</span></span>  
 <span data-ttu-id="a160e-106">Non modificare la pianificazione di thread durante il `SuspensionStarting` callback.</span><span class="sxs-lookup"><span data-stu-id="a160e-106">Do not reschedule any threads during the `SuspensionStarting` callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a160e-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="a160e-107">Requirements</span></span>  
 <span data-ttu-id="a160e-108">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a160e-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a160e-109">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="a160e-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a160e-110">**Libreria:** inclusa come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="a160e-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a160e-111">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a160e-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a160e-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a160e-112">See Also</span></span>  
 [<span data-ttu-id="a160e-113">IGCThreadControl (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="a160e-113">IGCThreadControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igcthreadcontrol-interface.md)
