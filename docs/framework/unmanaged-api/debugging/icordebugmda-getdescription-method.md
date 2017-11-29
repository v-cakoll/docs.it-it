---
title: Metodo ICorDebugMDA::GetDescription
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugMDA.GetDescription
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugMDA::GetDescription
helpviewer_keywords:
- GetDescription method [.NET Framework debugging]
- ICorDebugMDA::GetDescription method [.NET Framework debugging]
ms.assetid: 01d1b481-ca67-4712-8744-d342ec0df639
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 18ffd8ab92829404b1eadae33f067a1ea8391396
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugmdagetdescription-method"></a><span data-ttu-id="4f336-102">Metodo ICorDebugMDA::GetDescription</span><span class="sxs-lookup"><span data-stu-id="4f336-102">ICorDebugMDA::GetDescription Method</span></span>
<span data-ttu-id="4f336-103">Ottiene una stringa contenente la descrizione dell'Assistente al debug gestito (MDA) rappresentato da [ICorDebugMDA](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-interface.md).</span><span class="sxs-lookup"><span data-stu-id="4f336-103">Gets a string containing the description of the managed debugging assistant (MDA) represented by [ICorDebugMDA](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4f336-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4f336-104">Syntax</span></span>  
  
```  
HRESULT GetDescription (  
    [in] ULONG32   cchName,  
    [out] ULONG32  *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)]  
        WCHAR      szName[]  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4f336-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="4f336-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="4f336-106">[in] Le dimensioni del buffer di stringa in cui verrà archiviata la descrizione.</span><span class="sxs-lookup"><span data-stu-id="4f336-106">[in] The size of the string buffer that will store the description.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="4f336-107">[out] Puntatore al numero di byte restituiti nel buffer di stringa.</span><span class="sxs-lookup"><span data-stu-id="4f336-107">[out] A pointer to the number of bytes returned in the string buffer.</span></span>  
  
 `szName`  
 <span data-ttu-id="4f336-108">[out] Un buffer di stringa contenente la descrizione dell'Assistente al debug gestito.</span><span class="sxs-lookup"><span data-stu-id="4f336-108">[out] A string buffer containing the description of the MDA.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4f336-109">Note</span><span class="sxs-lookup"><span data-stu-id="4f336-109">Remarks</span></span>  
 <span data-ttu-id="4f336-110">La stringa può essere di lunghezza zero.</span><span class="sxs-lookup"><span data-stu-id="4f336-110">The string can be zero in length.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4f336-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="4f336-111">Requirements</span></span>  
 <span data-ttu-id="4f336-112">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4f336-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4f336-113">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="4f336-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4f336-114">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4f336-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4f336-115">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4f336-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4f336-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4f336-116">See Also</span></span>  
 [<span data-ttu-id="4f336-117">ICorDebugMDA (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="4f336-117">ICorDebugMDA Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-interface.md)  
 [<span data-ttu-id="4f336-118">Diagnostica degli errori tramite gli assistenti al debug gestito</span><span class="sxs-lookup"><span data-stu-id="4f336-118">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
