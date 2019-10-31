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
ms.openlocfilehash: 5e3619d12b9377a8482254703d3d97d0348a013b
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73127166"
---
# <a name="icordebugassemblygetname-method"></a><span data-ttu-id="b81df-102">Metodo ICorDebugAssembly::GetName</span><span class="sxs-lookup"><span data-stu-id="b81df-102">ICorDebugAssembly::GetName Method</span></span>
<span data-ttu-id="b81df-103">Ottiene il nome dell'assembly rappresentato da questa istanza di `ICorDebugAssembly`.</span><span class="sxs-lookup"><span data-stu-id="b81df-103">Gets the name of the assembly that this `ICorDebugAssembly` instance represents.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b81df-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b81df-104">Syntax</span></span>  
  
```cpp  
HRESULT GetName (  
    [in] ULONG32  cchName,  
    [out] ULONG32 *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)] WCHAR szName[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b81df-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="b81df-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="b81df-106">[in] Dimensione della matrice `szName`.</span><span class="sxs-lookup"><span data-stu-id="b81df-106">[in] The size of the `szName` array.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="b81df-107">out Puntatore a un Integer che specifica la lunghezza effettiva del nome.</span><span class="sxs-lookup"><span data-stu-id="b81df-107">[out] A pointer to an integer that specifies the actual length of the name.</span></span>  
  
 `szName`  
 <span data-ttu-id="b81df-108">out Matrice che archivia il nome.</span><span class="sxs-lookup"><span data-stu-id="b81df-108">[out] An array that stores the name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b81df-109">Note</span><span class="sxs-lookup"><span data-stu-id="b81df-109">Remarks</span></span>  
 <span data-ttu-id="b81df-110">Il metodo `GetName` restituisce il percorso completo e il nome file dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="b81df-110">The `GetName` method returns the full path and file name of the assembly.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b81df-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="b81df-111">Requirements</span></span>  
 <span data-ttu-id="b81df-112">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b81df-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b81df-113">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b81df-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b81df-114">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b81df-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b81df-115">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b81df-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
