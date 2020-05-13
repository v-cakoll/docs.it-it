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
ms.openlocfilehash: 6a6769265a2e140f1fa001bb8240bc5d4bd76018
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2020
ms.locfileid: "83213673"
---
# <a name="icordebugmdagetname-method"></a><span data-ttu-id="dd676-102">Metodo ICorDebugMDA::GetName</span><span class="sxs-lookup"><span data-stu-id="dd676-102">ICorDebugMDA::GetName Method</span></span>
<span data-ttu-id="dd676-103">Ottiene una stringa contenente il nome dell'assistente al debug gestito (MDA) rappresentato da [ICorDebugMDA](icordebugmda-interface.md).</span><span class="sxs-lookup"><span data-stu-id="dd676-103">Gets a string containing the name of the managed debugging assistant (MDA) represented by [ICorDebugMDA](icordebugmda-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dd676-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="dd676-104">Syntax</span></span>  
  
```cpp  
HRESULT GetName (  
    [in] ULONG32   cchName,  
    [out] ULONG32  *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)]  
        WCHAR      szName[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="dd676-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="dd676-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="dd676-106">[in] Dimensione della matrice `szName`.</span><span class="sxs-lookup"><span data-stu-id="dd676-106">[in] The size of the `szName` array.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="dd676-107">out Puntatore alla lunghezza del nome.</span><span class="sxs-lookup"><span data-stu-id="dd676-107">[out] A pointer to the length of the name.</span></span>  
  
 `szName`  
 <span data-ttu-id="dd676-108">out Matrice in cui archiviare il nome.</span><span class="sxs-lookup"><span data-stu-id="dd676-108">[out] An array in which to store the name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="dd676-109">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="dd676-109">Remarks</span></span>  
 <span data-ttu-id="dd676-110">I nomi dell'assistente al debug gestito sono valori univoci.</span><span class="sxs-lookup"><span data-stu-id="dd676-110">MDA names are unique values.</span></span> <span data-ttu-id="dd676-111">Il `GetName` metodo rappresenta una pratica alternativa alle prestazioni per ottenere il flusso XML ed estrarre il nome dal flusso in base allo schema.</span><span class="sxs-lookup"><span data-stu-id="dd676-111">The `GetName` method is a convenient performance alternative to getting the XML stream and extracting the name from the stream based on the schema.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dd676-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="dd676-112">Requirements</span></span>  
 <span data-ttu-id="dd676-113">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dd676-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dd676-114">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="dd676-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="dd676-115">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="dd676-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="dd676-116">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dd676-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dd676-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="dd676-117">See also</span></span>

- [<span data-ttu-id="dd676-118">Interfaccia ICorDebugMDA</span><span class="sxs-lookup"><span data-stu-id="dd676-118">ICorDebugMDA Interface</span></span>](icordebugmda-interface.md)
- [<span data-ttu-id="dd676-119">Diagnostica degli errori tramite gli assistenti al debug gestito</span><span class="sxs-lookup"><span data-stu-id="dd676-119">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
