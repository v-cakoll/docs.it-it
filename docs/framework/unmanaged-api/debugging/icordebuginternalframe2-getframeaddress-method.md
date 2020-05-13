---
title: Metodo ICorDebugInternalFrame2::GetFrameAddress
ms.date: 03/30/2017
api_name:
- ICorDebugInternalFrame2.GetFrameAddress Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugInternalFrame2::GetFrameAddress
helpviewer_keywords:
- GetFrameAddress method [.NET Framework debugging]
- ICorDebugInternalFrame2::GetFrameAddress method [.NET Framework debugging]
ms.assetid: 4ee8d058-ffc8-4967-9133-a5adfef4e518
topic_type:
- apiref
ms.openlocfilehash: 51c8f9a2b66d7b2553949056f7cdbedcf5ea37d6
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2020
ms.locfileid: "83209916"
---
# <a name="icordebuginternalframe2getframeaddress-method"></a><span data-ttu-id="45935-102">Metodo ICorDebugInternalFrame2::GetFrameAddress</span><span class="sxs-lookup"><span data-stu-id="45935-102">ICorDebugInternalFrame2::GetFrameAddress Method</span></span>
<span data-ttu-id="45935-103">Restituisce l'indirizzo dello stack del frame interno.</span><span class="sxs-lookup"><span data-stu-id="45935-103">Returns the stack address of the internal frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="45935-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="45935-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFrameAddress([out] CORDB_ADDRESS *pAddress);  
```  
  
## <a name="parameters"></a><span data-ttu-id="45935-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="45935-105">Parameters</span></span>  
 `pAddress`  
 <span data-ttu-id="45935-106">out Puntatore a `CORDB_ADDRESS` per il frame interno.</span><span class="sxs-lookup"><span data-stu-id="45935-106">[out] Pointer to the `CORDB_ADDRESS` for the internal frame.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="45935-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="45935-107">Return Value</span></span>  
 <span data-ttu-id="45935-108">Questo metodo restituisce gli specifici HRESULT seguenti, nonché gli errori di HRESULT che indicano la mancata riuscita del metodo.</span><span class="sxs-lookup"><span data-stu-id="45935-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="45935-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="45935-109">HRESULT</span></span>|<span data-ttu-id="45935-110">Description</span><span class="sxs-lookup"><span data-stu-id="45935-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="45935-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="45935-111">S_OK</span></span>|<span data-ttu-id="45935-112">L'indirizzo del frame interno è stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="45935-112">The address of the internal frame was successfully returned.</span></span>|  
|<span data-ttu-id="45935-113">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="45935-113">E_FAIL</span></span>|<span data-ttu-id="45935-114">Non è stato possibile restituire l'indirizzo del frame interno.</span><span class="sxs-lookup"><span data-stu-id="45935-114">The address of the internal frame could not be returned.</span></span>|  
|<span data-ttu-id="45935-115">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="45935-115">E_INVALIDARG</span></span>|<span data-ttu-id="45935-116">`pAddress` è `null`.</span><span class="sxs-lookup"><span data-stu-id="45935-116">`pAddress` is `null`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="45935-117">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="45935-117">Remarks</span></span>  
 <span data-ttu-id="45935-118">Il valore restituito in `pAddress` può essere utilizzato per determinare la posizione del frame interno rispetto ad altri frame nello stack.</span><span class="sxs-lookup"><span data-stu-id="45935-118">The value returned in `pAddress` can be used to determine the location of the internal frame relative to other frames on the stack.</span></span> <span data-ttu-id="45935-119">Anche nei computer basati su IA-64, il frame interno risiede solo nello stack e non esiste alcun puntatore corrispondente a un archivio di backup.</span><span class="sxs-lookup"><span data-stu-id="45935-119">Even on IA-64-based computers, the internal frame lives on the stack only, and there is no corresponding pointer to a backing store.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="45935-120">Requisiti</span><span class="sxs-lookup"><span data-stu-id="45935-120">Requirements</span></span>  
 <span data-ttu-id="45935-121">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="45935-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="45935-122">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="45935-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="45935-123">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="45935-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="45935-124">**Versioni .NET Framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="45935-124">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="45935-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="45935-125">See also</span></span>

- [<span data-ttu-id="45935-126">Interfaccia ICorDebugInternalFrame2</span><span class="sxs-lookup"><span data-stu-id="45935-126">ICorDebugInternalFrame2 Interface</span></span>](icordebuginternalframe2-interface.md)
- [<span data-ttu-id="45935-127">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="45935-127">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="45935-128">Debug</span><span class="sxs-lookup"><span data-stu-id="45935-128">Debugging</span></span>](index.md)
