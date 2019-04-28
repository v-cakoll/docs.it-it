---
title: Metodo ICorDebugProcess::IsTransitionStub
ms.date: 03/30/2017
api_name:
- ICorDebugProcess.IsTransitionStub
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess::IsTransitionStub
helpviewer_keywords:
- ICorDebugProcess::IsTransitionStub method [.NET Framework debugging]
- IsTransitionStub method [.NET Framework debugging]
ms.assetid: f7653317-7e48-4163-be03-f50f1a4b0f70
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 18084cb69d2c620fc892cc05e5a561e8fda3bc1c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61775518"
---
# <a name="icordebugprocessistransitionstub-method"></a><span data-ttu-id="4c28f-102">Metodo ICorDebugProcess::IsTransitionStub</span><span class="sxs-lookup"><span data-stu-id="4c28f-102">ICorDebugProcess::IsTransitionStub Method</span></span>
<span data-ttu-id="4c28f-103">Ottiene un valore che indica se un indirizzo è all'interno di uno stub che causa una transizione al codice gestito.</span><span class="sxs-lookup"><span data-stu-id="4c28f-103">Gets a value that indicates whether an address is inside a stub that will cause a transition to managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4c28f-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4c28f-104">Syntax</span></span>  
  
```  
HRESULT IsTransitionStub(  
    [in]  CORDB_ADDRESS address,  
    [out] BOOL *pbTransitionStub);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4c28f-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="4c28f-105">Parameters</span></span>  
 `address`  
 <span data-ttu-id="4c28f-106">[in] Oggetto `CORDB_ADDRESS` valore che specifica l'indirizzo in questione.</span><span class="sxs-lookup"><span data-stu-id="4c28f-106">[in] A `CORDB_ADDRESS` value that specifies the address in question.</span></span>  
  
 `pbTransitionStub`  
 <span data-ttu-id="4c28f-107">[out] Un puntatore a un valore booleano che è `true` se l'indirizzo specificato si trova all'interno di uno stub che causa una transizione al codice gestito; in caso contrario, \*`pbTransitionStub` è `false`.</span><span class="sxs-lookup"><span data-stu-id="4c28f-107">[out] A pointer to a Boolean value that is `true` if the specified address is inside a stub that will cause a transition to managed code; otherwise \*`pbTransitionStub` is `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4c28f-108">Note</span><span class="sxs-lookup"><span data-stu-id="4c28f-108">Remarks</span></span>  
 <span data-ttu-id="4c28f-109">Il `IsTransitionStub` metodo utilizzabile dal codice non gestito debug passo a passo per decidere quando restituire il controllo per il gestore gestito di istruzioni.</span><span class="sxs-lookup"><span data-stu-id="4c28f-109">The `IsTransitionStub` method can be used by unmanaged stepping code to decide when to return stepping control to the managed stepper.</span></span>  
  
 <span data-ttu-id="4c28f-110">È anche possibile stub transizione identità esaminando le informazioni contenute nel file eseguibile portabile (PE).</span><span class="sxs-lookup"><span data-stu-id="4c28f-110">You can also identity transition stubs by looking at information in the portable executable (PE) file.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4c28f-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="4c28f-111">Requirements</span></span>  
 <span data-ttu-id="4c28f-112">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4c28f-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4c28f-113">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4c28f-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4c28f-114">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4c28f-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4c28f-115">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4c28f-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
