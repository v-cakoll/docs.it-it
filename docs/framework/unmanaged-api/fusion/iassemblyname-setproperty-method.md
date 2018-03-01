---
title: Metodo IAssemblyName::SetProperty
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
- IAssemblyName.SetProperty
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyName::SetProperty
helpviewer_keywords:
- IAssemblyName::SetProperty method [.NET Framework fusion]
- SetProperty method [.NET Framework fusion]
ms.assetid: 496c3add-f60b-4073-943f-d1bcf33330cb
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 60ef27021ec3431c90086e0dfbae56bb6e6ccc86
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="iassemblynamesetproperty-method"></a><span data-ttu-id="a726c-102">Metodo IAssemblyName::SetProperty</span><span class="sxs-lookup"><span data-stu-id="a726c-102">IAssemblyName::SetProperty Method</span></span>
<span data-ttu-id="a726c-103">Imposta il valore della proprietà a cui fa riferimento l'identificatore della proprietà specificata.</span><span class="sxs-lookup"><span data-stu-id="a726c-103">Sets the value of the property referenced by the specified property identifier.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a726c-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a726c-104">Syntax</span></span>  
  
```  
HRESULT SetProperty (  
    [in] DWORD  PropertyId,  
    [in] LPVOID pvProperty,  
    [in] DWORD  cbProperty  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a726c-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="a726c-105">Parameters</span></span>  
 `PropertyId`  
 <span data-ttu-id="a726c-106">[in] Identificatore univoco della proprietà il cui valore verrà impostato.</span><span class="sxs-lookup"><span data-stu-id="a726c-106">[in] The unique identifier of the property whose value will be set.</span></span>  
  
 `pvProperty`  
 <span data-ttu-id="a726c-107">[in] Il valore su cui impostare la proprietà a cui fa riferimento `PropertyId`.</span><span class="sxs-lookup"><span data-stu-id="a726c-107">[in] The value to which to set the property referenced by `PropertyId`.</span></span>  
  
 `cbProperty`  
 <span data-ttu-id="a726c-108">[in] Le dimensioni, in byte, di `pvProperty`.</span><span class="sxs-lookup"><span data-stu-id="a726c-108">[in] The size, in bytes, of `pvProperty`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a726c-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="a726c-109">Requirements</span></span>  
 <span data-ttu-id="a726c-110">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a726c-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a726c-111">**Intestazione:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="a726c-111">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="a726c-112">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a726c-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a726c-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a726c-113">See Also</span></span>  
 [<span data-ttu-id="a726c-114">Interfaccia IAssemblyName</span><span class="sxs-lookup"><span data-stu-id="a726c-114">IAssemblyName Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md)
