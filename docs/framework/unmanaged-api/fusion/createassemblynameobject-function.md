---
title: Funzione CreateAssemblyNameObject
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
- CreateAssemblyNameObject
api_location:
- fusion.dll
- clr.dll
- mscorwks.dll
api_type:
- DLLExport
f1_keywords:
- CreateAssemblyNameObject
helpviewer_keywords:
- CreateAssemblyNameObject function [.NET Framework fusion]
ms.assetid: 55c8b41e-fbe4-4ae0-aa29-68fbb2311691
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 2d2616bd7aee878ebbc1d196cb1ac5f90ae7bd04
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="createassemblynameobject-function"></a><span data-ttu-id="7fa1d-102">Funzione CreateAssemblyNameObject</span><span class="sxs-lookup"><span data-stu-id="7fa1d-102">CreateAssemblyNameObject Function</span></span>
<span data-ttu-id="7fa1d-103">Ottiene un puntatore a interfaccia a un [IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md) istanza che rappresenta l'identità univoca dell'assembly con il nome specificato.</span><span class="sxs-lookup"><span data-stu-id="7fa1d-103">Gets an interface pointer to an [IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md) instance that represents the unique identity of the assembly with the specified name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7fa1d-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7fa1d-104">Syntax</span></span>  
  
```  
HRESULT CreateAssemblyNameObject (  
    [out] LPASSEMBLYNAME  *ppAssemblyNameObj,  
    [in]  LPCWSTR         szAssemblyName,  
    [in]  DWORD           dwFlags,  
    [in]  LPVOID          pvReserved  
 );  
```  
  
#### <a name="parameters"></a><span data-ttu-id="7fa1d-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="7fa1d-105">Parameters</span></span>  
 `ppAssemblyNameObj`  
 <span data-ttu-id="7fa1d-106">[out] L'oggetto restituito `IAssemblyName`.</span><span class="sxs-lookup"><span data-stu-id="7fa1d-106">[out] The returned `IAssemblyName`.</span></span>  
  
 `szAssemblyName`  
 <span data-ttu-id="7fa1d-107">[in] Il nome dell'assembly per cui creare il nuovo `IAssemblyName` istanza.</span><span class="sxs-lookup"><span data-stu-id="7fa1d-107">[in] The name of the assembly for which to create the new `IAssemblyName` instance.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="7fa1d-108">[in] Flag da passare al costruttore dell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="7fa1d-108">[in] Flags to pass to the object constructor.</span></span>  
  
 `pvReserved`  
 <span data-ttu-id="7fa1d-109">[in] Riservato per l'estensibilità futura.</span><span class="sxs-lookup"><span data-stu-id="7fa1d-109">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="7fa1d-110">`pvReserved`deve essere un riferimento null.</span><span class="sxs-lookup"><span data-stu-id="7fa1d-110">`pvReserved` must be a null reference.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7fa1d-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="7fa1d-111">Requirements</span></span>  
 <span data-ttu-id="7fa1d-112">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7fa1d-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7fa1d-113">**Intestazione:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="7fa1d-113">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="7fa1d-114">**Libreria:** inclusa come risorsa in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="7fa1d-114">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="7fa1d-115">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7fa1d-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7fa1d-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7fa1d-116">See Also</span></span>  
 [<span data-ttu-id="7fa1d-117">Interfaccia IAssemblyName</span><span class="sxs-lookup"><span data-stu-id="7fa1d-117">IAssemblyName Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md)  
 [<span data-ttu-id="7fa1d-118">Funzioni statiche globali Fusion</span><span class="sxs-lookup"><span data-stu-id="7fa1d-118">Fusion Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)
