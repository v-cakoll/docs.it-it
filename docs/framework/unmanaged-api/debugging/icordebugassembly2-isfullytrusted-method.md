---
title: Metodo ICorDebugAssembly2::IsFullyTrusted
ms.date: 03/30/2017
api_name:
- ICorDebugAssembly2.IsFullyTrusted
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAssembly2::IsFullyTrusted
helpviewer_keywords:
- ICorDebugAssembly2::IsFullyTrusted method [.NET Framework debugging]
- IsFullyTrusted method [.NET Framework debugging]
ms.assetid: 26cbd27d-12bf-444a-8197-ccd14d37dda3
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 895c8bc7b550fd063a9215c60f10f183e24bac83
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33402952"
---
# <a name="icordebugassembly2isfullytrusted-method"></a><span data-ttu-id="ce8ac-102">Metodo ICorDebugAssembly2::IsFullyTrusted</span><span class="sxs-lookup"><span data-stu-id="ce8ac-102">ICorDebugAssembly2::IsFullyTrusted Method</span></span>
<span data-ttu-id="ce8ac-103">Ottiene un valore che indica se l'assembly è stata concessa l'attendibilità totale per il sistema di sicurezza di runtime.</span><span class="sxs-lookup"><span data-stu-id="ce8ac-103">Gets a value that indicates whether the assembly has been granted full trust by the runtime security system.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ce8ac-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ce8ac-104">Syntax</span></span>  
  
```  
HRESULT IsFullyTrusted(  
    [out] BOOL *pbFullyTrusted  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ce8ac-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="ce8ac-105">Parameters</span></span>  
 `pbFullyTrusted`  
 <span data-ttu-id="ce8ac-106">[out] `true` se l'assembly è stata concessa l'attendibilità totale per il sistema di sicurezza runtime; in caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="ce8ac-106">[out] `true` if the assembly has been granted full trust by the runtime security system; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ce8ac-107">Note</span><span class="sxs-lookup"><span data-stu-id="ce8ac-107">Remarks</span></span>  
 <span data-ttu-id="ce8ac-108">Questo metodo restituisce un valore HRESULT di CORDBG_E_NOTREADY se i criteri di sicurezza per l'assembly non sono ancora stato risolto, vale a dire, se nessun codice nell'assembly è stato ancora eseguito.</span><span class="sxs-lookup"><span data-stu-id="ce8ac-108">This method returns an HRESULT of CORDBG_E_NOTREADY if the security policy for the assembly has not yet been resolved, that is, if no code in the assembly has been run yet.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ce8ac-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ce8ac-109">Requirements</span></span>  
 <span data-ttu-id="ce8ac-110">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ce8ac-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ce8ac-111">**Intestazione:** Cordebug. idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="ce8ac-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ce8ac-112">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="ce8ac-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ce8ac-113">**Versioni di .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ce8ac-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
