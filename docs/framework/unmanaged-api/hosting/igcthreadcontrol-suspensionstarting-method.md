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
ms.openlocfilehash: 95cbda3729c02b95557f9f700f1ea7c68aa450a1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33438015"
---
# <a name="igcthreadcontrolsuspensionstarting-method"></a><span data-ttu-id="79291-102">Metodo IGCThreadControl::SuspensionStarting</span><span class="sxs-lookup"><span data-stu-id="79291-102">IGCThreadControl::SuspensionStarting Method</span></span>
<span data-ttu-id="79291-103">Notifica all'host che il runtime sta avviando una sospensione di thread per una garbage collection o un'altra sospensione.</span><span class="sxs-lookup"><span data-stu-id="79291-103">Notifies the host that the runtime is beginning a thread suspension for a garbage collection or other suspension.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="79291-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="79291-104">Syntax</span></span>  
  
```  
HRESULT SuspensionStarting ( );  
```  
  
## <a name="remarks"></a><span data-ttu-id="79291-105">Note</span><span class="sxs-lookup"><span data-stu-id="79291-105">Remarks</span></span>  
 <span data-ttu-id="79291-106">Non modificare la pianificazione di thread durante il `SuspensionStarting` callback.</span><span class="sxs-lookup"><span data-stu-id="79291-106">Do not reschedule any threads during the `SuspensionStarting` callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="79291-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="79291-107">Requirements</span></span>  
 <span data-ttu-id="79291-108">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="79291-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="79291-109">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="79291-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="79291-110">**Libreria:** inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="79291-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="79291-111">**Versioni di .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="79291-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="79291-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="79291-112">See Also</span></span>  
 [<span data-ttu-id="79291-113">Interfaccia IGCThreadControl</span><span class="sxs-lookup"><span data-stu-id="79291-113">IGCThreadControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igcthreadcontrol-interface.md)
