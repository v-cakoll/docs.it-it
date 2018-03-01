---
title: Metodo ICorDebugAssembly::GetName
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorDebugAssembly.GetName
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAssembly::GetName
helpviewer_keywords:
- ICorDebugAssembly::GetName method [.NET Framework debugging]
- GetName method, ICorDebugAssembly interface [.NET Framework debugging]
ms.assetid: cdeda721-b214-4503-a291-c70b68b5f36b
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: cf2b84a6ab7cc1745fbf7330e66f94ea04635892
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugassemblygetname-method"></a><span data-ttu-id="7fa65-102">Metodo ICorDebugAssembly::GetName</span><span class="sxs-lookup"><span data-stu-id="7fa65-102">ICorDebugAssembly::GetName Method</span></span>
<span data-ttu-id="7fa65-103">Ottiene il nome dell'assembly che si `ICorDebugAssembly` istanza.</span><span class="sxs-lookup"><span data-stu-id="7fa65-103">Gets the name of the assembly that this `ICorDebugAssembly` instance represents.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7fa65-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7fa65-104">Syntax</span></span>  
  
```  
HRESULT GetName (  
    [in] ULONG32  cchName,  
    [out] ULONG32 *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)] WCHAR szName[]  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="7fa65-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="7fa65-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="7fa65-106">[in] Dimensione della matrice `szName`.</span><span class="sxs-lookup"><span data-stu-id="7fa65-106">[in] The size of the `szName` array.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="7fa65-107">[out] Un puntatore a un intero che specifica la lunghezza effettiva del nome.</span><span class="sxs-lookup"><span data-stu-id="7fa65-107">[out] A pointer to an integer that specifies the actual length of the name.</span></span>  
  
 `szName`  
 <span data-ttu-id="7fa65-108">[out] Matrice che archivia il nome.</span><span class="sxs-lookup"><span data-stu-id="7fa65-108">[out] An array that stores the name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7fa65-109">Note</span><span class="sxs-lookup"><span data-stu-id="7fa65-109">Remarks</span></span>  
 <span data-ttu-id="7fa65-110">Il `GetName` metodo restituisce il nome di file e percorso completo dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="7fa65-110">The `GetName` method returns the full path and file name of the assembly.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7fa65-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="7fa65-111">Requirements</span></span>  
 <span data-ttu-id="7fa65-112">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7fa65-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7fa65-113">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="7fa65-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7fa65-114">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7fa65-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7fa65-115">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7fa65-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
