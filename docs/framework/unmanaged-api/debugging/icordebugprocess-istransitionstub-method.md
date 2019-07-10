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
ms.openlocfilehash: 1ec29aa748c437199434fa1394e1a00c82154447
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67766882"
---
# <a name="icordebugprocessistransitionstub-method"></a><span data-ttu-id="b41b8-102">Metodo ICorDebugProcess::IsTransitionStub</span><span class="sxs-lookup"><span data-stu-id="b41b8-102">ICorDebugProcess::IsTransitionStub Method</span></span>
<span data-ttu-id="b41b8-103">Ottiene un valore che indica se un indirizzo è all'interno di uno stub che causa una transizione al codice gestito.</span><span class="sxs-lookup"><span data-stu-id="b41b8-103">Gets a value that indicates whether an address is inside a stub that will cause a transition to managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b41b8-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b41b8-104">Syntax</span></span>  
  
```cpp  
HRESULT IsTransitionStub(  
    [in]  CORDB_ADDRESS address,  
    [out] BOOL *pbTransitionStub);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b41b8-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="b41b8-105">Parameters</span></span>  
 `address`  
 <span data-ttu-id="b41b8-106">[in] Oggetto `CORDB_ADDRESS` valore che specifica l'indirizzo in questione.</span><span class="sxs-lookup"><span data-stu-id="b41b8-106">[in] A `CORDB_ADDRESS` value that specifies the address in question.</span></span>  
  
 `pbTransitionStub`  
 <span data-ttu-id="b41b8-107">[out] Un puntatore a un valore booleano che è `true` se l'indirizzo specificato si trova all'interno di uno stub che causa una transizione al codice gestito; in caso contrario, \*`pbTransitionStub` è `false`.</span><span class="sxs-lookup"><span data-stu-id="b41b8-107">[out] A pointer to a Boolean value that is `true` if the specified address is inside a stub that will cause a transition to managed code; otherwise \*`pbTransitionStub` is `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b41b8-108">Note</span><span class="sxs-lookup"><span data-stu-id="b41b8-108">Remarks</span></span>  
 <span data-ttu-id="b41b8-109">Il `IsTransitionStub` metodo utilizzabile dal codice non gestito debug passo a passo per decidere quando restituire il controllo per il gestore gestito di istruzioni.</span><span class="sxs-lookup"><span data-stu-id="b41b8-109">The `IsTransitionStub` method can be used by unmanaged stepping code to decide when to return stepping control to the managed stepper.</span></span>  
  
 <span data-ttu-id="b41b8-110">È anche possibile stub transizione identità esaminando le informazioni contenute nel file eseguibile portabile (PE).</span><span class="sxs-lookup"><span data-stu-id="b41b8-110">You can also identity transition stubs by looking at information in the portable executable (PE) file.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b41b8-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="b41b8-111">Requirements</span></span>  
 <span data-ttu-id="b41b8-112">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b41b8-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b41b8-113">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b41b8-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b41b8-114">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b41b8-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b41b8-115">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b41b8-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
