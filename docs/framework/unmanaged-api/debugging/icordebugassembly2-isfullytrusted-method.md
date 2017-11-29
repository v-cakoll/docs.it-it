---
title: Metodo ICorDebugAssembly2::IsFullyTrusted
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugAssembly2.IsFullyTrusted
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugAssembly2::IsFullyTrusted
helpviewer_keywords:
- ICorDebugAssembly2::IsFullyTrusted method [.NET Framework debugging]
- IsFullyTrusted method [.NET Framework debugging]
ms.assetid: 26cbd27d-12bf-444a-8197-ccd14d37dda3
topic_type: apiref
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 19058308876f80afdbaec73583242aa8ad3c33cb
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugassembly2isfullytrusted-method"></a><span data-ttu-id="b5e1c-102">Metodo ICorDebugAssembly2::IsFullyTrusted</span><span class="sxs-lookup"><span data-stu-id="b5e1c-102">ICorDebugAssembly2::IsFullyTrusted Method</span></span>
<span data-ttu-id="b5e1c-103">Ottiene un valore che indica se l'assembly è stata concessa l'attendibilità totale per il sistema di sicurezza di runtime.</span><span class="sxs-lookup"><span data-stu-id="b5e1c-103">Gets a value that indicates whether the assembly has been granted full trust by the runtime security system.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b5e1c-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b5e1c-104">Syntax</span></span>  
  
```  
HRESULT IsFullyTrusted(  
    [out] BOOL *pbFullyTrusted  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b5e1c-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="b5e1c-105">Parameters</span></span>  
 `pbFullyTrusted`  
 <span data-ttu-id="b5e1c-106">[out] `true` se l'assembly è stata concessa l'attendibilità totale per il sistema di sicurezza runtime; in caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="b5e1c-106">[out] `true` if the assembly has been granted full trust by the runtime security system; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b5e1c-107">Note</span><span class="sxs-lookup"><span data-stu-id="b5e1c-107">Remarks</span></span>  
 <span data-ttu-id="b5e1c-108">Questo metodo restituisce un valore HRESULT di CORDBG_E_NOTREADY se i criteri di sicurezza per l'assembly non sono ancora stato risolto, vale a dire, se nessun codice nell'assembly è stato ancora eseguito.</span><span class="sxs-lookup"><span data-stu-id="b5e1c-108">This method returns an HRESULT of CORDBG_E_NOTREADY if the security policy for the assembly has not yet been resolved, that is, if no code in the assembly has been run yet.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b5e1c-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="b5e1c-109">Requirements</span></span>  
 <span data-ttu-id="b5e1c-110">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b5e1c-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b5e1c-111">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="b5e1c-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b5e1c-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b5e1c-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b5e1c-113">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b5e1c-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
