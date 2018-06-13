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
ms.openlocfilehash: 977336f9ff5e65905018f7f93ade74e27625f514
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33430769"
---
# <a name="iassemblyenumgetnextassembly-method"></a><span data-ttu-id="595cc-102">Metodo IAssemblyEnum::GetNextAssembly</span><span class="sxs-lookup"><span data-stu-id="595cc-102">IAssemblyEnum::GetNextAssembly Method</span></span>
<span data-ttu-id="595cc-103">Ottiene un puntatore al successivo [IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md) contenuti in questo [IAssemblyEnum](../../../../docs/framework/unmanaged-api/fusion/iassemblyenum-interface.md) oggetto.</span><span class="sxs-lookup"><span data-stu-id="595cc-103">Gets a pointer to the next [IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md) contained in this [IAssemblyEnum](../../../../docs/framework/unmanaged-api/fusion/iassemblyenum-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="595cc-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="595cc-104">Syntax</span></span>  
  
```  
HRESULT GetNextAssembly (  
    [in]  LPVOID          pvReserved,  
    [out] IAssemblyName   **ppName,  
    [in]  DWORD           dwFlags  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="595cc-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="595cc-105">Parameters</span></span>  
 `pvReserved`  
 <span data-ttu-id="595cc-106">[in] Riservato per l'estensibilità futura.</span><span class="sxs-lookup"><span data-stu-id="595cc-106">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="595cc-107">`pvReserved` deve essere un riferimento null.</span><span class="sxs-lookup"><span data-stu-id="595cc-107">`pvReserved` must be a null reference.</span></span>  
  
 `ppName`  
 <span data-ttu-id="595cc-108">[out] L'oggetto restituito `IAssemblyName` puntatore.</span><span class="sxs-lookup"><span data-stu-id="595cc-108">[out] The returned `IAssemblyName` pointer.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="595cc-109">[in] Riservato per l'estensibilità futura.</span><span class="sxs-lookup"><span data-stu-id="595cc-109">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="595cc-110">`dwFlags` deve essere 0 (zero).</span><span class="sxs-lookup"><span data-stu-id="595cc-110">`dwFlags` must be 0 (zero).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="595cc-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="595cc-111">Requirements</span></span>  
 <span data-ttu-id="595cc-112">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="595cc-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="595cc-113">**Intestazione:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="595cc-113">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="595cc-114">**Versioni di .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="595cc-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="595cc-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="595cc-115">See Also</span></span>  
 [<span data-ttu-id="595cc-116">Interfaccia IAssemblyName</span><span class="sxs-lookup"><span data-stu-id="595cc-116">IAssemblyName Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md)  
 [<span data-ttu-id="595cc-117">Interfaccia IAssemblyEnum</span><span class="sxs-lookup"><span data-stu-id="595cc-117">IAssemblyEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyenum-interface.md)
