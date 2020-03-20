---
title: Metodo ICorDebugArrayValue::GetDimensions
ms.date: 03/30/2017
api_name:
- ICorDebugArrayValue.GetDimensions
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugArrayValue::GetDimensions
helpviewer_keywords:
- ICorDebugArrayValue::GetDimensions method [.NET Framework debugging]
- GetDimensions method [.NET Framework debugging]
ms.assetid: 6c116592-134b-4ef2-a319-680e92d013aa
topic_type:
- apiref
ms.openlocfilehash: 35e043c56977bf644efe1dd9cee1409f50cc877f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179022"
---
# <a name="icordebugarrayvaluegetdimensions-method"></a><span data-ttu-id="51329-102">Metodo ICorDebugArrayValue::GetDimensions</span><span class="sxs-lookup"><span data-stu-id="51329-102">ICorDebugArrayValue::GetDimensions Method</span></span>
<span data-ttu-id="51329-103">Ottiene il numero di elementi in ogni dimensione di questa matrice.</span><span class="sxs-lookup"><span data-stu-id="51329-103">Gets the number of elements in each dimension of this array.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="51329-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="51329-104">Syntax</span></span>  
  
```cpp  
HRESULT GetDimensions (  
    [in] ULONG32         cdim,  
    [out, size_is(cdim), length_is(cdim)]
        ULONG32          dims[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="51329-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="51329-105">Parameters</span></span>  
 `cdim`  
 <span data-ttu-id="51329-106">[in] Numero di dimensioni di questo ICorDebugArrayValue oggetto.</span><span class="sxs-lookup"><span data-stu-id="51329-106">[in] The number of dimensions of this ICorDebugArrayValue object.</span></span>  
  
 <span data-ttu-id="51329-107">Questo valore è anche `dims` la dimensione della matrice perché la sua `ICorDebugArrayValue` dimensione è uguale al numero di dimensioni dell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="51329-107">This value is also the size of the `dims` array because its size is equal to the number of dimensions of the `ICorDebugArrayValue` object.</span></span>  
  
 `dims`  
 <span data-ttu-id="51329-108">[fuori] Matrice di interi, ognuno dei quali specifica il numero `ICorDebugArrayValue` di elementi in una dimensione in questo oggetto.</span><span class="sxs-lookup"><span data-stu-id="51329-108">[out] An array of integers, each of which specifies the number of elements in a dimension in this `ICorDebugArrayValue` object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="51329-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="51329-109">Requirements</span></span>  
 <span data-ttu-id="51329-110">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="51329-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="51329-111">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="51329-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="51329-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="51329-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="51329-113">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="51329-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
