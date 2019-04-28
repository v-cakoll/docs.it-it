---
title: Metodo ICorDebugCode2::GetCodeChunks
ms.date: 03/30/2017
api_name:
- ICorDebugCode2.GetCodeChunks
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode2::GetCodeChunks
helpviewer_keywords:
- GetCodeChunks method [.NET Framework debugging]
- ICorDebugCode2::GetCodeChunks method [.NET Framework debugging]
ms.assetid: 210a2f02-2678-4555-bc4a-78a0408764c8
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1428fc245d4f6993050c2753321684afee488c0e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61750150"
---
# <a name="icordebugcode2getcodechunks-method"></a><span data-ttu-id="83c73-102">Metodo ICorDebugCode2::GetCodeChunks</span><span class="sxs-lookup"><span data-stu-id="83c73-102">ICorDebugCode2::GetCodeChunks Method</span></span>
<span data-ttu-id="83c73-103">Ottiene i blocchi di codice che è costituito da questo oggetto di codice.</span><span class="sxs-lookup"><span data-stu-id="83c73-103">Gets the chunks of code that this code object is composed of.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="83c73-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="83c73-104">Syntax</span></span>  
  
```  
HRESULT GetCodeChunks (  
    [in]  ULONG32     cbufSize,  
    [out] ULONG32     *pcnumChunks,  
    [out, size_is(cbufSize), length_is(*pcnumChunks)]   
        CodeChunkInfo chunks[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="83c73-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="83c73-105">Parameters</span></span>  
 `cbufSize`  
 <span data-ttu-id="83c73-106">[in] Dimensioni del `chunks` matrice.</span><span class="sxs-lookup"><span data-stu-id="83c73-106">[in] Size of the `chunks` array.</span></span>  
  
 `pcnumChunks`  
 <span data-ttu-id="83c73-107">[out] Il numero di blocchi restituite nel `chunks` matrice.</span><span class="sxs-lookup"><span data-stu-id="83c73-107">[out] The number of chunks returned in the `chunks` array.</span></span>  
  
 `chunks`  
 <span data-ttu-id="83c73-108">[out] Matrice di strutture "CodeChunkInfo", ognuno dei quali rappresenta un singolo blocco di codice.</span><span class="sxs-lookup"><span data-stu-id="83c73-108">[out] An array of "CodeChunkInfo" structures, each of which represents a single chunk of code.</span></span> <span data-ttu-id="83c73-109">Se il valore di `cbufSize` è 0, questo parametro può essere null.</span><span class="sxs-lookup"><span data-stu-id="83c73-109">If the value of `cbufSize` is 0, this parameter can be null.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="83c73-110">Note</span><span class="sxs-lookup"><span data-stu-id="83c73-110">Remarks</span></span>  
 <span data-ttu-id="83c73-111">I blocchi di codice mai si sovrapporranno e gli utenti seguano l'ordine in cui sarebbe stato concatenati dai [ICorDebugCode](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getcode-method.md).</span><span class="sxs-lookup"><span data-stu-id="83c73-111">The code chunks will never overlap, and they will follow the order in which they would have been concatenated by [ICorDebugCode::GetCode](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getcode-method.md).</span></span> <span data-ttu-id="83c73-112">Un oggetto di codice Microsoft intermediate language (MSIL) in .NET Framework versione 2.0 includerà un solo blocco di codice.</span><span class="sxs-lookup"><span data-stu-id="83c73-112">A Microsoft intermediate language (MSIL) code object in the .NET Framework version 2.0 will comprise a single code chunk.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="83c73-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="83c73-113">Requirements</span></span>  
 <span data-ttu-id="83c73-114">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="83c73-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="83c73-115">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="83c73-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="83c73-116">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="83c73-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="83c73-117">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="83c73-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83c73-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="83c73-118">See also</span></span>
