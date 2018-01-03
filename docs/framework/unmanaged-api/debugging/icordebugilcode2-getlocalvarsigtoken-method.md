---
title: Metodo ICorDebugILCode2::GetLocalVarSigToken
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs: cpp
api_name: ICorDebugILCode2.GetLocalVarSigToken
api_location: mscordbi.dll
api_type: COM
ms.assetid: 17665b77-1342-4115-94fd-9f45b0ecfb0f
topic_type: apiref
caps.latest.revision: "3"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 47004375194438b1ef0aaf61144ba6f16278545b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugilcode2getlocalvarsigtoken-method"></a><span data-ttu-id="ea00e-102">Metodo ICorDebugILCode2::GetLocalVarSigToken</span><span class="sxs-lookup"><span data-stu-id="ea00e-102">ICorDebugILCode2::GetLocalVarSigToken Method</span></span>
<span data-ttu-id="ea00e-103">[Supportato in .NET Framework 4.5.2 e versioni successive]</span><span class="sxs-lookup"><span data-stu-id="ea00e-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="ea00e-104">Ottiene il token di metadati per la firma di una variabile locale della funzione rappresentata da questa istanza.</span><span class="sxs-lookup"><span data-stu-id="ea00e-104">Gets the metadata token for the local variable signature for the function that is represented by this instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ea00e-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ea00e-105">Syntax</span></span>  
  
```cpp
HRESULT GetLocalVarSigToken(  
   [out] mdSignature *pmdSig  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ea00e-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="ea00e-106">Parameters</span></span>  
 `pmdSig`  
 <span data-ttu-id="ea00e-107">[out] Puntatore al token `mdSignature` per la firma di una variabile locale di questa funzione o `mdSignatureNil` se non è presenta alcuna firma, ovvero se la funzione non contiene variabili locali.</span><span class="sxs-lookup"><span data-stu-id="ea00e-107">[out] A pointer to the `mdSignature` token for the local variable signature for this function, or `mdSignatureNil` if there is no signature (that is, if the function doesn't have any local variables).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ea00e-108">Note</span><span class="sxs-lookup"><span data-stu-id="ea00e-108">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ea00e-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ea00e-109">Requirements</span></span>  
 <span data-ttu-id="ea00e-110">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ea00e-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ea00e-111">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="ea00e-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ea00e-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ea00e-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ea00e-113">**Versioni di .NET framework:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ea00e-113">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ea00e-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ea00e-114">See Also</span></span>  
 [<span data-ttu-id="ea00e-115">Interfaccia ICorDebugILCode2</span><span class="sxs-lookup"><span data-stu-id="ea00e-115">ICorDebugILCode2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode2-interface.md)  
 [<span data-ttu-id="ea00e-116">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="ea00e-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
