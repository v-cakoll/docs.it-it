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
ms.openlocfilehash: 3c6def32c63e3557a4de72baf7b1c3e67feb4891
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73136525"
---
# <a name="getclridentitymanager-function"></a><span data-ttu-id="270c6-102">Funzione GetCLRIdentityManager</span><span class="sxs-lookup"><span data-stu-id="270c6-102">GetCLRIdentityManager Function</span></span>
<span data-ttu-id="270c6-103">Ottiene un puntatore a un'interfaccia che consente all'Common Language Runtime (CLR) di gestire le identità.</span><span class="sxs-lookup"><span data-stu-id="270c6-103">Gets a pointer to an interface that allows the common language runtime (CLR) to manage identities.</span></span>  
  
 <span data-ttu-id="270c6-104">Questa funzione è stata deprecata nel .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="270c6-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="270c6-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="270c6-105">Syntax</span></span>  
  
```cpp  
STDAPI GetCLRIdentityManager(  
    [in]  REFIID      riid,  
    [out] IUnknown  **ppManager  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="270c6-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="270c6-106">Parameters</span></span>  
 `riid`  
 <span data-ttu-id="270c6-107">in Un `REFIID` (un identificatore di interfaccia) che specifica l'interfaccia da ottenere.</span><span class="sxs-lookup"><span data-stu-id="270c6-107">[in] A `REFIID` (an interface identifier) that specifies which interface to get.</span></span> <span data-ttu-id="270c6-108">Questo valore deve essere IID_ICLRAssemblyIdentityManager o IID_ICLRHostBindingPolicyManager.</span><span class="sxs-lookup"><span data-stu-id="270c6-108">This value must be either IID_ICLRAssemblyIdentityManager or IID_ICLRHostBindingPolicyManager.</span></span>  
  
 `ppManager`  
 <span data-ttu-id="270c6-109">out Puntatore all'indirizzo di un oggetto [ICLRAssemblyIdentityManager](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md) o [ICLRHostBindingPolicyManager](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="270c6-109">[out] A pointer to the address of either an [ICLRAssemblyIdentityManager](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md) or an [ICLRHostBindingPolicyManager](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-interface.md) object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="270c6-110">Note</span><span class="sxs-lookup"><span data-stu-id="270c6-110">Remarks</span></span>  
 <span data-ttu-id="270c6-111">Chiamare la funzione [GetRealProcAddress](../../../../docs/framework/unmanaged-api/hosting/getrealprocaddress-function.md) per ottenere un puntatore alla funzione `GetCLRIdentityManager`.</span><span class="sxs-lookup"><span data-stu-id="270c6-111">Call the [GetRealProcAddress](../../../../docs/framework/unmanaged-api/hosting/getrealprocaddress-function.md) function to get a pointer to the `GetCLRIdentityManager` function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="270c6-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="270c6-112">Requirements</span></span>  
 <span data-ttu-id="270c6-113">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="270c6-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="270c6-114">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="270c6-114">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="270c6-115">**Libreria:** MSCorWks. dll</span><span class="sxs-lookup"><span data-stu-id="270c6-115">**Library:** MSCorWks.dll</span></span>  
  
 <span data-ttu-id="270c6-116">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="270c6-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="270c6-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="270c6-117">See also</span></span>

- [<span data-ttu-id="270c6-118">Funzioni di hosting CLR deprecate</span><span class="sxs-lookup"><span data-stu-id="270c6-118">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
