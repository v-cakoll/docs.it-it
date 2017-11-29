---
title: Metodo ICorDebugProcess6::GetCode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: faa538c2-60c9-4064-b996-1b4c24ebd751
caps.latest.revision: "5"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: c69ce290a486960978ddaf87203328df4f392b48
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugprocess6getcode-method"></a><span data-ttu-id="f359b-102">Metodo ICorDebugProcess6::GetCode</span><span class="sxs-lookup"><span data-stu-id="f359b-102">ICorDebugProcess6::GetCode Method</span></span>
<span data-ttu-id="f359b-103">Ottiene informazioni sul codice gestito in un indirizzo di codice specifico.</span><span class="sxs-lookup"><span data-stu-id="f359b-103">Gets information about the managed code at a particular code address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f359b-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f359b-104">Syntax</span></span>  
  
```  
HRESULT GetCode(  
    [in] CORDB_ADDRESS codeAddress,   
    [out] ICorDebugCode **ppCode);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f359b-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="f359b-105">Parameters</span></span>  
 `codeAddress`  
 <span data-ttu-id="f359b-106">[in] Oggetto [CORDB_ADDRESS](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md) valore che specifica l'indirizzo iniziale del segmento di codice gestito.</span><span class="sxs-lookup"><span data-stu-id="f359b-106">[in] A [CORDB_ADDRESS](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md) value that specifies the starting address of the managed code segment.</span></span>  
  
 `ppCode`  
 <span data-ttu-id="f359b-107">[out] Un puntatore all'indirizzo di un oggetto "ICorDebugCode" che rappresenta un segmento di codice gestito.</span><span class="sxs-lookup"><span data-stu-id="f359b-107">[out] A pointer to the address of an "ICorDebugCode" object that represents a segment of managed code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f359b-108">Note</span><span class="sxs-lookup"><span data-stu-id="f359b-108">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f359b-109">Questo metodo è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="f359b-109">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f359b-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f359b-110">Requirements</span></span>  
 <span data-ttu-id="f359b-111">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f359b-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f359b-112">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="f359b-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f359b-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f359b-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f359b-114">**Versioni di .NET framework:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f359b-114">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f359b-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f359b-115">See Also</span></span>  
 [<span data-ttu-id="f359b-116">Interfaccia ICorDebugProcess6</span><span class="sxs-lookup"><span data-stu-id="f359b-116">ICorDebugProcess6 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-interface.md)  
 [<span data-ttu-id="f359b-117">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="f359b-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
