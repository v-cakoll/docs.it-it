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
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59179751"
---
# <a name="igcthreadcontrolsuspensionstarting-method"></a><span data-ttu-id="88125-102">Metodo IGCThreadControl::SuspensionStarting</span><span class="sxs-lookup"><span data-stu-id="88125-102">IGCThreadControl::SuspensionStarting Method</span></span>
<span data-ttu-id="88125-103">Notifica all'host di runtime è l'avvio di una sospensione di thread per una garbage collection o un'altra sospensione.</span><span class="sxs-lookup"><span data-stu-id="88125-103">Notifies the host that the runtime is beginning a thread suspension for a garbage collection or other suspension.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="88125-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="88125-104">Syntax</span></span>  
  
```  
HRESULT SuspensionStarting ( );  
```  
  
## <a name="remarks"></a><span data-ttu-id="88125-105">Note</span><span class="sxs-lookup"><span data-stu-id="88125-105">Remarks</span></span>  
 <span data-ttu-id="88125-106">Non modificare la pianificazione di tutti i thread durante il `SuspensionStarting` callback.</span><span class="sxs-lookup"><span data-stu-id="88125-106">Do not reschedule any threads during the `SuspensionStarting` callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="88125-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="88125-107">Requirements</span></span>  
 <span data-ttu-id="88125-108">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="88125-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="88125-109">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="88125-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="88125-110">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="88125-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="88125-111">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="88125-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="88125-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="88125-112">See also</span></span>

- [<span data-ttu-id="88125-113">Interfaccia IGCThreadControl</span><span class="sxs-lookup"><span data-stu-id="88125-113">IGCThreadControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igcthreadcontrol-interface.md)
