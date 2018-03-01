---
title: Metodo IAssemblyName::GetProperty
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
- IAssemblyName.GetProperty
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyName::GetProperty
helpviewer_keywords:
- IAssemblyName::GetProperty method [.NET Framework fusion]
- GetProperty method [.NET Framework fusion]
ms.assetid: e59fda62-77d5-4e37-89cb-ce7ae4627975
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 3311cc79cd010f59d707283fa555a2ebf66e53db
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="iassemblynamegetproperty-method"></a><span data-ttu-id="1b1ee-102">Metodo IAssemblyName::GetProperty</span><span class="sxs-lookup"><span data-stu-id="1b1ee-102">IAssemblyName::GetProperty Method</span></span>
<span data-ttu-id="1b1ee-103">Ottiene un puntatore alla proprietà a cui fa riferimento l'identificatore della proprietà specificata.</span><span class="sxs-lookup"><span data-stu-id="1b1ee-103">Gets a pointer to the property referenced by the specified property identifier.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1b1ee-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1b1ee-104">Syntax</span></span>  
  
```  
HRESULT GetProperty (  
    [in]      DWORD    PropertyId,  
    [out]     LPVOID   pvProperty,  
    [in, out] LPDWORD  pcbProperty  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="1b1ee-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="1b1ee-105">Parameters</span></span>  
 `PropertyId`  
 <span data-ttu-id="1b1ee-106">[in] Identificatore univoco per la proprietà richiesta.</span><span class="sxs-lookup"><span data-stu-id="1b1ee-106">[in] The unique identifier for the requested property.</span></span>  
  
 `pvProperty`  
 <span data-ttu-id="1b1ee-107">[out] I dati restituiti della proprietà.</span><span class="sxs-lookup"><span data-stu-id="1b1ee-107">[out] The returned property data.</span></span>  
  
 `pcbProperty`  
 <span data-ttu-id="1b1ee-108">[in, out] Le dimensioni, in byte, di `pvProperty`.</span><span class="sxs-lookup"><span data-stu-id="1b1ee-108">[in, out] The size, in bytes, of `pvProperty`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1b1ee-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="1b1ee-109">Requirements</span></span>  
 <span data-ttu-id="1b1ee-110">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1b1ee-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1b1ee-111">**Intestazione:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="1b1ee-111">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="1b1ee-112">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1b1ee-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1b1ee-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1b1ee-113">See Also</span></span>  
 [<span data-ttu-id="1b1ee-114">Interfaccia IAssemblyName</span><span class="sxs-lookup"><span data-stu-id="1b1ee-114">IAssemblyName Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md)
