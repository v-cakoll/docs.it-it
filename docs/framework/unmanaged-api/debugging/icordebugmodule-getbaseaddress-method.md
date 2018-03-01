---
title: Metodo ICorDebugModule::GetBaseAddress
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
- ICorDebugModule.GetBaseAddress
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule::GetBaseAddress
helpviewer_keywords:
- GetBaseAddress method [.NET Framework debugging]
- ICorDebugModule::GetBaseAddress method [.NET Framework debugging]
ms.assetid: 26a82815-1982-4eb7-92d1-5c3d318d5be4
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: aca93086e5425d7579b1394f72b039938f519ca9
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugmodulegetbaseaddress-method"></a><span data-ttu-id="efe74-102">Metodo ICorDebugModule::GetBaseAddress</span><span class="sxs-lookup"><span data-stu-id="efe74-102">ICorDebugModule::GetBaseAddress Method</span></span>
<span data-ttu-id="efe74-103">Ottiene l'indirizzo di base del modulo.</span><span class="sxs-lookup"><span data-stu-id="efe74-103">Gets the base address of the module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="efe74-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="efe74-104">Syntax</span></span>  
  
```  
HRESULT GetBaseAddress(  
    [out] CORDB_ADDRESS *pAddress  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="efe74-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="efe74-105">Parameters</span></span>  
 `pAddress`  
 <span data-ttu-id="efe74-106">[out] Oggetto `CORDB_ADDRESS` che specifica l'indirizzo di base del modulo.</span><span class="sxs-lookup"><span data-stu-id="efe74-106">[out] A `CORDB_ADDRESS` that specifies the base address of the module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="efe74-107">Note</span><span class="sxs-lookup"><span data-stu-id="efe74-107">Remarks</span></span>  
 <span data-ttu-id="efe74-108">Se il modulo è nativo immagine (ovvero, se il modulo è stato generato dal generatore di immagini native, NGen.exe), il relativo indirizzo di base sarà zero.</span><span class="sxs-lookup"><span data-stu-id="efe74-108">If the module is a native image (that is, if the module was produced by the native image generator, NGen.exe), its base address will be zero.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="efe74-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="efe74-109">Requirements</span></span>  
 <span data-ttu-id="efe74-110">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="efe74-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="efe74-111">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="efe74-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="efe74-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="efe74-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="efe74-113">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="efe74-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="efe74-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="efe74-114">See Also</span></span>  
    
 
