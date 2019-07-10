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
ms.openlocfilehash: d231595ab2c7b41d1a24f654e9785b90b34ac780
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67744509"
---
# <a name="icordebugassembly2isfullytrusted-method"></a><span data-ttu-id="4d321-102">Metodo ICorDebugAssembly2::IsFullyTrusted</span><span class="sxs-lookup"><span data-stu-id="4d321-102">ICorDebugAssembly2::IsFullyTrusted Method</span></span>
<span data-ttu-id="4d321-103">Ottiene un valore che indica se l'assembly è stata concessa l'attendibilità totale da sistema di sicurezza di runtime.</span><span class="sxs-lookup"><span data-stu-id="4d321-103">Gets a value that indicates whether the assembly has been granted full trust by the runtime security system.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4d321-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4d321-104">Syntax</span></span>  
  
```cpp  
HRESULT IsFullyTrusted(  
    [out] BOOL *pbFullyTrusted  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4d321-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="4d321-105">Parameters</span></span>  
 `pbFullyTrusted`  
 <span data-ttu-id="4d321-106">[out] `true` se l'assembly è stata concessa l'attendibilità totale da sistema di sicurezza di runtime; in caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="4d321-106">[out] `true` if the assembly has been granted full trust by the runtime security system; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4d321-107">Note</span><span class="sxs-lookup"><span data-stu-id="4d321-107">Remarks</span></span>  
 <span data-ttu-id="4d321-108">Questo metodo restituisce un valore HRESULT di CORDBG_E_NOTREADY se i criteri di sicurezza per l'assembly non sono ancora stato risolto, vale a dire, se nessun codice nell'assembly è stato ancora eseguito.</span><span class="sxs-lookup"><span data-stu-id="4d321-108">This method returns an HRESULT of CORDBG_E_NOTREADY if the security policy for the assembly has not yet been resolved, that is, if no code in the assembly has been run yet.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4d321-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="4d321-109">Requirements</span></span>  
 <span data-ttu-id="4d321-110">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4d321-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4d321-111">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4d321-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4d321-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4d321-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4d321-113">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4d321-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
