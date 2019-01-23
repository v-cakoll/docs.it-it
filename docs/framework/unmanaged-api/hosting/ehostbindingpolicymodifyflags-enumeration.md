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
ms.openlocfilehash: b3aba84f1ae451ee943028d063e91ca7a6d63548
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54504694"
---
# <a name="ehostbindingpolicymodifyflags-enumeration"></a><span data-ttu-id="c0f51-102">Enumerazione EHostBindingPolicyModifyFlags</span><span class="sxs-lookup"><span data-stu-id="c0f51-102">EHostBindingPolicyModifyFlags Enumeration</span></span>
<span data-ttu-id="c0f51-103">Consente all'host specificare il tipo di reindirizzamento che Common language runtime (CLR) deve essere eseguito quando si applicano le modifiche dei criteri da un assembly di origine a un assembly di destinazione.</span><span class="sxs-lookup"><span data-stu-id="c0f51-103">Allows the host to specify the type of redirection the common language runtime (CLR) should perform when applying policy modifications from a source assembly to a target assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c0f51-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c0f51-104">Syntax</span></span>  
  
```  
typedef enum _hostBindingPolicyModifyFlags {  
    HOST_BINDING_POLICY_MODIFY_DEFAULT  = 0,  
    HOST_BINDING_POLICY_MODIFY_CHAIN    = 1,  
    HOST_BINDING_POLICY_MODIFY_REMOVE   = 2,  
    HOST_BINDING_POLICY_MODIFY_MAX      = 3  
} EHostBindingPolicyModifyFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="c0f51-105">Membri</span><span class="sxs-lookup"><span data-stu-id="c0f51-105">Members</span></span>  
  
|<span data-ttu-id="c0f51-106">Membro</span><span class="sxs-lookup"><span data-stu-id="c0f51-106">Member</span></span>|<span data-ttu-id="c0f51-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c0f51-107">Description</span></span>|  
|------------|-----------------|  
|`HOST_BINDING_POLICY_MODIFY_CHAIN`|<span data-ttu-id="c0f51-108">Specifica che Common Language Runtime verrà concatenare i valori dei criteri dell'assembly di origine a quelli dell'assembly di destinazione.</span><span class="sxs-lookup"><span data-stu-id="c0f51-108">Specifies that the CLR will chain policy values of the source assembly onto those of the target assembly.</span></span>|  
|`HOST_BINDING_POLICY_MODIFY_DEFAULT`|<span data-ttu-id="c0f51-109">Specifica che il CLR eseguirà l'azione predefinita.</span><span class="sxs-lookup"><span data-stu-id="c0f51-109">Specifies that the CLR will perform the default action.</span></span>|  
|`HOST_BINDING_POLICY_MODIFY_MAX`|<span data-ttu-id="c0f51-110">Specifica che Common Language Runtime verrà impostato i valori dei criteri dell'assembly di destinazione per i valori massimi.</span><span class="sxs-lookup"><span data-stu-id="c0f51-110">Specifies that the CLR will set the policy values of the target assembly to the maximum values.</span></span>|  
|`HOST_BINDING_POLICY_MODIFY_REMOVE`|<span data-ttu-id="c0f51-111">Specifica che Common Language Runtime sostituirà i valori dei criteri dell'assembly di destinazione con quelle dell'assembly di origine.</span><span class="sxs-lookup"><span data-stu-id="c0f51-111">Specifies that the CLR will replace policy values of the target assembly with those of the source assembly.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c0f51-112">Note</span><span class="sxs-lookup"><span data-stu-id="c0f51-112">Remarks</span></span>  
 <span data-ttu-id="c0f51-113">Il [ICLRHostBindingPolicyManager](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-modifyapplicationpolicy-method.md) metodo accetta un parametro di tipo `EHostBindingPolicyModifyFlags`.</span><span class="sxs-lookup"><span data-stu-id="c0f51-113">The [ICLRHostBindingPolicyManager::ModifyApplicationPolicy](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-modifyapplicationpolicy-method.md) method takes a parameter of type `EHostBindingPolicyModifyFlags`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c0f51-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="c0f51-114">Requirements</span></span>  
 <span data-ttu-id="c0f51-115">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c0f51-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c0f51-116">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="c0f51-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c0f51-117">**Libreria:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="c0f51-117">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c0f51-118">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c0f51-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c0f51-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c0f51-119">See also</span></span>
- [<span data-ttu-id="c0f51-120">Interfaccia ICLRHostBindingPolicyManager</span><span class="sxs-lookup"><span data-stu-id="c0f51-120">ICLRHostBindingPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-interface.md)
- [<span data-ttu-id="c0f51-121">Enumerazioni di hosting</span><span class="sxs-lookup"><span data-stu-id="c0f51-121">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
