---
title: Metodo IAssemblyName::GetProperty
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IAssemblyName.GetProperty
api_location: fusion.dll
api_type: COM
f1_keywords: IAssemblyName::GetProperty
helpviewer_keywords:
- IAssemblyName::GetProperty method [.NET Framework fusion]
- GetProperty method [.NET Framework fusion]
ms.assetid: e59fda62-77d5-4e37-89cb-ce7ae4627975
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 6eae7cf2d6dabe9bad4912d6a97249f52464fe65
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="iassemblynamegetproperty-method"></a><span data-ttu-id="58d48-102">Metodo IAssemblyName::GetProperty</span><span class="sxs-lookup"><span data-stu-id="58d48-102">IAssemblyName::GetProperty Method</span></span>
<span data-ttu-id="58d48-103">Ottiene un puntatore alla proprietà a cui fa riferimento l'identificatore della proprietà specificata.</span><span class="sxs-lookup"><span data-stu-id="58d48-103">Gets a pointer to the property referenced by the specified property identifier.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="58d48-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="58d48-104">Syntax</span></span>  
  
```  
HRESULT GetProperty (  
    [in]      DWORD    PropertyId,  
    [out]     LPVOID   pvProperty,  
    [in, out] LPDWORD  pcbProperty  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="58d48-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="58d48-105">Parameters</span></span>  
 `PropertyId`  
 <span data-ttu-id="58d48-106">[in] Identificatore univoco per la proprietà richiesta.</span><span class="sxs-lookup"><span data-stu-id="58d48-106">[in] The unique identifier for the requested property.</span></span>  
  
 `pvProperty`  
 <span data-ttu-id="58d48-107">[out] I dati restituiti della proprietà.</span><span class="sxs-lookup"><span data-stu-id="58d48-107">[out] The returned property data.</span></span>  
  
 `pcbProperty`  
 <span data-ttu-id="58d48-108">[in, out] Le dimensioni, in byte, di `pvProperty`.</span><span class="sxs-lookup"><span data-stu-id="58d48-108">[in, out] The size, in bytes, of `pvProperty`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="58d48-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="58d48-109">Requirements</span></span>  
 <span data-ttu-id="58d48-110">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="58d48-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="58d48-111">**Intestazione:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="58d48-111">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="58d48-112">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="58d48-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="58d48-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="58d48-113">See Also</span></span>  
 [<span data-ttu-id="58d48-114">IAssemblyName (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="58d48-114">IAssemblyName Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md)
