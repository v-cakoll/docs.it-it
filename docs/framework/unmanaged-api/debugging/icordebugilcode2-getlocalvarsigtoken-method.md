---
title: Metodo ICorDebugILCode2::GetLocalVarSigToken
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ICorDebugILCode2.GetLocalVarSigToken
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: 17665b77-1342-4115-94fd-9f45b0ecfb0f
topic_type:
- apiref
ms.openlocfilehash: 243000a2399b4938a3ad7f732c64e2f79b664f51
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73131052"
---
# <a name="icordebugilcode2getlocalvarsigtoken-method"></a><span data-ttu-id="2d3ec-102">Metodo ICorDebugILCode2::GetLocalVarSigToken</span><span class="sxs-lookup"><span data-stu-id="2d3ec-102">ICorDebugILCode2::GetLocalVarSigToken Method</span></span>
<span data-ttu-id="2d3ec-103">[Supportato in .NET Framework 4.5.2 e versioni successive]</span><span class="sxs-lookup"><span data-stu-id="2d3ec-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="2d3ec-104">Ottiene il token di metadati per la firma di una variabile locale della funzione rappresentata da questa istanza.</span><span class="sxs-lookup"><span data-stu-id="2d3ec-104">Gets the metadata token for the local variable signature for the function that is represented by this instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2d3ec-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2d3ec-105">Syntax</span></span>  
  
```cpp
HRESULT GetLocalVarSigToken(  
   [out] mdSignature *pmdSig  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2d3ec-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="2d3ec-106">Parameters</span></span>  
 `pmdSig`  
 <span data-ttu-id="2d3ec-107">[out] Puntatore al token `mdSignature` per la firma di una variabile locale di questa funzione o `mdSignatureNil` se non è presenta alcuna firma, ovvero se la funzione non contiene variabili locali.</span><span class="sxs-lookup"><span data-stu-id="2d3ec-107">[out] A pointer to the `mdSignature` token for the local variable signature for this function, or `mdSignatureNil` if there is no signature (that is, if the function doesn't have any local variables).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2d3ec-108">Note</span><span class="sxs-lookup"><span data-stu-id="2d3ec-108">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2d3ec-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="2d3ec-109">Requirements</span></span>  
 <span data-ttu-id="2d3ec-110">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2d3ec-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2d3ec-111">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2d3ec-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2d3ec-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2d3ec-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2d3ec-113">**Versioni di .NET Framework:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2d3ec-113">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2d3ec-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2d3ec-114">See also</span></span>

- [<span data-ttu-id="2d3ec-115">Interfaccia ICorDebugILCode2</span><span class="sxs-lookup"><span data-stu-id="2d3ec-115">ICorDebugILCode2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode2-interface.md)
- [<span data-ttu-id="2d3ec-116">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="2d3ec-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
