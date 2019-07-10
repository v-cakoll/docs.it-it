---
title: Metodo IAssemblyName::SetProperty
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 40953d03904e3268770c8a1b6e212873ec66d2dd
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67761840"
---
# <a name="iassemblynamesetproperty-method"></a><span data-ttu-id="beec3-102">Metodo IAssemblyName::SetProperty</span><span class="sxs-lookup"><span data-stu-id="beec3-102">IAssemblyName::SetProperty Method</span></span>
<span data-ttu-id="beec3-103">Imposta il valore della proprietà fa riferimento l'identificatore della proprietà specificata.</span><span class="sxs-lookup"><span data-stu-id="beec3-103">Sets the value of the property referenced by the specified property identifier.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="beec3-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="beec3-104">Syntax</span></span>  
  
```cpp  
HRESULT SetProperty (  
    [in] DWORD  PropertyId,  
    [in] LPVOID pvProperty,  
    [in] DWORD  cbProperty  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="beec3-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="beec3-105">Parameters</span></span>  
 `PropertyId`  
 <span data-ttu-id="beec3-106">[in] Identificatore univoco della proprietà il cui valore verrà impostato.</span><span class="sxs-lookup"><span data-stu-id="beec3-106">[in] The unique identifier of the property whose value will be set.</span></span>  
  
 `pvProperty`  
 <span data-ttu-id="beec3-107">[in] Il valore su cui impostare la proprietà fa `PropertyId`.</span><span class="sxs-lookup"><span data-stu-id="beec3-107">[in] The value to which to set the property referenced by `PropertyId`.</span></span>  
  
 `cbProperty`  
 <span data-ttu-id="beec3-108">[in] Le dimensioni, in byte, di `pvProperty`.</span><span class="sxs-lookup"><span data-stu-id="beec3-108">[in] The size, in bytes, of `pvProperty`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="beec3-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="beec3-109">Requirements</span></span>  
 <span data-ttu-id="beec3-110">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="beec3-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="beec3-111">**Intestazione:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="beec3-111">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="beec3-112">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="beec3-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="beec3-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="beec3-113">See also</span></span>

- [<span data-ttu-id="beec3-114">Interfaccia IAssemblyName</span><span class="sxs-lookup"><span data-stu-id="beec3-114">IAssemblyName Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md)
