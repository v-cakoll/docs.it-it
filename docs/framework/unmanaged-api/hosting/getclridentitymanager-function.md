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
ms.openlocfilehash: 57f771d933e896677dfc0bd5d9dac58da2af22c8
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83617256"
---
# <a name="getclridentitymanager-function"></a><span data-ttu-id="0bd6b-102">Funzione GetCLRIdentityManager</span><span class="sxs-lookup"><span data-stu-id="0bd6b-102">GetCLRIdentityManager Function</span></span>
<span data-ttu-id="0bd6b-103">Ottiene un puntatore a un'interfaccia che consente all'Common Language Runtime (CLR) di gestire le identità.</span><span class="sxs-lookup"><span data-stu-id="0bd6b-103">Gets a pointer to an interface that allows the common language runtime (CLR) to manage identities.</span></span>  
  
 <span data-ttu-id="0bd6b-104">Questa funzione è stata deprecata nel .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="0bd6b-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0bd6b-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0bd6b-105">Syntax</span></span>  
  
```cpp  
STDAPI GetCLRIdentityManager(  
    [in]  REFIID      riid,  
    [out] IUnknown  **ppManager  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0bd6b-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="0bd6b-106">Parameters</span></span>  
 `riid`  
 <span data-ttu-id="0bd6b-107">in Oggetto `REFIID` (un identificatore di interfaccia) che specifica l'interfaccia da ottenere.</span><span class="sxs-lookup"><span data-stu-id="0bd6b-107">[in] A `REFIID` (an interface identifier) that specifies which interface to get.</span></span> <span data-ttu-id="0bd6b-108">Questo valore deve essere IID_ICLRAssemblyIdentityManager o IID_ICLRHostBindingPolicyManager.</span><span class="sxs-lookup"><span data-stu-id="0bd6b-108">This value must be either IID_ICLRAssemblyIdentityManager or IID_ICLRHostBindingPolicyManager.</span></span>  
  
 `ppManager`  
 <span data-ttu-id="0bd6b-109">out Puntatore all'indirizzo di un oggetto [ICLRAssemblyIdentityManager](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md) o [ICLRHostBindingPolicyManager](iclrhostbindingpolicymanager-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="0bd6b-109">[out] A pointer to the address of either an [ICLRAssemblyIdentityManager](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md) or an [ICLRHostBindingPolicyManager](iclrhostbindingpolicymanager-interface.md) object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0bd6b-110">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="0bd6b-110">Remarks</span></span>  
 <span data-ttu-id="0bd6b-111">Chiamare la funzione [GetRealProcAddress](getrealprocaddress-function.md) per ottenere un puntatore alla `GetCLRIdentityManager` funzione.</span><span class="sxs-lookup"><span data-stu-id="0bd6b-111">Call the [GetRealProcAddress](getrealprocaddress-function.md) function to get a pointer to the `GetCLRIdentityManager` function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0bd6b-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="0bd6b-112">Requirements</span></span>  
 <span data-ttu-id="0bd6b-113">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0bd6b-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0bd6b-114">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="0bd6b-114">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="0bd6b-115">**Libreria:** MSCorWks. dll</span><span class="sxs-lookup"><span data-stu-id="0bd6b-115">**Library:** MSCorWks.dll</span></span>  
  
 <span data-ttu-id="0bd6b-116">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0bd6b-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0bd6b-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0bd6b-117">See also</span></span>

- [<span data-ttu-id="0bd6b-118">Funzioni di hosting CLR deprecate</span><span class="sxs-lookup"><span data-stu-id="0bd6b-118">Deprecated CLR Hosting Functions</span></span>](deprecated-clr-hosting-functions.md)
