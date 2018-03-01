---
title: Coclasse CLRRuntimeHost
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
- CLRRuntimeHost Coclass
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CLRRuntimeHost
helpviewer_keywords:
- CLRRuntimeHost coclass [.NET Framework hosting]
ms.assetid: 2ac9cbf5-8a2d-4e4f-8831-0dad8ef0a897
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 18e4518a2e321609a8add06c399ed9588748d1ae
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="clrruntimehost-coclass"></a><span data-ttu-id="4a8aa-102">Coclasse CLRRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="4a8aa-102">CLRRuntimeHost Coclass</span></span>
<span data-ttu-id="4a8aa-103">Fornisce interfacce per gestire l'esecuzione del codice dal runtime.</span><span class="sxs-lookup"><span data-stu-id="4a8aa-103">Provides interfaces for managing code execution by the runtime.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4a8aa-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4a8aa-104">Syntax</span></span>  
  
```  
coclass CLRRuntimeHost {  
    [default] interface  ICLRRuntimeHost;  
    interface            ICLRValidator;  
};  
```  
  
## <a name="interfaces"></a><span data-ttu-id="4a8aa-105">Interfacce</span><span class="sxs-lookup"><span data-stu-id="4a8aa-105">Interfaces</span></span>  
  
|<span data-ttu-id="4a8aa-106">Interfaccia</span><span class="sxs-lookup"><span data-stu-id="4a8aa-106">Interface</span></span>|<span data-ttu-id="4a8aa-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4a8aa-107">Description</span></span>|  
|---------------|-----------------|  
|[<span data-ttu-id="4a8aa-108">Interfaccia ICLRRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="4a8aa-108">ICLRRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)|<span data-ttu-id="4a8aa-109">Fornisce metodi per controllare l'esecuzione di applicazioni dal runtime.</span><span class="sxs-lookup"><span data-stu-id="4a8aa-109">Provides methods for controlling the execution of applications by the runtime.</span></span>|  
|[<span data-ttu-id="4a8aa-110">Interfaccia ICLRValidator</span><span class="sxs-lookup"><span data-stu-id="4a8aa-110">ICLRValidator Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrvalidator-interface.md)|<span data-ttu-id="4a8aa-111">Fornisce metodi per la convalida delle immagini di tipo PE e per la creazione di report dettagliati di errori di convalida.</span><span class="sxs-lookup"><span data-stu-id="4a8aa-111">Provides methods for validation of portable executable images and for detailed reporting of validation errors.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="4a8aa-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="4a8aa-112">Requirements</span></span>  
 <span data-ttu-id="4a8aa-113">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4a8aa-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4a8aa-114">**Intestazione:** Mscoree</span><span class="sxs-lookup"><span data-stu-id="4a8aa-114">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="4a8aa-115">**Libreria:** inclusa come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="4a8aa-115">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4a8aa-116">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4a8aa-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4a8aa-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4a8aa-117">See Also</span></span>  
 [<span data-ttu-id="4a8aa-118">Coclassi di hosting</span><span class="sxs-lookup"><span data-stu-id="4a8aa-118">Hosting Coclasses</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-coclasses.md)
