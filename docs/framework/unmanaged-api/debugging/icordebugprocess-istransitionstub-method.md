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
ms.openlocfilehash: ab2121605f974fdf3f9053214a4d29d8b0dd72db
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2020
ms.locfileid: "83211046"
---
# <a name="icordebugprocessistransitionstub-method"></a><span data-ttu-id="d8e2a-102">Metodo ICorDebugProcess::IsTransitionStub</span><span class="sxs-lookup"><span data-stu-id="d8e2a-102">ICorDebugProcess::IsTransitionStub Method</span></span>
<span data-ttu-id="d8e2a-103">Ottiene un valore che indica se un indirizzo si trova all'interno di uno stub che provocherà una transizione al codice gestito.</span><span class="sxs-lookup"><span data-stu-id="d8e2a-103">Gets a value that indicates whether an address is inside a stub that will cause a transition to managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d8e2a-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d8e2a-104">Syntax</span></span>  
  
```cpp  
HRESULT IsTransitionStub(  
    [in]  CORDB_ADDRESS address,  
    [out] BOOL *pbTransitionStub);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d8e2a-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="d8e2a-105">Parameters</span></span>  
 `address`  
 <span data-ttu-id="d8e2a-106">in `CORDB_ADDRESS`Valore che specifica l'indirizzo in questione.</span><span class="sxs-lookup"><span data-stu-id="d8e2a-106">[in] A `CORDB_ADDRESS` value that specifies the address in question.</span></span>  
  
 `pbTransitionStub`  
 <span data-ttu-id="d8e2a-107">out Puntatore a un valore booleano che è `true` se l'indirizzo specificato si trova all'interno di uno stub che provocherà una transizione al codice gestito; in caso contrario, \* `pbTransitionStub` è `false` .</span><span class="sxs-lookup"><span data-stu-id="d8e2a-107">[out] A pointer to a Boolean value that is `true` if the specified address is inside a stub that will cause a transition to managed code; otherwise \*`pbTransitionStub` is `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d8e2a-108">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="d8e2a-108">Remarks</span></span>  
 <span data-ttu-id="d8e2a-109">Il `IsTransitionStub` metodo può essere usato dal codice dell'istruzione non gestita per decidere quando restituire il controllo di avanzamento al gestore di debug gestito.</span><span class="sxs-lookup"><span data-stu-id="d8e2a-109">The `IsTransitionStub` method can be used by unmanaged stepping code to decide when to return stepping control to the managed stepper.</span></span>  
  
 <span data-ttu-id="d8e2a-110">È anche possibile identificare gli stub di transizione esaminando le informazioni nel file eseguibile di tipo PE.</span><span class="sxs-lookup"><span data-stu-id="d8e2a-110">You can also identity transition stubs by looking at information in the portable executable (PE) file.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d8e2a-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="d8e2a-111">Requirements</span></span>  
 <span data-ttu-id="d8e2a-112">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d8e2a-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d8e2a-113">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d8e2a-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d8e2a-114">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d8e2a-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d8e2a-115">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d8e2a-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
