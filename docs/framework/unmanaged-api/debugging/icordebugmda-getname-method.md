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
ms.openlocfilehash: ca5d96e51c3809c6652d1a1fd75b80efb0b34222
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67761907"
---
# <a name="icordebugmdagetname-method"></a><span data-ttu-id="d88bd-102">Metodo ICorDebugMDA::GetName</span><span class="sxs-lookup"><span data-stu-id="d88bd-102">ICorDebugMDA::GetName Method</span></span>
<span data-ttu-id="d88bd-103">Ottiene una stringa contenente il nome dell'Assistente al debug gestito (MDA) rappresentato da [ICorDebugMDA](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-interface.md).</span><span class="sxs-lookup"><span data-stu-id="d88bd-103">Gets a string containing the name of the managed debugging assistant (MDA) represented by [ICorDebugMDA](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d88bd-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d88bd-104">Syntax</span></span>  
  
```cpp  
HRESULT GetName (  
    [in] ULONG32   cchName,  
    [out] ULONG32  *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)]  
        WCHAR      szName[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d88bd-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="d88bd-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="d88bd-106">[in] Dimensione della matrice `szName`.</span><span class="sxs-lookup"><span data-stu-id="d88bd-106">[in] The size of the `szName` array.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="d88bd-107">[out] Puntatore alla lunghezza del nome.</span><span class="sxs-lookup"><span data-stu-id="d88bd-107">[out] A pointer to the length of the name.</span></span>  
  
 `szName`  
 <span data-ttu-id="d88bd-108">[out] Matrice in cui archiviare il nome.</span><span class="sxs-lookup"><span data-stu-id="d88bd-108">[out] An array in which to store the name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d88bd-109">Note</span><span class="sxs-lookup"><span data-stu-id="d88bd-109">Remarks</span></span>  
 <span data-ttu-id="d88bd-110">I nomi di assistente al debug gestito sono valori univoci.</span><span class="sxs-lookup"><span data-stu-id="d88bd-110">MDA names are unique values.</span></span> <span data-ttu-id="d88bd-111">Il `GetName` metodo è un'alternativa con prestazioni utile per ottenere il flusso XML ed estrarre il nome dal flusso basato sullo schema.</span><span class="sxs-lookup"><span data-stu-id="d88bd-111">The `GetName` method is a convenient performance alternative to getting the XML stream and extracting the name from the stream based on the schema.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d88bd-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="d88bd-112">Requirements</span></span>  
 <span data-ttu-id="d88bd-113">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d88bd-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d88bd-114">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d88bd-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d88bd-115">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d88bd-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d88bd-116">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d88bd-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d88bd-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d88bd-117">See also</span></span>

- [<span data-ttu-id="d88bd-118">Interfaccia ICorDebugMDA</span><span class="sxs-lookup"><span data-stu-id="d88bd-118">ICorDebugMDA Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-interface.md)
- [<span data-ttu-id="d88bd-119">Diagnostica degli errori tramite gli assistenti al debug gestito</span><span class="sxs-lookup"><span data-stu-id="d88bd-119">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
