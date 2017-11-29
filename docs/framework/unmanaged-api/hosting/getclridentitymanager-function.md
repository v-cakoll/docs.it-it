---
title: Funzione GetCLRIdentityManager
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: GetCLRIdentityManager
api_location: mscoree.dll
api_type: COM
f1_keywords: GetCLRIdentityManager
helpviewer_keywords: GetCLRIdentityManager function [.NET Framework hosting]
ms.assetid: 66eeca30-adb4-45f4-aff5-347564c95724
topic_type: apiref
caps.latest.revision: "15"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: ddc0395b6fd659ecd6a26a3132fccc65bbb961fe
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="getclridentitymanager-function"></a><span data-ttu-id="97833-102">Funzione GetCLRIdentityManager</span><span class="sxs-lookup"><span data-stu-id="97833-102">GetCLRIdentityManager Function</span></span>
<span data-ttu-id="97833-103">Ottiene un puntatore a un'interfaccia che consente a common language runtime (CLR) per gestire le identità.</span><span class="sxs-lookup"><span data-stu-id="97833-103">Gets a pointer to an interface that allows the common language runtime (CLR) to manage identities.</span></span>  
  
 <span data-ttu-id="97833-104">Questa funzione è stata deprecata nel [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="97833-104">This function has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="97833-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="97833-105">Syntax</span></span>  
  
```  
STDAPI GetCLRIdentityManager(  
    [in]  REFIID      riid,  
    [out] IUnknown  **ppManager  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="97833-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="97833-106">Parameters</span></span>  
 `riid`  
 <span data-ttu-id="97833-107">[in] Oggetto `REFIID` (un identificatore di interfaccia) che specifica quale interfaccia da ottenere.</span><span class="sxs-lookup"><span data-stu-id="97833-107">[in] A `REFIID` (an interface identifier) that specifies which interface to get.</span></span> <span data-ttu-id="97833-108">Questo valore deve essere IID_ICLRAssemblyIdentityManager o IID_ICLRHostBindingPolicyManager.</span><span class="sxs-lookup"><span data-stu-id="97833-108">This value must be either IID_ICLRAssemblyIdentityManager or IID_ICLRHostBindingPolicyManager.</span></span>  
  
 `ppManager`  
 <span data-ttu-id="97833-109">[out] Un puntatore all'indirizzo tra un [ICLRAssemblyIdentityManager](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md) o [ICLRHostBindingPolicyManager](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-interface.md) oggetto.</span><span class="sxs-lookup"><span data-stu-id="97833-109">[out] A pointer to the address of either an [ICLRAssemblyIdentityManager](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md) or an [ICLRHostBindingPolicyManager](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-interface.md) object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="97833-110">Note</span><span class="sxs-lookup"><span data-stu-id="97833-110">Remarks</span></span>  
 <span data-ttu-id="97833-111">Chiamare il [GetRealProcAddress](../../../../docs/framework/unmanaged-api/hosting/getrealprocaddress-function.md) funzione per ottenere un puntatore per il `GetCLRIdentityManager` (funzione).</span><span class="sxs-lookup"><span data-stu-id="97833-111">Call the [GetRealProcAddress](../../../../docs/framework/unmanaged-api/hosting/getrealprocaddress-function.md) function to get a pointer to the `GetCLRIdentityManager` function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="97833-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="97833-112">Requirements</span></span>  
 <span data-ttu-id="97833-113">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="97833-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="97833-114">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="97833-114">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="97833-115">**Libreria:** MSCorWks.dll</span><span class="sxs-lookup"><span data-stu-id="97833-115">**Library:** MSCorWks.dll</span></span>  
  
 <span data-ttu-id="97833-116">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="97833-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="97833-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="97833-117">See Also</span></span>  
 [<span data-ttu-id="97833-118">Funzioni di Hosting CLR deprecate</span><span class="sxs-lookup"><span data-stu-id="97833-118">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
