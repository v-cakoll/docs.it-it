---
title: Metodo IAssemblyName::IsEqual
ms.date: 03/30/2017
api_name:
- IAssemblyName.IsEqual
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyName::IsEqual
helpviewer_keywords:
- IsEqual method [.NET Framework fusion]
- IAssemblyName::IsEqual method [.NET Framework fusion]
ms.assetid: 6dfc220f-d0d4-45b3-bfce-5829f817766f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 70784106798748eeaabd8e6b6c3787e27b0ece74
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54746674"
---
# <a name="iassemblynameisequal-method"></a><span data-ttu-id="9ca5c-102">Metodo IAssemblyName::IsEqual</span><span class="sxs-lookup"><span data-stu-id="9ca5c-102">IAssemblyName::IsEqual Method</span></span>
<span data-ttu-id="9ca5c-103">Determina se un oggetto specificato [IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md) è uguale all'oggetto `IAssemblyName`, in base al flag di confronto specificati.</span><span class="sxs-lookup"><span data-stu-id="9ca5c-103">Determines whether a specified [IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md) object is equal to this `IAssemblyName`, based on the specified comparison flags.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9ca5c-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9ca5c-104">Syntax</span></span>  
  
```  
HRESULT IsEqual (  
    [in] IAssemblyName  *pName,  
    [in] DWORD          dwCmpFlags  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9ca5c-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="9ca5c-105">Parameters</span></span>  
 `pName`  
 <span data-ttu-id="9ca5c-106">[in] Il `IAssemblyName` oggetto con cui confrontare questo `IAssemblyName`.</span><span class="sxs-lookup"><span data-stu-id="9ca5c-106">[in] The `IAssemblyName` object to which to compare this `IAssemblyName`.</span></span>  
  
 `dwCmpFlags`  
 <span data-ttu-id="9ca5c-107">[in] Una combinazione bit per bit di [ASM_CMP_FLAGS](../../../../docs/framework/unmanaged-api/fusion/asm-cmp-flags-enumeration.md) valori che influenzano il confronto.</span><span class="sxs-lookup"><span data-stu-id="9ca5c-107">[in] A bitwise combination of [ASM_CMP_FLAGS](../../../../docs/framework/unmanaged-api/fusion/asm-cmp-flags-enumeration.md) values that influence the comparison.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9ca5c-108">Requisiti</span><span class="sxs-lookup"><span data-stu-id="9ca5c-108">Requirements</span></span>  
 <span data-ttu-id="9ca5c-109">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9ca5c-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9ca5c-110">**Intestazione:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="9ca5c-110">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="9ca5c-111">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9ca5c-111">**NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9ca5c-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9ca5c-112">See also</span></span>
- [<span data-ttu-id="9ca5c-113">Interfaccia IAssemblyName</span><span class="sxs-lookup"><span data-stu-id="9ca5c-113">IAssemblyName Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md)
- [<span data-ttu-id="9ca5c-114">Enumerazioni Fusion</span><span class="sxs-lookup"><span data-stu-id="9ca5c-114">Fusion Enumerations</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-enumerations.md)
