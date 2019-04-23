---
title: Metodo ICorDebugModule::GetName
ms.date: 03/30/2017
api_name:
- ICorDebugModule.GetName
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule::GetName
helpviewer_keywords:
- ICorDebugModule::GetName method [.NET Framework debugging]
- GetName method, ICorDebugModule interface [.NET Framework debugging]
ms.assetid: db499637-7ba9-421e-b8b1-35856995e80b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b39467c067e50f2d553b35a41b0f783e0fc82156
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59176644"
---
# <a name="icordebugmodulegetname-method"></a><span data-ttu-id="21e2a-102">Metodo ICorDebugModule::GetName</span><span class="sxs-lookup"><span data-stu-id="21e2a-102">ICorDebugModule::GetName Method</span></span>
<span data-ttu-id="21e2a-103">Ottiene il nome del file del modulo.</span><span class="sxs-lookup"><span data-stu-id="21e2a-103">Gets the file name of the module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="21e2a-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="21e2a-104">Syntax</span></span>  
  
```  
HRESULT GetName(  
    [in] ULONG32 cchName,  
    [out] ULONG32 *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)] WCHAR szName[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="21e2a-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="21e2a-105">Parameters</span></span>  
 `cchname`  
 <span data-ttu-id="21e2a-106">[in] Dimensione della matrice `szName`.</span><span class="sxs-lookup"><span data-stu-id="21e2a-106">[in] The size of the `szName` array.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="21e2a-107">[in] Puntatore alla lunghezza del nome restituito.</span><span class="sxs-lookup"><span data-stu-id="21e2a-107">[in] A pointer to the length of the returned name.</span></span>  
  
 `szName`  
 <span data-ttu-id="21e2a-108">[out] Matrice che archivia il nome restituito.</span><span class="sxs-lookup"><span data-stu-id="21e2a-108">[out] An array that stores the returned name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="21e2a-109">Note</span><span class="sxs-lookup"><span data-stu-id="21e2a-109">Remarks</span></span>  
 <span data-ttu-id="21e2a-110">Il `GetName` metodo restituisce un HRESULT S_OK se il nome del modulo file corrisponda al nome del disco.</span><span class="sxs-lookup"><span data-stu-id="21e2a-110">The `GetName` method returns an S_OK HRESULT if the module's file name matches the name on disk.</span></span> <span data-ttu-id="21e2a-111">`GetName` Restituisce un HRESULT S_FALSE se il nome viene creato, ad esempio per un modulo dinamico o in memoria.</span><span class="sxs-lookup"><span data-stu-id="21e2a-111">`GetName` returns an S_FALSE HRESULT if the name is fabricated, such as for a dynamic or in-memory module.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="21e2a-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="21e2a-112">Requirements</span></span>  
 <span data-ttu-id="21e2a-113">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="21e2a-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="21e2a-114">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="21e2a-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="21e2a-115">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="21e2a-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="21e2a-116">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="21e2a-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="21e2a-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="21e2a-117">See also</span></span>
