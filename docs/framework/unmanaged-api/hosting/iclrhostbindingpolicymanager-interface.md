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
ms.openlocfilehash: 3cf2a945607bf85a51dbec35342ff5ac46878bca
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2020
ms.locfileid: "83703573"
---
# <a name="iclrhostbindingpolicymanager-interface"></a><span data-ttu-id="ff893-102">Interfaccia ICLRHostBindingPolicyManager</span><span class="sxs-lookup"><span data-stu-id="ff893-102">ICLRHostBindingPolicyManager Interface</span></span>
<span data-ttu-id="ff893-103">Fornisce metodi che consentono all'host di valutare i criteri di associazione correnti e di comunicare le modifiche dei criteri per un assembly specificato.</span><span class="sxs-lookup"><span data-stu-id="ff893-103">Provides methods for the host to evaluate current binding policy and communicate policy changes for a specified assembly.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="ff893-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="ff893-104">Methods</span></span>  
  
|<span data-ttu-id="ff893-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="ff893-105">Method</span></span>|<span data-ttu-id="ff893-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ff893-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="ff893-107">Metodo EvaluatePolicy</span><span class="sxs-lookup"><span data-stu-id="ff893-107">EvaluatePolicy Method</span></span>](iclrhostbindingpolicymanager-evaluatepolicy-method.md)|<span data-ttu-id="ff893-108">Valuta i criteri di associazione per conto dell'host.</span><span class="sxs-lookup"><span data-stu-id="ff893-108">Evaluates binding policy on behalf of the host.</span></span>|  
|[<span data-ttu-id="ff893-109">Metodo ModifyApplicationPolicy</span><span class="sxs-lookup"><span data-stu-id="ff893-109">ModifyApplicationPolicy Method</span></span>](iclrhostbindingpolicymanager-modifyapplicationpolicy-method.md)|<span data-ttu-id="ff893-110">Modifica i criteri di associazione per l'assembly specificato e crea una nuova versione del criterio.</span><span class="sxs-lookup"><span data-stu-id="ff893-110">Modifies the binding policy for the specified assembly, and creates a new version of the policy.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ff893-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ff893-111">Requirements</span></span>  
 <span data-ttu-id="ff893-112">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ff893-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ff893-113">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="ff893-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ff893-114">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="ff893-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ff893-115">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ff893-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ff893-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ff893-116">See also</span></span>

- [<span data-ttu-id="ff893-117">Interfaccia ICLRAssemblyIdentityManager</span><span class="sxs-lookup"><span data-stu-id="ff893-117">ICLRAssemblyIdentityManager Interface</span></span>](iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="ff893-118">Interfaccia IHostAssemblyStore</span><span class="sxs-lookup"><span data-stu-id="ff893-118">IHostAssemblyStore Interface</span></span>](ihostassemblystore-interface.md)
- [<span data-ttu-id="ff893-119">Interfacce di hosting</span><span class="sxs-lookup"><span data-stu-id="ff893-119">Hosting Interfaces</span></span>](hosting-interfaces.md)
