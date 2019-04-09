---
title: Interfaccia ICLRHostBindingPolicyManager
ms.date: 03/30/2017
api_name:
- ICLRHostBindingPolicyManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRHostBindingPolicyManager
helpviewer_keywords:
- ICLRHostBindingPolicyManager interface [.NET Framework hosting]
ms.assetid: f9da168b-366b-4b2b-bdb9-330b6bad5a6b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e494bbbd08a77329b7b64816216e4bb2e1b724a2
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59074196"
---
# <a name="iclrhostbindingpolicymanager-interface"></a><span data-ttu-id="eb31f-102">Interfaccia ICLRHostBindingPolicyManager</span><span class="sxs-lookup"><span data-stu-id="eb31f-102">ICLRHostBindingPolicyManager Interface</span></span>
<span data-ttu-id="eb31f-103">Fornisce metodi per l'host valutare i criteri di associazione corrente e comunicare le modifiche dei criteri per un assembly specificato.</span><span class="sxs-lookup"><span data-stu-id="eb31f-103">Provides methods for the host to evaluate current binding policy and communicate policy changes for a specified assembly.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="eb31f-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="eb31f-104">Methods</span></span>  
  
|<span data-ttu-id="eb31f-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="eb31f-105">Method</span></span>|<span data-ttu-id="eb31f-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="eb31f-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="eb31f-107">Metodo EvaluatePolicy</span><span class="sxs-lookup"><span data-stu-id="eb31f-107">EvaluatePolicy Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-evaluatepolicy-method.md)|<span data-ttu-id="eb31f-108">Valuta i criteri di associazione per conto dell'host.</span><span class="sxs-lookup"><span data-stu-id="eb31f-108">Evaluates binding policy on behalf of the host.</span></span>|  
|[<span data-ttu-id="eb31f-109">Metodo ModifyApplicationPolicy</span><span class="sxs-lookup"><span data-stu-id="eb31f-109">ModifyApplicationPolicy Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-modifyapplicationpolicy-method.md)|<span data-ttu-id="eb31f-110">Modifica i criteri di associazione per l'assembly specificato e crea una nuova versione del criterio.</span><span class="sxs-lookup"><span data-stu-id="eb31f-110">Modifies the binding policy for the specified assembly, and creates a new version of the policy.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="eb31f-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="eb31f-111">Requirements</span></span>  
 <span data-ttu-id="eb31f-112">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="eb31f-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="eb31f-113">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="eb31f-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="eb31f-114">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="eb31f-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="eb31f-115">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="eb31f-115">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="eb31f-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="eb31f-116">See also</span></span>

- [<span data-ttu-id="eb31f-117">Interfaccia ICLRAssemblyIdentityManager</span><span class="sxs-lookup"><span data-stu-id="eb31f-117">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="eb31f-118">Interfaccia IHostAssemblyStore</span><span class="sxs-lookup"><span data-stu-id="eb31f-118">IHostAssemblyStore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)
- [<span data-ttu-id="eb31f-119">Interfacce di hosting</span><span class="sxs-lookup"><span data-stu-id="eb31f-119">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
