---
title: Interfaccia ICLRHostProtectionManager
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1d4cb310215967a79e43e43319e107b6c42551e6
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54557435"
---
# <a name="iclrhostprotectionmanager-interface"></a><span data-ttu-id="a19f6-102">Interfaccia ICLRHostProtectionManager</span><span class="sxs-lookup"><span data-stu-id="a19f6-102">ICLRHostProtectionManager Interface</span></span>
<span data-ttu-id="a19f6-103">Consente all'host bloccare le classi gestite specifiche, metodi, proprietà e campi dall'esecuzione di codice parzialmente attendibile.</span><span class="sxs-lookup"><span data-stu-id="a19f6-103">Enables the host to block specific managed classes, methods, properties, and fields from running in partially trusted code.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a19f6-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="a19f6-104">Methods</span></span>  
  
|<span data-ttu-id="a19f6-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="a19f6-105">Method</span></span>|<span data-ttu-id="a19f6-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a19f6-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a19f6-107">SetEagerSerializeGrantSets</span><span class="sxs-lookup"><span data-stu-id="a19f6-107">SetEagerSerializeGrantSets</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-seteagerserializegrantsets-method.md)|<span data-ttu-id="a19f6-108">Fornisce una garanzia che determinati rara race condition che possono causare irreversibile common language runtime (CLR) errori si verificheranno mai.</span><span class="sxs-lookup"><span data-stu-id="a19f6-108">Provides a guarantee that certain rare race conditions that can cause fatal common language runtime (CLR) errors will never arise.</span></span>|  
|[<span data-ttu-id="a19f6-109">Metodo SetProtectedCategories</span><span class="sxs-lookup"><span data-stu-id="a19f6-109">SetProtectedCategories Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-setprotectedcategories-method.md)|<span data-ttu-id="a19f6-110">Specifica le categorie di tipi gestiti e membri che devono essere impediti l'esecuzione di codice parzialmente attendibile.</span><span class="sxs-lookup"><span data-stu-id="a19f6-110">Specifies the categories of managed types and members that should be blocked from running in partially trusted code.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="a19f6-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="a19f6-111">Requirements</span></span>  
 <span data-ttu-id="a19f6-112">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a19f6-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a19f6-113">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="a19f6-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a19f6-114">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="a19f6-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a19f6-115">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a19f6-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a19f6-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a19f6-116">See also</span></span>
- [<span data-ttu-id="a19f6-117">Enumerazione EApiCategories</span><span class="sxs-lookup"><span data-stu-id="a19f6-117">EApiCategories Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eapicategories-enumeration.md)
- [<span data-ttu-id="a19f6-118">Interfaccia ICLRControl</span><span class="sxs-lookup"><span data-stu-id="a19f6-118">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
