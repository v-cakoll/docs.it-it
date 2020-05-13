---
title: Metodo ICorDebugThread3::CreateStackWalk
ms.date: 03/30/2017
api_name:
- ICorDebugThread3.CreateStackWalk Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread3::CreateStackWalk
helpviewer_keywords:
- CreateStackWalk method [.NET Framework debugging]
- ICorDebugThread3::CreateStackWalk method [.NET Framework debugging]
ms.assetid: c55e35d9-f9aa-4268-94b5-dce44c61acf2
topic_type:
- apiref
ms.openlocfilehash: f2850e6c9cbb2250a08ab4a0e34c69e377d3a23d
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/13/2020
ms.locfileid: "83375845"
---
# <a name="icordebugthread3createstackwalk-method"></a><span data-ttu-id="4e910-102">Metodo ICorDebugThread3::CreateStackWalk</span><span class="sxs-lookup"><span data-stu-id="4e910-102">ICorDebugThread3::CreateStackWalk Method</span></span>
<span data-ttu-id="4e910-103">Crea un oggetto [ICorDebugStackWalk](icordebugstackwalk-interface.md) per il thread il cui stack si vuole rimuovere.</span><span class="sxs-lookup"><span data-stu-id="4e910-103">Creates an [ICorDebugStackWalk](icordebugstackwalk-interface.md) object for the thread whose stack you want to unwind.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4e910-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4e910-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateStackWalk([out] ICorDebugStackWalk **ppStackWalk);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4e910-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="4e910-105">Parameters</span></span>  
 `ppStackWalk`  
 <span data-ttu-id="4e910-106">out Puntatore all'indirizzo dell'oggetto [ICorDebugStackWalk](icordebugstackwalk-interface.md) per il thread di cui si desidera rimuovere lo stack.</span><span class="sxs-lookup"><span data-stu-id="4e910-106">[out] A pointer to address of the [ICorDebugStackWalk](icordebugstackwalk-interface.md) object for the thread whose stack you want to unwind.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4e910-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="4e910-107">Return Value</span></span>  
 <span data-ttu-id="4e910-108">Questo metodo restituisce gli specifici HRESULT seguenti, nonché gli errori di HRESULT che indicano la mancata riuscita del metodo.</span><span class="sxs-lookup"><span data-stu-id="4e910-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="4e910-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="4e910-109">HRESULT</span></span>|<span data-ttu-id="4e910-110">Description</span><span class="sxs-lookup"><span data-stu-id="4e910-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="4e910-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="4e910-111">S_OK</span></span>|<span data-ttu-id="4e910-112">`ICorDebugStackWalk`Creazione dell'oggetto completata.</span><span class="sxs-lookup"><span data-stu-id="4e910-112">The `ICorDebugStackWalk` object was successfully created.</span></span>|  
|<span data-ttu-id="4e910-113">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="4e910-113">E_FAIL</span></span>|<span data-ttu-id="4e910-114">L' `ICorDebugStackWalk` oggetto non è stato creato.</span><span class="sxs-lookup"><span data-stu-id="4e910-114">The `ICorDebugStackWalk` object was not created.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="4e910-115">Eccezioni</span><span class="sxs-lookup"><span data-stu-id="4e910-115">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4e910-116">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="4e910-116">Remarks</span></span>  
 <span data-ttu-id="4e910-117">Se il `CreateStackWalk` metodo ha esito positivo, il `ICorDebugStackWalk` contesto dell'oggetto restituito viene impostato sul contesto corrente del thread.</span><span class="sxs-lookup"><span data-stu-id="4e910-117">If the `CreateStackWalk` method succeeds, the returned `ICorDebugStackWalk` object's context is set to the thread's current context.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4e910-118">Requisiti</span><span class="sxs-lookup"><span data-stu-id="4e910-118">Requirements</span></span>  
 <span data-ttu-id="4e910-119">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4e910-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4e910-120">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4e910-120">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4e910-121">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4e910-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4e910-122">**Versioni .NET Framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4e910-122">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4e910-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4e910-123">See also</span></span>

- [<span data-ttu-id="4e910-124">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="4e910-124">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="4e910-125">Debug</span><span class="sxs-lookup"><span data-stu-id="4e910-125">Debugging</span></span>](index.md)
