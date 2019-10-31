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
ms.openlocfilehash: b27e7a2cdcbfc3a88a734230118d99c2dd5c700e
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73129532"
---
# <a name="icordebugmodulegetname-method"></a><span data-ttu-id="2bb0a-102">Metodo ICorDebugModule::GetName</span><span class="sxs-lookup"><span data-stu-id="2bb0a-102">ICorDebugModule::GetName Method</span></span>
<span data-ttu-id="2bb0a-103">Ottiene il nome file del modulo.</span><span class="sxs-lookup"><span data-stu-id="2bb0a-103">Gets the file name of the module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2bb0a-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2bb0a-104">Syntax</span></span>  
  
```cpp
HRESULT GetName(  
    [in] ULONG32 cchName,  
    [out] ULONG32 *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)] WCHAR szName[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2bb0a-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="2bb0a-105">Parameters</span></span>  
 `cchname`  
 <span data-ttu-id="2bb0a-106">[in] Dimensione della matrice `szName`.</span><span class="sxs-lookup"><span data-stu-id="2bb0a-106">[in] The size of the `szName` array.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="2bb0a-107">in Puntatore alla lunghezza del nome restituito.</span><span class="sxs-lookup"><span data-stu-id="2bb0a-107">[in] A pointer to the length of the returned name.</span></span>  
  
 `szName`  
 <span data-ttu-id="2bb0a-108">out Matrice che archivia il nome restituito.</span><span class="sxs-lookup"><span data-stu-id="2bb0a-108">[out] An array that stores the returned name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2bb0a-109">Note</span><span class="sxs-lookup"><span data-stu-id="2bb0a-109">Remarks</span></span>  
 <span data-ttu-id="2bb0a-110">Il metodo `GetName` restituisce un valore HRESULT S_OK se il nome file del modulo corrisponde al nome su disco.</span><span class="sxs-lookup"><span data-stu-id="2bb0a-110">The `GetName` method returns an S_OK HRESULT if the module's file name matches the name on disk.</span></span> <span data-ttu-id="2bb0a-111">`GetName` restituisce un valore HRESULT S_FALSE se il nome viene fabbricato, ad esempio per un modulo dinamico o in memoria.</span><span class="sxs-lookup"><span data-stu-id="2bb0a-111">`GetName` returns an S_FALSE HRESULT if the name is fabricated, such as for a dynamic or in-memory module.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2bb0a-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="2bb0a-112">Requirements</span></span>  
 <span data-ttu-id="2bb0a-113">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2bb0a-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2bb0a-114">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2bb0a-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2bb0a-115">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2bb0a-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2bb0a-116">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2bb0a-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2bb0a-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2bb0a-117">See also</span></span>
