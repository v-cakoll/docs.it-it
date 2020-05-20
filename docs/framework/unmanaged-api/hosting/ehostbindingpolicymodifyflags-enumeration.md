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
ms.openlocfilehash: 256c362ae0aea51fea16ce799db243b105dee81a
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616242"
---
# <a name="ehostbindingpolicymodifyflags-enumeration"></a><span data-ttu-id="42c93-102">Enumerazione EHostBindingPolicyModifyFlags</span><span class="sxs-lookup"><span data-stu-id="42c93-102">EHostBindingPolicyModifyFlags Enumeration</span></span>
<span data-ttu-id="42c93-103">Consente all'host di specificare il tipo di reindirizzamento che il Common Language Runtime (CLR) deve eseguire quando si applicano le modifiche dei criteri da un assembly di origine a un assembly di destinazione.</span><span class="sxs-lookup"><span data-stu-id="42c93-103">Allows the host to specify the type of redirection the common language runtime (CLR) should perform when applying policy modifications from a source assembly to a target assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="42c93-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="42c93-104">Syntax</span></span>  
  
```cpp  
typedef enum _hostBindingPolicyModifyFlags {  
    HOST_BINDING_POLICY_MODIFY_DEFAULT  = 0,  
    HOST_BINDING_POLICY_MODIFY_CHAIN    = 1,  
    HOST_BINDING_POLICY_MODIFY_REMOVE   = 2,  
    HOST_BINDING_POLICY_MODIFY_MAX      = 3  
} EHostBindingPolicyModifyFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="42c93-105">Membri</span><span class="sxs-lookup"><span data-stu-id="42c93-105">Members</span></span>  
  
|<span data-ttu-id="42c93-106">Membro</span><span class="sxs-lookup"><span data-stu-id="42c93-106">Member</span></span>|<span data-ttu-id="42c93-107">Description</span><span class="sxs-lookup"><span data-stu-id="42c93-107">Description</span></span>|  
|------------|-----------------|  
|`HOST_BINDING_POLICY_MODIFY_CHAIN`|<span data-ttu-id="42c93-108">Specifica che CLR concatena i valori dei criteri dell'assembly di origine su quelli dell'assembly di destinazione.</span><span class="sxs-lookup"><span data-stu-id="42c93-108">Specifies that the CLR will chain policy values of the source assembly onto those of the target assembly.</span></span>|  
|`HOST_BINDING_POLICY_MODIFY_DEFAULT`|<span data-ttu-id="42c93-109">Specifica che CLR eseguirà l'azione predefinita.</span><span class="sxs-lookup"><span data-stu-id="42c93-109">Specifies that the CLR will perform the default action.</span></span>|  
|`HOST_BINDING_POLICY_MODIFY_MAX`|<span data-ttu-id="42c93-110">Specifica che CLR imposterà i valori dei criteri dell'assembly di destinazione sui valori massimi.</span><span class="sxs-lookup"><span data-stu-id="42c93-110">Specifies that the CLR will set the policy values of the target assembly to the maximum values.</span></span>|  
|`HOST_BINDING_POLICY_MODIFY_REMOVE`|<span data-ttu-id="42c93-111">Specifica che CLR sostituirà i valori dei criteri dell'assembly di destinazione con quelli dell'assembly di origine.</span><span class="sxs-lookup"><span data-stu-id="42c93-111">Specifies that the CLR will replace policy values of the target assembly with those of the source assembly.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="42c93-112">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="42c93-112">Remarks</span></span>  
 <span data-ttu-id="42c93-113">Il metodo [ICLRHostBindingPolicyManager:: ModifyApplicationPolicy](iclrhostbindingpolicymanager-modifyapplicationpolicy-method.md) accetta un parametro di tipo `EHostBindingPolicyModifyFlags` .</span><span class="sxs-lookup"><span data-stu-id="42c93-113">The [ICLRHostBindingPolicyManager::ModifyApplicationPolicy](iclrhostbindingpolicymanager-modifyapplicationpolicy-method.md) method takes a parameter of type `EHostBindingPolicyModifyFlags`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="42c93-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="42c93-114">Requirements</span></span>  
 <span data-ttu-id="42c93-115">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="42c93-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="42c93-116">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="42c93-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="42c93-117">**Libreria:** MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="42c93-117">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="42c93-118">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="42c93-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="42c93-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="42c93-119">See also</span></span>

- [<span data-ttu-id="42c93-120">Interfaccia ICLRHostBindingPolicyManager</span><span class="sxs-lookup"><span data-stu-id="42c93-120">ICLRHostBindingPolicyManager Interface</span></span>](iclrhostbindingpolicymanager-interface.md)
- [<span data-ttu-id="42c93-121">Enumerazioni di hosting</span><span class="sxs-lookup"><span data-stu-id="42c93-121">Hosting Enumerations</span></span>](hosting-enumerations.md)
