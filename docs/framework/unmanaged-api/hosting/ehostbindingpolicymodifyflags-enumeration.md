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
ms.openlocfilehash: a2faf22b48dd0b809d6c3668a37f2119733a9b18
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73129440"
---
# <a name="ehostbindingpolicymodifyflags-enumeration"></a><span data-ttu-id="991b7-102">Enumerazione EHostBindingPolicyModifyFlags</span><span class="sxs-lookup"><span data-stu-id="991b7-102">EHostBindingPolicyModifyFlags Enumeration</span></span>
<span data-ttu-id="991b7-103">Consente all'host di specificare il tipo di reindirizzamento che il Common Language Runtime (CLR) deve eseguire quando si applicano le modifiche dei criteri da un assembly di origine a un assembly di destinazione.</span><span class="sxs-lookup"><span data-stu-id="991b7-103">Allows the host to specify the type of redirection the common language runtime (CLR) should perform when applying policy modifications from a source assembly to a target assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="991b7-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="991b7-104">Syntax</span></span>  
  
```cpp  
typedef enum _hostBindingPolicyModifyFlags {  
    HOST_BINDING_POLICY_MODIFY_DEFAULT  = 0,  
    HOST_BINDING_POLICY_MODIFY_CHAIN    = 1,  
    HOST_BINDING_POLICY_MODIFY_REMOVE   = 2,  
    HOST_BINDING_POLICY_MODIFY_MAX      = 3  
} EHostBindingPolicyModifyFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="991b7-105">Members</span><span class="sxs-lookup"><span data-stu-id="991b7-105">Members</span></span>  
  
|<span data-ttu-id="991b7-106">Member</span><span class="sxs-lookup"><span data-stu-id="991b7-106">Member</span></span>|<span data-ttu-id="991b7-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="991b7-107">Description</span></span>|  
|------------|-----------------|  
|`HOST_BINDING_POLICY_MODIFY_CHAIN`|<span data-ttu-id="991b7-108">Specifica che CLR concatena i valori dei criteri dell'assembly di origine su quelli dell'assembly di destinazione.</span><span class="sxs-lookup"><span data-stu-id="991b7-108">Specifies that the CLR will chain policy values of the source assembly onto those of the target assembly.</span></span>|  
|`HOST_BINDING_POLICY_MODIFY_DEFAULT`|<span data-ttu-id="991b7-109">Specifica che CLR eseguirà l'azione predefinita.</span><span class="sxs-lookup"><span data-stu-id="991b7-109">Specifies that the CLR will perform the default action.</span></span>|  
|`HOST_BINDING_POLICY_MODIFY_MAX`|<span data-ttu-id="991b7-110">Specifica che CLR imposterà i valori dei criteri dell'assembly di destinazione sui valori massimi.</span><span class="sxs-lookup"><span data-stu-id="991b7-110">Specifies that the CLR will set the policy values of the target assembly to the maximum values.</span></span>|  
|`HOST_BINDING_POLICY_MODIFY_REMOVE`|<span data-ttu-id="991b7-111">Specifica che CLR sostituirà i valori dei criteri dell'assembly di destinazione con quelli dell'assembly di origine.</span><span class="sxs-lookup"><span data-stu-id="991b7-111">Specifies that the CLR will replace policy values of the target assembly with those of the source assembly.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="991b7-112">Note</span><span class="sxs-lookup"><span data-stu-id="991b7-112">Remarks</span></span>  
 <span data-ttu-id="991b7-113">Il metodo [ICLRHostBindingPolicyManager:: ModifyApplicationPolicy](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-modifyapplicationpolicy-method.md) accetta un parametro di tipo `EHostBindingPolicyModifyFlags`.</span><span class="sxs-lookup"><span data-stu-id="991b7-113">The [ICLRHostBindingPolicyManager::ModifyApplicationPolicy](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-modifyapplicationpolicy-method.md) method takes a parameter of type `EHostBindingPolicyModifyFlags`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="991b7-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="991b7-114">Requirements</span></span>  
 <span data-ttu-id="991b7-115">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="991b7-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="991b7-116">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="991b7-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="991b7-117">**Libreria:** MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="991b7-117">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="991b7-118">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="991b7-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="991b7-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="991b7-119">See also</span></span>

- [<span data-ttu-id="991b7-120">Interfaccia ICLRHostBindingPolicyManager</span><span class="sxs-lookup"><span data-stu-id="991b7-120">ICLRHostBindingPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-interface.md)
- [<span data-ttu-id="991b7-121">Enumerazioni di hosting</span><span class="sxs-lookup"><span data-stu-id="991b7-121">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
