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
ms.openlocfilehash: bef51fe9df0f85659603c637f11ed4e856c8e01a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133958"
---
# <a name="icordebugassembly2isfullytrusted-method"></a><span data-ttu-id="7eb90-102">Metodo ICorDebugAssembly2::IsFullyTrusted</span><span class="sxs-lookup"><span data-stu-id="7eb90-102">ICorDebugAssembly2::IsFullyTrusted Method</span></span>
<span data-ttu-id="7eb90-103">Ottiene un valore che indica se all'assembly è stata concessa l'attendibilità totale dal sistema di sicurezza del runtime.</span><span class="sxs-lookup"><span data-stu-id="7eb90-103">Gets a value that indicates whether the assembly has been granted full trust by the runtime security system.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7eb90-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7eb90-104">Syntax</span></span>  
  
```cpp  
HRESULT IsFullyTrusted(  
    [out] BOOL *pbFullyTrusted  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7eb90-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="7eb90-105">Parameters</span></span>  
 `pbFullyTrusted`  
 <span data-ttu-id="7eb90-106">[out] `true` se all'assembly è stata concessa l'attendibilità totale dal sistema di sicurezza di runtime; in caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="7eb90-106">[out] `true` if the assembly has been granted full trust by the runtime security system; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7eb90-107">Note</span><span class="sxs-lookup"><span data-stu-id="7eb90-107">Remarks</span></span>  
 <span data-ttu-id="7eb90-108">Questo metodo restituisce un valore HRESULT di CORDBG_E_NOTREADY se i criteri di sicurezza per l'assembly non sono stati ancora risolti, ovvero se non è stato ancora eseguito alcun codice nell'assembly.</span><span class="sxs-lookup"><span data-stu-id="7eb90-108">This method returns an HRESULT of CORDBG_E_NOTREADY if the security policy for the assembly has not yet been resolved, that is, if no code in the assembly has been run yet.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7eb90-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="7eb90-109">Requirements</span></span>  
 <span data-ttu-id="7eb90-110">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7eb90-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7eb90-111">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7eb90-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7eb90-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7eb90-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7eb90-113">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7eb90-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
