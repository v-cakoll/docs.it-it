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
ms.openlocfilehash: 522ac2fd448abaaba48d4d5c20551e8029b35fd4
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793235"
---
# <a name="icordebugmdagetname-method"></a><span data-ttu-id="4c221-102">Metodo ICorDebugMDA::GetName</span><span class="sxs-lookup"><span data-stu-id="4c221-102">ICorDebugMDA::GetName Method</span></span>
<span data-ttu-id="4c221-103">Ottiene una stringa contenente il nome dell'assistente al debug gestito (MDA) rappresentato da [ICorDebugMDA](icordebugmda-interface.md).</span><span class="sxs-lookup"><span data-stu-id="4c221-103">Gets a string containing the name of the managed debugging assistant (MDA) represented by [ICorDebugMDA](icordebugmda-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4c221-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4c221-104">Syntax</span></span>  
  
```cpp  
HRESULT GetName (  
    [in] ULONG32   cchName,  
    [out] ULONG32  *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)]  
        WCHAR      szName[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4c221-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="4c221-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="4c221-106">[in] Dimensione della matrice `szName`.</span><span class="sxs-lookup"><span data-stu-id="4c221-106">[in] The size of the `szName` array.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="4c221-107">out Puntatore alla lunghezza del nome.</span><span class="sxs-lookup"><span data-stu-id="4c221-107">[out] A pointer to the length of the name.</span></span>  
  
 `szName`  
 <span data-ttu-id="4c221-108">out Matrice in cui archiviare il nome.</span><span class="sxs-lookup"><span data-stu-id="4c221-108">[out] An array in which to store the name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4c221-109">Note</span><span class="sxs-lookup"><span data-stu-id="4c221-109">Remarks</span></span>  
 <span data-ttu-id="4c221-110">I nomi dell'assistente al debug gestito sono valori univoci.</span><span class="sxs-lookup"><span data-stu-id="4c221-110">MDA names are unique values.</span></span> <span data-ttu-id="4c221-111">Il metodo `GetName` rappresenta una pratica alternativa alle prestazioni per ottenere il flusso XML ed estrarre il nome dal flusso in base allo schema.</span><span class="sxs-lookup"><span data-stu-id="4c221-111">The `GetName` method is a convenient performance alternative to getting the XML stream and extracting the name from the stream based on the schema.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4c221-112">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="4c221-112">Requirements</span></span>  
 <span data-ttu-id="4c221-113">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4c221-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4c221-114">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4c221-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4c221-115">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4c221-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4c221-116">**Versioni .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4c221-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4c221-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4c221-117">See also</span></span>

- [<span data-ttu-id="4c221-118">Interfaccia ICorDebugMDA</span><span class="sxs-lookup"><span data-stu-id="4c221-118">ICorDebugMDA Interface</span></span>](icordebugmda-interface.md)
- [<span data-ttu-id="4c221-119">Diagnostica degli errori tramite gli assistenti al debug gestito</span><span class="sxs-lookup"><span data-stu-id="4c221-119">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
