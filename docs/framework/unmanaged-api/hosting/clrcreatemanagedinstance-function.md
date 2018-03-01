---
title: Funzione ClrCreateManagedInstance
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
- ClrCreateManagedInstance
api_location:
- mscoree.dll
- clr.dll
- mscorwks.dll
- mscoreei.dll
api_type:
- DLLExport
f1_keywords:
- ClrCreateManagedInstance
helpviewer_keywords:
- ClrCreateManagedInstance function [.NET Framework hosting]
ms.assetid: 58ba42c0-4857-43bf-a039-73a4dc6544c2
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 64a1bc6bbd89e3a36ac53b322bb246a7e61baa67
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="clrcreatemanagedinstance-function"></a><span data-ttu-id="9430e-102">Funzione ClrCreateManagedInstance</span><span class="sxs-lookup"><span data-stu-id="9430e-102">ClrCreateManagedInstance Function</span></span>
<span data-ttu-id="9430e-103">Crea un'istanza del tipo gestito specificato.</span><span class="sxs-lookup"><span data-stu-id="9430e-103">Creates an instance of the specified managed type.</span></span>  
  
 <span data-ttu-id="9430e-104">Questa funzione è stata deprecata nel [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9430e-104">This function has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span> <span data-ttu-id="9430e-105">Utilizzare l'attivazione COM per creare un'istanza del tipo gestito o utilizzare l'hosting (vedere [CLR Hosting interfacce aggiunte in .NET Framework 4 e 4.5](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces-added-in-the-net-framework-4-and-4-5.md)).</span><span class="sxs-lookup"><span data-stu-id="9430e-105">Use COM activation to create an instance of the managed type, or use hosting (see [CLR Hosting Interfaces Added in the .NET Framework 4 and 4.5](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces-added-in-the-net-framework-4-and-4-5.md)).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9430e-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9430e-106">Syntax</span></span>  
  
```  
STDAPI ClrCreateManagedInstance (  
    [in]  LPCWSTR  pTypeName,   
    [in]  REFIID   riid,   
    [out] void     **ppObject  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9430e-107">Parametri</span><span class="sxs-lookup"><span data-stu-id="9430e-107">Parameters</span></span>  
 `pTypeName`  
 <span data-ttu-id="9430e-108">[in] Un puntatore al nome del tipo di istanza richiesto.</span><span class="sxs-lookup"><span data-stu-id="9430e-108">[in] A pointer to the name of the instance type being requested.</span></span>  
  
 `riid`  
 <span data-ttu-id="9430e-109">[in] Il `IID` del tipo di istanza richiesto.</span><span class="sxs-lookup"><span data-stu-id="9430e-109">[in] The `IID` of the instance type being requested.</span></span>  
  
 `ppObject`  
 <span data-ttu-id="9430e-110">[out] Un puntatore a un puntatore a un'istanza del tipo gestito che è stata richiesta dal chiamante.</span><span class="sxs-lookup"><span data-stu-id="9430e-110">[out] A pointer to a pointer to an instance of the managed type that was requested by the caller.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9430e-111">Note</span><span class="sxs-lookup"><span data-stu-id="9430e-111">Remarks</span></span>  
 <span data-ttu-id="9430e-112">Common language runtime deve già essere caricato in un processo.</span><span class="sxs-lookup"><span data-stu-id="9430e-112">The common language runtime should already be loaded into a process.</span></span> <span data-ttu-id="9430e-113">Ad esempio, può essere caricato tramite una chiamata al [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) funzione prima di `ClrCreateManagedInstance` funzione viene chiamata.</span><span class="sxs-lookup"><span data-stu-id="9430e-113">For example, it can be loaded by using a call to the [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) function before the `ClrCreateManagedInstance` function is called.</span></span> <span data-ttu-id="9430e-114">Se il runtime non è stato caricato, `ClrCreateManagedInstance` tenta innanzitutto di caricare v 1.0.3705 del runtime.</span><span class="sxs-lookup"><span data-stu-id="9430e-114">If the runtime is not loaded, `ClrCreateManagedInstance` first tries to load v1.0.3705 of the runtime.</span></span> <span data-ttu-id="9430e-115">Se il problema persiste, tenta di caricare la versione più recente del runtime.</span><span class="sxs-lookup"><span data-stu-id="9430e-115">If that fails, it attempts to load the latest version of the runtime.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9430e-116">Requisiti</span><span class="sxs-lookup"><span data-stu-id="9430e-116">Requirements</span></span>  
 <span data-ttu-id="9430e-117">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9430e-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9430e-118">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="9430e-118">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="9430e-119">**Libreria:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="9430e-119">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9430e-120">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9430e-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9430e-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9430e-121">See Also</span></span>  
 [<span data-ttu-id="9430e-122">Funzioni di hosting CLR deprecate</span><span class="sxs-lookup"><span data-stu-id="9430e-122">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)  
 [<span data-ttu-id="9430e-123">Hosting</span><span class="sxs-lookup"><span data-stu-id="9430e-123">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
