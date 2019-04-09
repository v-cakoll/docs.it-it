---
title: Metodo ICorDebugMDA::GetDescription
ms.date: 03/30/2017
api_name:
- ICorDebugMDA.GetDescription
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugMDA::GetDescription
helpviewer_keywords:
- GetDescription method [.NET Framework debugging]
- ICorDebugMDA::GetDescription method [.NET Framework debugging]
ms.assetid: 01d1b481-ca67-4712-8744-d342ec0df639
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 998d4baf03123f1ffc174b2a7aeed0ff4a25b001
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59133484"
---
# <a name="icordebugmdagetdescription-method"></a><span data-ttu-id="3d9b9-102">Metodo ICorDebugMDA::GetDescription</span><span class="sxs-lookup"><span data-stu-id="3d9b9-102">ICorDebugMDA::GetDescription Method</span></span>
<span data-ttu-id="3d9b9-103">Ottiene una stringa contenente la descrizione dell'Assistente al debug gestito (MDA) rappresentato da [ICorDebugMDA](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-interface.md).</span><span class="sxs-lookup"><span data-stu-id="3d9b9-103">Gets a string containing the description of the managed debugging assistant (MDA) represented by [ICorDebugMDA](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3d9b9-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3d9b9-104">Syntax</span></span>  
  
```  
HRESULT GetDescription (  
    [in] ULONG32   cchName,  
    [out] ULONG32  *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)]  
        WCHAR      szName[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3d9b9-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="3d9b9-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="3d9b9-106">[in] Le dimensioni del buffer di stringa in cui verrà archiviata la descrizione.</span><span class="sxs-lookup"><span data-stu-id="3d9b9-106">[in] The size of the string buffer that will store the description.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="3d9b9-107">[out] Puntatore al numero di byte restituiti nel buffer di stringa.</span><span class="sxs-lookup"><span data-stu-id="3d9b9-107">[out] A pointer to the number of bytes returned in the string buffer.</span></span>  
  
 `szName`  
 <span data-ttu-id="3d9b9-108">[out] Un buffer di stringa contenente la descrizione dell'Assistente al debug gestito.</span><span class="sxs-lookup"><span data-stu-id="3d9b9-108">[out] A string buffer containing the description of the MDA.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3d9b9-109">Note</span><span class="sxs-lookup"><span data-stu-id="3d9b9-109">Remarks</span></span>  
 <span data-ttu-id="3d9b9-110">La stringa può essere di lunghezza zero.</span><span class="sxs-lookup"><span data-stu-id="3d9b9-110">The string can be zero in length.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3d9b9-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="3d9b9-111">Requirements</span></span>  
 <span data-ttu-id="3d9b9-112">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3d9b9-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3d9b9-113">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3d9b9-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3d9b9-114">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3d9b9-114">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="3d9b9-115">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="3d9b9-115">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="3d9b9-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3d9b9-116">See also</span></span>

- [<span data-ttu-id="3d9b9-117">Interfaccia ICorDebugMDA</span><span class="sxs-lookup"><span data-stu-id="3d9b9-117">ICorDebugMDA Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-interface.md)
- [<span data-ttu-id="3d9b9-118">Diagnostica degli errori tramite gli assistenti al debug gestito</span><span class="sxs-lookup"><span data-stu-id="3d9b9-118">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
