---
title: Metodo IGCThreadControl::SuspensionStarting
ms.date: 03/30/2017
api_name:
- IGCThreadControl.SuspensionStarting
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- SuspensionStarting
helpviewer_keywords:
- IGCThreadControl::SuspensionStarting method [.NET Framework hosting]
- SuspensionStarting method, IGCThreadControl interface [.NET Framework hosting]
ms.assetid: 0af312af-98e9-415e-b182-42e80a1aee51
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7613bc744ad4c2e172fc4f6dd7bf282fb3d9072c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61992758"
---
# <a name="igcthreadcontrolsuspensionstarting-method"></a><span data-ttu-id="bafa9-102">Metodo IGCThreadControl::SuspensionStarting</span><span class="sxs-lookup"><span data-stu-id="bafa9-102">IGCThreadControl::SuspensionStarting Method</span></span>
<span data-ttu-id="bafa9-103">Notifica all'host di runtime è l'avvio di una sospensione di thread per una garbage collection o un'altra sospensione.</span><span class="sxs-lookup"><span data-stu-id="bafa9-103">Notifies the host that the runtime is beginning a thread suspension for a garbage collection or other suspension.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bafa9-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="bafa9-104">Syntax</span></span>  
  
```  
HRESULT SuspensionStarting ( );  
```  
  
## <a name="remarks"></a><span data-ttu-id="bafa9-105">Note</span><span class="sxs-lookup"><span data-stu-id="bafa9-105">Remarks</span></span>  
 <span data-ttu-id="bafa9-106">Non modificare la pianificazione di tutti i thread durante il `SuspensionStarting` callback.</span><span class="sxs-lookup"><span data-stu-id="bafa9-106">Do not reschedule any threads during the `SuspensionStarting` callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bafa9-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="bafa9-107">Requirements</span></span>  
 <span data-ttu-id="bafa9-108">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bafa9-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bafa9-109">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="bafa9-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="bafa9-110">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="bafa9-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="bafa9-111">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bafa9-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bafa9-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bafa9-112">See also</span></span>

- [<span data-ttu-id="bafa9-113">Interfaccia IGCThreadControl</span><span class="sxs-lookup"><span data-stu-id="bafa9-113">IGCThreadControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igcthreadcontrol-interface.md)
