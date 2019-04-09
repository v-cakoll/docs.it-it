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
ms.openlocfilehash: fd096344c987d8901f0baab86e370abbb03528e5
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59177775"
---
# <a name="iclrhostprotectionmanager-interface"></a><span data-ttu-id="05e9e-102">Interfaccia ICLRHostProtectionManager</span><span class="sxs-lookup"><span data-stu-id="05e9e-102">ICLRHostProtectionManager Interface</span></span>
<span data-ttu-id="05e9e-103">Consente all'host bloccare le classi gestite specifiche, metodi, proprietà e campi dall'esecuzione di codice parzialmente attendibile.</span><span class="sxs-lookup"><span data-stu-id="05e9e-103">Enables the host to block specific managed classes, methods, properties, and fields from running in partially trusted code.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="05e9e-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="05e9e-104">Methods</span></span>  
  
|<span data-ttu-id="05e9e-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="05e9e-105">Method</span></span>|<span data-ttu-id="05e9e-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="05e9e-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="05e9e-107">SetEagerSerializeGrantSets</span><span class="sxs-lookup"><span data-stu-id="05e9e-107">SetEagerSerializeGrantSets</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-seteagerserializegrantsets-method.md)|<span data-ttu-id="05e9e-108">Fornisce una garanzia che determinati rara race condition che possono causare irreversibile common language runtime (CLR) errori si verificheranno mai.</span><span class="sxs-lookup"><span data-stu-id="05e9e-108">Provides a guarantee that certain rare race conditions that can cause fatal common language runtime (CLR) errors will never arise.</span></span>|  
|[<span data-ttu-id="05e9e-109">Metodo SetProtectedCategories</span><span class="sxs-lookup"><span data-stu-id="05e9e-109">SetProtectedCategories Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-setprotectedcategories-method.md)|<span data-ttu-id="05e9e-110">Specifica le categorie di tipi gestiti e membri che devono essere impediti l'esecuzione di codice parzialmente attendibile.</span><span class="sxs-lookup"><span data-stu-id="05e9e-110">Specifies the categories of managed types and members that should be blocked from running in partially trusted code.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="05e9e-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="05e9e-111">Requirements</span></span>  
 <span data-ttu-id="05e9e-112">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="05e9e-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="05e9e-113">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="05e9e-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="05e9e-114">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="05e9e-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="05e9e-115">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="05e9e-115">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="05e9e-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="05e9e-116">See also</span></span>

- [<span data-ttu-id="05e9e-117">Enumerazione EApiCategories</span><span class="sxs-lookup"><span data-stu-id="05e9e-117">EApiCategories Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eapicategories-enumeration.md)
- [<span data-ttu-id="05e9e-118">Interfaccia ICLRControl</span><span class="sxs-lookup"><span data-stu-id="05e9e-118">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
