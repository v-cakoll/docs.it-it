---
title: Metodo ICorDebugAssembly::GetName
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3077e0494816a083d97839d66d06b18130e5dac8
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61645578"
---
# <a name="icordebugassemblygetname-method"></a><span data-ttu-id="1b4b0-102">Metodo ICorDebugAssembly::GetName</span><span class="sxs-lookup"><span data-stu-id="1b4b0-102">ICorDebugAssembly::GetName Method</span></span>
<span data-ttu-id="1b4b0-103">Ottiene il nome dell'assembly a cui questo `ICorDebugAssembly` istanza rappresenta.</span><span class="sxs-lookup"><span data-stu-id="1b4b0-103">Gets the name of the assembly that this `ICorDebugAssembly` instance represents.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1b4b0-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1b4b0-104">Syntax</span></span>  
  
```  
HRESULT GetName (  
    [in] ULONG32  cchName,  
    [out] ULONG32 *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)] WCHAR szName[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1b4b0-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="1b4b0-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="1b4b0-106">[in] Dimensione della matrice `szName`.</span><span class="sxs-lookup"><span data-stu-id="1b4b0-106">[in] The size of the `szName` array.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="1b4b0-107">[out] Un puntatore a un intero che specifica la lunghezza effettiva del nome.</span><span class="sxs-lookup"><span data-stu-id="1b4b0-107">[out] A pointer to an integer that specifies the actual length of the name.</span></span>  
  
 `szName`  
 <span data-ttu-id="1b4b0-108">[out] Matrice che archivia il nome.</span><span class="sxs-lookup"><span data-stu-id="1b4b0-108">[out] An array that stores the name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1b4b0-109">Note</span><span class="sxs-lookup"><span data-stu-id="1b4b0-109">Remarks</span></span>  
 <span data-ttu-id="1b4b0-110">Il `GetName` metodo restituisce il nome di file e percorso completo dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="1b4b0-110">The `GetName` method returns the full path and file name of the assembly.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1b4b0-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="1b4b0-111">Requirements</span></span>  
 <span data-ttu-id="1b4b0-112">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1b4b0-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1b4b0-113">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1b4b0-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1b4b0-114">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1b4b0-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1b4b0-115">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1b4b0-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
