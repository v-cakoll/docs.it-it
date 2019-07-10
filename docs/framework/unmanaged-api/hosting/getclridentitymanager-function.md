---
title: Funzione GetCLRIdentityManager
ms.date: 03/30/2017
api_name:
- GetCLRIdentityManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- GetCLRIdentityManager
helpviewer_keywords:
- GetCLRIdentityManager function [.NET Framework hosting]
ms.assetid: 66eeca30-adb4-45f4-aff5-347564c95724
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8ea4947582e4e8bfdb6873a90c5284e9ae9d8a62
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67736249"
---
# <a name="getclridentitymanager-function"></a><span data-ttu-id="967a2-102">Funzione GetCLRIdentityManager</span><span class="sxs-lookup"><span data-stu-id="967a2-102">GetCLRIdentityManager Function</span></span>
<span data-ttu-id="967a2-103">Ottiene un puntatore a un'interfaccia che consente a common language runtime (CLR) per gestire le identità.</span><span class="sxs-lookup"><span data-stu-id="967a2-103">Gets a pointer to an interface that allows the common language runtime (CLR) to manage identities.</span></span>  
  
 <span data-ttu-id="967a2-104">Questa funzione è stata deprecata in .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="967a2-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="967a2-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="967a2-105">Syntax</span></span>  
  
```cpp  
STDAPI GetCLRIdentityManager(  
    [in]  REFIID      riid,  
    [out] IUnknown  **ppManager  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="967a2-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="967a2-106">Parameters</span></span>  
 `riid`  
 <span data-ttu-id="967a2-107">[in] Oggetto `REFIID` (un identificatore di interfaccia) che specifica quale interfaccia da ottenere.</span><span class="sxs-lookup"><span data-stu-id="967a2-107">[in] A `REFIID` (an interface identifier) that specifies which interface to get.</span></span> <span data-ttu-id="967a2-108">Questo valore deve essere IID_ICLRAssemblyIdentityManager o IID_ICLRHostBindingPolicyManager.</span><span class="sxs-lookup"><span data-stu-id="967a2-108">This value must be either IID_ICLRAssemblyIdentityManager or IID_ICLRHostBindingPolicyManager.</span></span>  
  
 `ppManager`  
 <span data-ttu-id="967a2-109">[out] Un puntatore per l'indirizzo di una un' [ICLRAssemblyIdentityManager](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md) o un' [ICLRHostBindingPolicyManager](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-interface.md) oggetto.</span><span class="sxs-lookup"><span data-stu-id="967a2-109">[out] A pointer to the address of either an [ICLRAssemblyIdentityManager](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md) or an [ICLRHostBindingPolicyManager](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-interface.md) object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="967a2-110">Note</span><span class="sxs-lookup"><span data-stu-id="967a2-110">Remarks</span></span>  
 <span data-ttu-id="967a2-111">Chiamare il [GetRealProcAddress](../../../../docs/framework/unmanaged-api/hosting/getrealprocaddress-function.md) per ottenere un puntatore a funzione di `GetCLRIdentityManager` (funzione).</span><span class="sxs-lookup"><span data-stu-id="967a2-111">Call the [GetRealProcAddress](../../../../docs/framework/unmanaged-api/hosting/getrealprocaddress-function.md) function to get a pointer to the `GetCLRIdentityManager` function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="967a2-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="967a2-112">Requirements</span></span>  
 <span data-ttu-id="967a2-113">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="967a2-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="967a2-114">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="967a2-114">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="967a2-115">**Libreria:** MSCorWks.dll</span><span class="sxs-lookup"><span data-stu-id="967a2-115">**Library:** MSCorWks.dll</span></span>  
  
 <span data-ttu-id="967a2-116">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="967a2-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="967a2-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="967a2-117">See also</span></span>

- [<span data-ttu-id="967a2-118">Funzioni di hosting CLR deprecate</span><span class="sxs-lookup"><span data-stu-id="967a2-118">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
