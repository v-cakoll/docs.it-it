---
title: Metodo ICorDebugArrayValue::GetBaseIndicies
ms.date: 03/30/2017
api_name:
- ICorDebugArrayValue.GetBaseIndicies
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugArrayValue::GetBaseIndicies
helpviewer_keywords:
- ICorDebugArrayValue::GetBaseIndicies method [.NET Framework debugging]
- GetBaseIndicies method [.NET Framework debugging]
ms.assetid: 868b339b-acdb-4fe0-91c7-b85f4fba99eb
topic_type:
- apiref
ms.openlocfilehash: 7c6d1905cdbd12b960014e687034ea9d163b68d7
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179030"
---
# <a name="icordebugarrayvaluegetbaseindicies-method"></a><span data-ttu-id="f2811-102">Metodo ICorDebugArrayValue::GetBaseIndicies</span><span class="sxs-lookup"><span data-stu-id="f2811-102">ICorDebugArrayValue::GetBaseIndicies Method</span></span>
<span data-ttu-id="f2811-103">Ottiene l'indice di base di ogni dimensione nella matrice.</span><span class="sxs-lookup"><span data-stu-id="f2811-103">Gets the base index of each dimension in the array.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f2811-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f2811-104">Syntax</span></span>  
  
```cpp  
HRESULT GetBaseIndicies (  
    [in] ULONG32          cdim,  
    [out, size_is(cdim), length_is(cdim)]
        ULONG32           indicies[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f2811-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="f2811-105">Parameters</span></span>  
 `cdim`  
 <span data-ttu-id="f2811-106">[in] Numero di dimensioni `ICorDebugArrayValue` di questo oggetto.</span><span class="sxs-lookup"><span data-stu-id="f2811-106">[in] The number of dimensions of this `ICorDebugArrayValue` object.</span></span> <span data-ttu-id="f2811-107">Questo valore è anche `indicies` la dimensione della matrice perché la sua `ICorDebugArrayValue` dimensione è uguale al numero di dimensioni dell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="f2811-107">This value is also the size of the `indicies` array because its size is equal to the number of dimensions of the `ICorDebugArrayValue` object.</span></span>  
  
 `indicies`  
 <span data-ttu-id="f2811-108">[fuori] Matrice di interi, ognuno dei quali è l'indice di base (ovvero l'indice iniziale) di una dimensione di questo `ICorDebugArrayValue` oggetto.</span><span class="sxs-lookup"><span data-stu-id="f2811-108">[out] An array of integers, each of which is the base index (that is, the starting index) of a dimension of this `ICorDebugArrayValue` object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f2811-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f2811-109">Requirements</span></span>  
 <span data-ttu-id="f2811-110">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f2811-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f2811-111">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f2811-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f2811-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f2811-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f2811-113">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f2811-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
