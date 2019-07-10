---
title: Metodo IAssemblyEnum::GetNextAssembly
ms.date: 03/30/2017
api_name:
- IAssemblyEnum.GetNextAssembly
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyEnum::GetNextAssembly
helpviewer_keywords:
- GetNextAssembly method [.NET Framework fusion]
- IAssemblyEnum::GetNextAssembly method [.NET Framework fusion]
ms.assetid: 5d7a4ca2-5f46-4ef1-a9a2-257884e9dc11
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 57d64096ea693be41359aef63c04674ca77769c6
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67760971"
---
# <a name="iassemblyenumgetnextassembly-method"></a><span data-ttu-id="7e79d-102">Metodo IAssemblyEnum::GetNextAssembly</span><span class="sxs-lookup"><span data-stu-id="7e79d-102">IAssemblyEnum::GetNextAssembly Method</span></span>
<span data-ttu-id="7e79d-103">Ottiene un puntatore al successivo [IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md) contenute in questo [IAssemblyEnum](../../../../docs/framework/unmanaged-api/fusion/iassemblyenum-interface.md) oggetto.</span><span class="sxs-lookup"><span data-stu-id="7e79d-103">Gets a pointer to the next [IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md) contained in this [IAssemblyEnum](../../../../docs/framework/unmanaged-api/fusion/iassemblyenum-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7e79d-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7e79d-104">Syntax</span></span>  
  
```cpp  
HRESULT GetNextAssembly (  
    [in]  LPVOID          pvReserved,  
    [out] IAssemblyName   **ppName,  
    [in]  DWORD           dwFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7e79d-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="7e79d-105">Parameters</span></span>  
 `pvReserved`  
 <span data-ttu-id="7e79d-106">[in] Riservato per un'estendibilità futura.</span><span class="sxs-lookup"><span data-stu-id="7e79d-106">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="7e79d-107">`pvReserved` deve essere un riferimento null.</span><span class="sxs-lookup"><span data-stu-id="7e79d-107">`pvReserved` must be a null reference.</span></span>  
  
 `ppName`  
 <span data-ttu-id="7e79d-108">[out] L'oggetto restituito `IAssemblyName` puntatore.</span><span class="sxs-lookup"><span data-stu-id="7e79d-108">[out] The returned `IAssemblyName` pointer.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="7e79d-109">[in] Riservato per un'estendibilità futura.</span><span class="sxs-lookup"><span data-stu-id="7e79d-109">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="7e79d-110">`dwFlags` deve essere 0 (zero).</span><span class="sxs-lookup"><span data-stu-id="7e79d-110">`dwFlags` must be 0 (zero).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7e79d-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="7e79d-111">Requirements</span></span>  
 <span data-ttu-id="7e79d-112">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7e79d-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7e79d-113">**Intestazione:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="7e79d-113">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="7e79d-114">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7e79d-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7e79d-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7e79d-115">See also</span></span>

- [<span data-ttu-id="7e79d-116">Interfaccia IAssemblyName</span><span class="sxs-lookup"><span data-stu-id="7e79d-116">IAssemblyName Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md)
- [<span data-ttu-id="7e79d-117">Interfaccia IAssemblyEnum</span><span class="sxs-lookup"><span data-stu-id="7e79d-117">IAssemblyEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyenum-interface.md)
