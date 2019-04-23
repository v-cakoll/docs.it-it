---
title: Metodo ICorDebugProcess6::GetCode
ms.date: 03/30/2017
ms.assetid: faa538c2-60c9-4064-b996-1b4c24ebd751
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7349a20da35eb0b87894440026a0974d49ae2aa0
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59097295"
---
# <a name="icordebugprocess6getcode-method"></a><span data-ttu-id="5fed3-102">Metodo ICorDebugProcess6::GetCode</span><span class="sxs-lookup"><span data-stu-id="5fed3-102">ICorDebugProcess6::GetCode Method</span></span>
<span data-ttu-id="5fed3-103">Ottiene informazioni sul codice gestito in un indirizzo di codice specifico.</span><span class="sxs-lookup"><span data-stu-id="5fed3-103">Gets information about the managed code at a particular code address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5fed3-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5fed3-104">Syntax</span></span>  
  
```  
HRESULT GetCode(  
    [in] CORDB_ADDRESS codeAddress,   
    [out] ICorDebugCode **ppCode);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5fed3-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="5fed3-105">Parameters</span></span>  
 `codeAddress`  
 <span data-ttu-id="5fed3-106">[in] Oggetto [CORDB_ADDRESS](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md) valore che specifica l'indirizzo iniziale del segmento di codice gestito.</span><span class="sxs-lookup"><span data-stu-id="5fed3-106">[in] A [CORDB_ADDRESS](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md) value that specifies the starting address of the managed code segment.</span></span>  
  
 `ppCode`  
 <span data-ttu-id="5fed3-107">[out] Un puntatore all'indirizzo di un oggetto "ICorDebugCode" che rappresenta un segmento di codice gestito.</span><span class="sxs-lookup"><span data-stu-id="5fed3-107">[out] A pointer to the address of an "ICorDebugCode" object that represents a segment of managed code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5fed3-108">Note</span><span class="sxs-lookup"><span data-stu-id="5fed3-108">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5fed3-109">Questo metodo è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="5fed3-109">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5fed3-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="5fed3-110">Requirements</span></span>  
 <span data-ttu-id="5fed3-111">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5fed3-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5fed3-112">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5fed3-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5fed3-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5fed3-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5fed3-114">**Versioni di .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5fed3-114">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5fed3-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5fed3-115">See also</span></span>

- [<span data-ttu-id="5fed3-116">Interfaccia ICorDebugProcess6</span><span class="sxs-lookup"><span data-stu-id="5fed3-116">ICorDebugProcess6 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-interface.md)
- [<span data-ttu-id="5fed3-117">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="5fed3-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
