---
title: Enumerazione EHostBindingPolicyModifyFlags
ms.date: 03/30/2017
api_name:
- EHostBindingPolicyModifyFlags
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- EHostBindingPolicyModifyFlags
helpviewer_keywords:
- EHostBindingPolicyModifyFlags enumeration [.NET Framework hosting]
ms.assetid: 0339af16-ee1d-48ec-837d-a79d9a9c89f8
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2fa8cc15f77ff59e3d3c570341d9bba70cf1e953
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33431714"
---
# <a name="ehostbindingpolicymodifyflags-enumeration"></a><span data-ttu-id="1fc7c-102">Enumerazione EHostBindingPolicyModifyFlags</span><span class="sxs-lookup"><span data-stu-id="1fc7c-102">EHostBindingPolicyModifyFlags Enumeration</span></span>
<span data-ttu-id="1fc7c-103">Consente all'host di specificare il tipo di reindirizzamento che Common language runtime (CLR) deve essere eseguito quando si applicano le modifiche dei criteri da un assembly di origine a un assembly di destinazione.</span><span class="sxs-lookup"><span data-stu-id="1fc7c-103">Allows the host to specify the type of redirection the common language runtime (CLR) should perform when applying policy modifications from a source assembly to a target assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1fc7c-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1fc7c-104">Syntax</span></span>  
  
```  
typedef enum _hostBindingPolicyModifyFlags {  
    HOST_BINDING_POLICY_MODIFY_DEFAULT  = 0,  
    HOST_BINDING_POLICY_MODIFY_CHAIN    = 1,  
    HOST_BINDING_POLICY_MODIFY_REMOVE   = 2,  
    HOST_BINDING_POLICY_MODIFY_MAX      = 3  
} EHostBindingPolicyModifyFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="1fc7c-105">Membri</span><span class="sxs-lookup"><span data-stu-id="1fc7c-105">Members</span></span>  
  
|<span data-ttu-id="1fc7c-106">Membro</span><span class="sxs-lookup"><span data-stu-id="1fc7c-106">Member</span></span>|<span data-ttu-id="1fc7c-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1fc7c-107">Description</span></span>|  
|------------|-----------------|  
|`HOST_BINDING_POLICY_MODIFY_CHAIN`|<span data-ttu-id="1fc7c-108">Consente di specificare che CLR dovrà concatenare i valori dei criteri dell'assembly di origine a quelli dell'assembly di destinazione.</span><span class="sxs-lookup"><span data-stu-id="1fc7c-108">Specifies that the CLR will chain policy values of the source assembly onto those of the target assembly.</span></span>|  
|`HOST_BINDING_POLICY_MODIFY_DEFAULT`|<span data-ttu-id="1fc7c-109">Specifica che Common Language Runtime eseguirà l'azione predefinita.</span><span class="sxs-lookup"><span data-stu-id="1fc7c-109">Specifies that the CLR will perform the default action.</span></span>|  
|`HOST_BINDING_POLICY_MODIFY_MAX`|<span data-ttu-id="1fc7c-110">Specifica che il CLR imposta i valori dei criteri dell'assembly di destinazione per i valori massimi.</span><span class="sxs-lookup"><span data-stu-id="1fc7c-110">Specifies that the CLR will set the policy values of the target assembly to the maximum values.</span></span>|  
|`HOST_BINDING_POLICY_MODIFY_REMOVE`|<span data-ttu-id="1fc7c-111">Specifica che Common Language Runtime sostituirà i valori dei criteri dell'assembly di destinazione con quelle dell'assembly di origine.</span><span class="sxs-lookup"><span data-stu-id="1fc7c-111">Specifies that the CLR will replace policy values of the target assembly with those of the source assembly.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1fc7c-112">Note</span><span class="sxs-lookup"><span data-stu-id="1fc7c-112">Remarks</span></span>  
 <span data-ttu-id="1fc7c-113">Il [ICLRHostBindingPolicyManager:: ModifyApplicationPolicy](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-modifyapplicationpolicy-method.md) metodo accetta un parametro di tipo `EHostBindingPolicyModifyFlags`.</span><span class="sxs-lookup"><span data-stu-id="1fc7c-113">The [ICLRHostBindingPolicyManager::ModifyApplicationPolicy](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-modifyapplicationpolicy-method.md) method takes a parameter of type `EHostBindingPolicyModifyFlags`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1fc7c-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="1fc7c-114">Requirements</span></span>  
 <span data-ttu-id="1fc7c-115">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1fc7c-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1fc7c-116">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="1fc7c-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="1fc7c-117">**Libreria:** Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="1fc7c-117">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1fc7c-118">**Versioni di .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1fc7c-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1fc7c-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1fc7c-119">See Also</span></span>  
 [<span data-ttu-id="1fc7c-120">Interfaccia ICLRHostBindingPolicyManager</span><span class="sxs-lookup"><span data-stu-id="1fc7c-120">ICLRHostBindingPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-interface.md)  
 [<span data-ttu-id="1fc7c-121">Enumerazioni di hosting</span><span class="sxs-lookup"><span data-stu-id="1fc7c-121">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
