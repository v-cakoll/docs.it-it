---
title: Interfaccia ICLRHostProtectionManager
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRHostProtectionManager
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRHostProtectionManager
helpviewer_keywords: ICLRHostProtectionManager interface [.NET Framework hosting]
ms.assetid: ce2770ae-23d0-45d9-8bcf-46504ac5020e
topic_type: apiref
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: c88279eb26b819adaaaf86dcf59105c6ac728017
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="iclrhostprotectionmanager-interface"></a><span data-ttu-id="e0641-102">Interfaccia ICLRHostProtectionManager</span><span class="sxs-lookup"><span data-stu-id="e0641-102">ICLRHostProtectionManager Interface</span></span>
<span data-ttu-id="e0641-103">Consente all'host di bloccare le classi gestite specifiche, metodi, proprietà e i campi dall'esecuzione di codice parzialmente attendibile.</span><span class="sxs-lookup"><span data-stu-id="e0641-103">Enables the host to block specific managed classes, methods, properties, and fields from running in partially trusted code.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="e0641-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="e0641-104">Methods</span></span>  
  
|<span data-ttu-id="e0641-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="e0641-105">Method</span></span>|<span data-ttu-id="e0641-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e0641-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="e0641-107">SetEagerSerializeGrantSets</span><span class="sxs-lookup"><span data-stu-id="e0641-107">SetEagerSerializeGrantSets</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-seteagerserializegrantsets-method.md)|<span data-ttu-id="e0641-108">Fornisce una garanzia che non si verificheranno mai delle rare race condition che possono causare irreversibili di common language runtime (CLR) errori.</span><span class="sxs-lookup"><span data-stu-id="e0641-108">Provides a guarantee that certain rare race conditions that can cause fatal common language runtime (CLR) errors will never arise.</span></span>|  
|[<span data-ttu-id="e0641-109">SetProtectedCategories (metodo)</span><span class="sxs-lookup"><span data-stu-id="e0641-109">SetProtectedCategories Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-setprotectedcategories-method.md)|<span data-ttu-id="e0641-110">Specifica le categorie di tipi gestiti e i membri che devono essere bloccati dall'esecuzione di codice parzialmente attendibile.</span><span class="sxs-lookup"><span data-stu-id="e0641-110">Specifies the categories of managed types and members that should be blocked from running in partially trusted code.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="e0641-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="e0641-111">Requirements</span></span>  
 <span data-ttu-id="e0641-112">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e0641-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e0641-113">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="e0641-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e0641-114">**Libreria:** inclusa come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="e0641-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e0641-115">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e0641-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e0641-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e0641-116">See Also</span></span>  
 [<span data-ttu-id="e0641-117">EApiCategories (enumerazione)</span><span class="sxs-lookup"><span data-stu-id="e0641-117">EApiCategories Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eapicategories-enumeration.md)  
 [<span data-ttu-id="e0641-118">ICLRControl (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="e0641-118">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
