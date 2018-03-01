---
title: Interfaccia ICLRHostProtectionManager
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICLRHostProtectionManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRHostProtectionManager
helpviewer_keywords:
- ICLRHostProtectionManager interface [.NET Framework hosting]
ms.assetid: ce2770ae-23d0-45d9-8bcf-46504ac5020e
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 37b1aaeef1d4c375f36ad043124287fc3b41e3fe
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="iclrhostprotectionmanager-interface"></a><span data-ttu-id="48987-102">Interfaccia ICLRHostProtectionManager</span><span class="sxs-lookup"><span data-stu-id="48987-102">ICLRHostProtectionManager Interface</span></span>
<span data-ttu-id="48987-103">Consente all'host di bloccare le classi gestite specifiche, metodi, proprietà e i campi dall'esecuzione di codice parzialmente attendibile.</span><span class="sxs-lookup"><span data-stu-id="48987-103">Enables the host to block specific managed classes, methods, properties, and fields from running in partially trusted code.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="48987-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="48987-104">Methods</span></span>  
  
|<span data-ttu-id="48987-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="48987-105">Method</span></span>|<span data-ttu-id="48987-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="48987-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="48987-107">SetEagerSerializeGrantSets</span><span class="sxs-lookup"><span data-stu-id="48987-107">SetEagerSerializeGrantSets</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-seteagerserializegrantsets-method.md)|<span data-ttu-id="48987-108">Fornisce una garanzia che non si verificheranno mai delle rare race condition che possono causare irreversibili di common language runtime (CLR) errori.</span><span class="sxs-lookup"><span data-stu-id="48987-108">Provides a guarantee that certain rare race conditions that can cause fatal common language runtime (CLR) errors will never arise.</span></span>|  
|[<span data-ttu-id="48987-109">Metodo SetProtectedCategories</span><span class="sxs-lookup"><span data-stu-id="48987-109">SetProtectedCategories Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-setprotectedcategories-method.md)|<span data-ttu-id="48987-110">Specifica le categorie di tipi gestiti e i membri che devono essere bloccati dall'esecuzione di codice parzialmente attendibile.</span><span class="sxs-lookup"><span data-stu-id="48987-110">Specifies the categories of managed types and members that should be blocked from running in partially trusted code.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="48987-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="48987-111">Requirements</span></span>  
 <span data-ttu-id="48987-112">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="48987-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="48987-113">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="48987-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="48987-114">**Libreria:** inclusa come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="48987-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="48987-115">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="48987-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="48987-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="48987-116">See Also</span></span>  
 [<span data-ttu-id="48987-117">Enumerazione EApiCategories</span><span class="sxs-lookup"><span data-stu-id="48987-117">EApiCategories Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eapicategories-enumeration.md)  
 [<span data-ttu-id="48987-118">Interfaccia ICLRControl</span><span class="sxs-lookup"><span data-stu-id="48987-118">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
