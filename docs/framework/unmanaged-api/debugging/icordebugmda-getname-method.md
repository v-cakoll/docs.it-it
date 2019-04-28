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
ms.openlocfilehash: 5f62fa23d30a93f863cb2be0fa060bd2eba8dca1
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61723056"
---
# <a name="icordebugmdagetname-method"></a><span data-ttu-id="5d34f-102">Metodo ICorDebugMDA::GetName</span><span class="sxs-lookup"><span data-stu-id="5d34f-102">ICorDebugMDA::GetName Method</span></span>
<span data-ttu-id="5d34f-103">Ottiene una stringa contenente il nome dell'Assistente al debug gestito (MDA) rappresentato da [ICorDebugMDA](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-interface.md).</span><span class="sxs-lookup"><span data-stu-id="5d34f-103">Gets a string containing the name of the managed debugging assistant (MDA) represented by [ICorDebugMDA](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5d34f-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5d34f-104">Syntax</span></span>  
  
```  
HRESULT GetName (  
    [in] ULONG32   cchName,  
    [out] ULONG32  *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)]  
        WCHAR      szName[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5d34f-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="5d34f-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="5d34f-106">[in] Dimensione della matrice `szName`.</span><span class="sxs-lookup"><span data-stu-id="5d34f-106">[in] The size of the `szName` array.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="5d34f-107">[out] Puntatore alla lunghezza del nome.</span><span class="sxs-lookup"><span data-stu-id="5d34f-107">[out] A pointer to the length of the name.</span></span>  
  
 `szName`  
 <span data-ttu-id="5d34f-108">[out] Matrice in cui archiviare il nome.</span><span class="sxs-lookup"><span data-stu-id="5d34f-108">[out] An array in which to store the name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5d34f-109">Note</span><span class="sxs-lookup"><span data-stu-id="5d34f-109">Remarks</span></span>  
 <span data-ttu-id="5d34f-110">I nomi di assistente al debug gestito sono valori univoci.</span><span class="sxs-lookup"><span data-stu-id="5d34f-110">MDA names are unique values.</span></span> <span data-ttu-id="5d34f-111">Il `GetName` metodo è un'alternativa con prestazioni utile per ottenere il flusso XML ed estrarre il nome dal flusso basato sullo schema.</span><span class="sxs-lookup"><span data-stu-id="5d34f-111">The `GetName` method is a convenient performance alternative to getting the XML stream and extracting the name from the stream based on the schema.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5d34f-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="5d34f-112">Requirements</span></span>  
 <span data-ttu-id="5d34f-113">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5d34f-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5d34f-114">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5d34f-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5d34f-115">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5d34f-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5d34f-116">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5d34f-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5d34f-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5d34f-117">See also</span></span>

- [<span data-ttu-id="5d34f-118">Interfaccia ICorDebugMDA</span><span class="sxs-lookup"><span data-stu-id="5d34f-118">ICorDebugMDA Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-interface.md)
- [<span data-ttu-id="5d34f-119">Diagnostica degli errori tramite gli assistenti al debug gestito</span><span class="sxs-lookup"><span data-stu-id="5d34f-119">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
