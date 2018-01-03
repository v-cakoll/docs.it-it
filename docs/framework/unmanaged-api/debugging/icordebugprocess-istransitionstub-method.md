---
title: Metodo ICorDebugProcess::IsTransitionStub
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugProcess.IsTransitionStub
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugProcess::IsTransitionStub
helpviewer_keywords:
- ICorDebugProcess::IsTransitionStub method [.NET Framework debugging]
- IsTransitionStub method [.NET Framework debugging]
ms.assetid: f7653317-7e48-4163-be03-f50f1a4b0f70
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 9fe38cf5f53c2514b845238c1d52fa12df526fdd
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugprocessistransitionstub-method"></a><span data-ttu-id="89a56-102">Metodo ICorDebugProcess::IsTransitionStub</span><span class="sxs-lookup"><span data-stu-id="89a56-102">ICorDebugProcess::IsTransitionStub Method</span></span>
<span data-ttu-id="89a56-103">Ottiene un valore che indica se un indirizzo è all'interno di uno stub che causerà una transizione da codice gestito.</span><span class="sxs-lookup"><span data-stu-id="89a56-103">Gets a value that indicates whether an address is inside a stub that will cause a transition to managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="89a56-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="89a56-104">Syntax</span></span>  
  
```  
HRESULT IsTransitionStub(  
    [in]  CORDB_ADDRESS address,  
    [out] BOOL *pbTransitionStub);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="89a56-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="89a56-105">Parameters</span></span>  
 `address`  
 <span data-ttu-id="89a56-106">[in] Oggetto `CORDB_ADDRESS` valore che specifica l'indirizzo in questione.</span><span class="sxs-lookup"><span data-stu-id="89a56-106">[in] A `CORDB_ADDRESS` value that specifies the address in question.</span></span>  
  
 `pbTransitionStub`  
 <span data-ttu-id="89a56-107">[out] Un puntatore a un valore booleano che è `true` se l'indirizzo specificato si trova all'interno di uno stub che causerà una transizione a codice gestito; in caso contrario *`pbTransitionStub` è `false`.</span><span class="sxs-lookup"><span data-stu-id="89a56-107">[out] A pointer to a Boolean value that is `true` if the specified address is inside a stub that will cause a transition to managed code; otherwise *`pbTransitionStub` is `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="89a56-108">Note</span><span class="sxs-lookup"><span data-stu-id="89a56-108">Remarks</span></span>  
 <span data-ttu-id="89a56-109">Il `IsTransitionStub` metodo può essere usato da passo a passo il codice non gestito per decidere quando restituire il controllo per il gestore di istruzioni gestito.</span><span class="sxs-lookup"><span data-stu-id="89a56-109">The `IsTransitionStub` method can be used by unmanaged stepping code to decide when to return stepping control to the managed stepper.</span></span>  
  
 <span data-ttu-id="89a56-110">È possibile anche gli stub di transizione identità esaminando le informazioni contenute nel file eseguibile portabile (PE).</span><span class="sxs-lookup"><span data-stu-id="89a56-110">You can also identity transition stubs by looking at information in the portable executable (PE) file.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="89a56-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="89a56-111">Requirements</span></span>  
 <span data-ttu-id="89a56-112">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="89a56-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="89a56-113">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="89a56-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="89a56-114">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="89a56-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="89a56-115">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="89a56-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
