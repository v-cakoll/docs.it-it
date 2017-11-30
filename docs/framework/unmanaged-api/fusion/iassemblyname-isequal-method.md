---
title: Metodo IAssemblyName::IsEqual
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IAssemblyName.IsEqual
api_location: fusion.dll
api_type: COM
f1_keywords: IAssemblyName::IsEqual
helpviewer_keywords:
- IsEqual method [.NET Framework fusion]
- IAssemblyName::IsEqual method [.NET Framework fusion]
ms.assetid: 6dfc220f-d0d4-45b3-bfce-5829f817766f
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 51a4fbe005a8e270b9fe6767ae5173bd027a191b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="iassemblynameisequal-method"></a><span data-ttu-id="4d16b-102">Metodo IAssemblyName::IsEqual</span><span class="sxs-lookup"><span data-stu-id="4d16b-102">IAssemblyName::IsEqual Method</span></span>
<span data-ttu-id="4d16b-103">Determina se un oggetto [IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md) è uguale all'oggetto `IAssemblyName`, in base ai flag di confronto specificati.</span><span class="sxs-lookup"><span data-stu-id="4d16b-103">Determines whether a specified [IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md) object is equal to this `IAssemblyName`, based on the specified comparison flags.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4d16b-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4d16b-104">Syntax</span></span>  
  
```  
HRESULT IsEqual (  
    [in] IAssemblyName  *pName,  
    [in] DWORD          dwCmpFlags  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4d16b-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="4d16b-105">Parameters</span></span>  
 `pName`  
 <span data-ttu-id="4d16b-106">[in] Il `IAssemblyName` oggetto con cui confrontare questa `IAssemblyName`.</span><span class="sxs-lookup"><span data-stu-id="4d16b-106">[in] The `IAssemblyName` object to which to compare this `IAssemblyName`.</span></span>  
  
 `dwCmpFlags`  
 <span data-ttu-id="4d16b-107">[in] Combinazione bit per bit di [ASM_CMP_FLAGS](../../../../docs/framework/unmanaged-api/fusion/asm-cmp-flags-enumeration.md) valori che influenzano il confronto.</span><span class="sxs-lookup"><span data-stu-id="4d16b-107">[in] A bitwise combination of [ASM_CMP_FLAGS](../../../../docs/framework/unmanaged-api/fusion/asm-cmp-flags-enumeration.md) values that influence the comparison.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4d16b-108">Requisiti</span><span class="sxs-lookup"><span data-stu-id="4d16b-108">Requirements</span></span>  
 <span data-ttu-id="4d16b-109">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4d16b-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4d16b-110">**Intestazione:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="4d16b-110">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="4d16b-111">**Versioni di .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4d16b-111">**NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4d16b-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4d16b-112">See Also</span></span>  
 [<span data-ttu-id="4d16b-113">IAssemblyName (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="4d16b-113">IAssemblyName Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md)  
 [<span data-ttu-id="4d16b-114">Enumerazioni Fusion</span><span class="sxs-lookup"><span data-stu-id="4d16b-114">Fusion Enumerations</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-enumerations.md)
