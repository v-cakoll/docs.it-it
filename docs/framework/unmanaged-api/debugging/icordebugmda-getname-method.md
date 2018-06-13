---
title: Metodo ICorDebugMDA::GetName
ms.date: 03/30/2017
api_name:
- ICorDebugMDA.GetName
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugMDA::GetName
helpviewer_keywords:
- ICorDebugMDA::GetName method [.NET Framework debugging]
- GetName method, ICorDebugMDA interface [.NET Framework debugging]
ms.assetid: 885bf5e8-00b7-4cd7-9d8d-e720d47918c4
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8c9f76f2c3b2ecf3ac5805dea8f8243f0b74ad48
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33417833"
---
# <a name="icordebugmdagetname-method"></a><span data-ttu-id="287c2-102">Metodo ICorDebugMDA::GetName</span><span class="sxs-lookup"><span data-stu-id="287c2-102">ICorDebugMDA::GetName Method</span></span>
<span data-ttu-id="287c2-103">Ottiene una stringa contenente il nome dell'Assistente al debug gestito (MDA) rappresentato da [ICorDebugMDA](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-interface.md).</span><span class="sxs-lookup"><span data-stu-id="287c2-103">Gets a string containing the name of the managed debugging assistant (MDA) represented by [ICorDebugMDA](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="287c2-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="287c2-104">Syntax</span></span>  
  
```  
HRESULT GetName (  
    [in] ULONG32   cchName,  
    [out] ULONG32  *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)]  
        WCHAR      szName[]  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="287c2-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="287c2-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="287c2-106">[in] Dimensione della matrice `szName`.</span><span class="sxs-lookup"><span data-stu-id="287c2-106">[in] The size of the `szName` array.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="287c2-107">[out] Puntatore alla lunghezza del nome.</span><span class="sxs-lookup"><span data-stu-id="287c2-107">[out] A pointer to the length of the name.</span></span>  
  
 `szName`  
 <span data-ttu-id="287c2-108">[out] Matrice in cui archiviare il nome.</span><span class="sxs-lookup"><span data-stu-id="287c2-108">[out] An array in which to store the name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="287c2-109">Note</span><span class="sxs-lookup"><span data-stu-id="287c2-109">Remarks</span></span>  
 <span data-ttu-id="287c2-110">I nomi di assistente al debug gestito sono valori univoci.</span><span class="sxs-lookup"><span data-stu-id="287c2-110">MDA names are unique values.</span></span> <span data-ttu-id="287c2-111">Il `GetName` metodo è un'alternativa di prestazioni ideale per ottenere il flusso XML ed estrarre il nome dal flusso in base allo schema.</span><span class="sxs-lookup"><span data-stu-id="287c2-111">The `GetName` method is a convenient performance alternative to getting the XML stream and extracting the name from the stream based on the schema.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="287c2-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="287c2-112">Requirements</span></span>  
 <span data-ttu-id="287c2-113">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="287c2-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="287c2-114">**Intestazione:** Cordebug. idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="287c2-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="287c2-115">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="287c2-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="287c2-116">**Versioni di .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="287c2-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="287c2-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="287c2-117">See Also</span></span>  
 [<span data-ttu-id="287c2-118">Interfaccia ICorDebugMDA</span><span class="sxs-lookup"><span data-stu-id="287c2-118">ICorDebugMDA Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-interface.md)  
 [<span data-ttu-id="287c2-119">Diagnostica degli errori tramite gli assistenti al debug gestito</span><span class="sxs-lookup"><span data-stu-id="287c2-119">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
