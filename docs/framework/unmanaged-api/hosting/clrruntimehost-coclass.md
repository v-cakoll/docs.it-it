---
title: Coclasse CLRRuntimeHost
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CLRRuntimeHost Coclass
api_location: mscoree.dll
api_type: COM
f1_keywords: CLRRuntimeHost
helpviewer_keywords: CLRRuntimeHost coclass [.NET Framework hosting]
ms.assetid: 2ac9cbf5-8a2d-4e4f-8831-0dad8ef0a897
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 372b2466baaa76ba47a6710447d93f9fa6bb967f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="clrruntimehost-coclass"></a><span data-ttu-id="7cf52-102">Coclasse CLRRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="7cf52-102">CLRRuntimeHost Coclass</span></span>
<span data-ttu-id="7cf52-103">Fornisce interfacce per gestire l'esecuzione del codice dal runtime.</span><span class="sxs-lookup"><span data-stu-id="7cf52-103">Provides interfaces for managing code execution by the runtime.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7cf52-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7cf52-104">Syntax</span></span>  
  
```  
coclass CLRRuntimeHost {  
    [default] interface  ICLRRuntimeHost;  
    interface            ICLRValidator;  
};  
```  
  
## <a name="interfaces"></a><span data-ttu-id="7cf52-105">Interfacce</span><span class="sxs-lookup"><span data-stu-id="7cf52-105">Interfaces</span></span>  
  
|<span data-ttu-id="7cf52-106">Interfaccia</span><span class="sxs-lookup"><span data-stu-id="7cf52-106">Interface</span></span>|<span data-ttu-id="7cf52-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7cf52-107">Description</span></span>|  
|---------------|-----------------|  
|[<span data-ttu-id="7cf52-108">ICLRRuntimeHost (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="7cf52-108">ICLRRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)|<span data-ttu-id="7cf52-109">Fornisce metodi per controllare l'esecuzione di applicazioni dal runtime.</span><span class="sxs-lookup"><span data-stu-id="7cf52-109">Provides methods for controlling the execution of applications by the runtime.</span></span>|  
|[<span data-ttu-id="7cf52-110">ICLRValidator (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="7cf52-110">ICLRValidator Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrvalidator-interface.md)|<span data-ttu-id="7cf52-111">Fornisce metodi per la convalida delle immagini di tipo PE e per la creazione di report dettagliati di errori di convalida.</span><span class="sxs-lookup"><span data-stu-id="7cf52-111">Provides methods for validation of portable executable images and for detailed reporting of validation errors.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="7cf52-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="7cf52-112">Requirements</span></span>  
 <span data-ttu-id="7cf52-113">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7cf52-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7cf52-114">**Intestazione:** Mscoree</span><span class="sxs-lookup"><span data-stu-id="7cf52-114">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="7cf52-115">**Libreria:** inclusa come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="7cf52-115">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7cf52-116">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7cf52-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7cf52-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7cf52-117">See Also</span></span>  
 [<span data-ttu-id="7cf52-118">Coclassi di hosting</span><span class="sxs-lookup"><span data-stu-id="7cf52-118">Hosting Coclasses</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-coclasses.md)
