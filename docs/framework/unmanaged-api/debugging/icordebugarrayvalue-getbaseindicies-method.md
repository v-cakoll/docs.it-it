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
ms.openlocfilehash: e103401b85626e53db53e1894c22b161774e5163
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73088681"
---
# <a name="icordebugarrayvaluegetbaseindicies-method"></a><span data-ttu-id="8de4e-102">Metodo ICorDebugArrayValue::GetBaseIndicies</span><span class="sxs-lookup"><span data-stu-id="8de4e-102">ICorDebugArrayValue::GetBaseIndicies Method</span></span>
<span data-ttu-id="8de4e-103">Ottiene l'indice di base di ogni dimensione nella matrice.</span><span class="sxs-lookup"><span data-stu-id="8de4e-103">Gets the base index of each dimension in the array.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8de4e-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8de4e-104">Syntax</span></span>  
  
```cpp  
HRESULT GetBaseIndicies (  
    [in] ULONG32          cdim,  
    [out, size_is(cdim), length_is(cdim)]   
        ULONG32           indicies[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8de4e-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="8de4e-105">Parameters</span></span>  
 `cdim`  
 <span data-ttu-id="8de4e-106">in Numero di dimensioni dell'oggetto `ICorDebugArrayValue`.</span><span class="sxs-lookup"><span data-stu-id="8de4e-106">[in] The number of dimensions of this `ICorDebugArrayValue` object.</span></span> <span data-ttu-id="8de4e-107">Questo valore corrisponde anche alla dimensione della matrice `indicies` perché la relativa dimensione è uguale al numero di dimensioni dell'oggetto `ICorDebugArrayValue`.</span><span class="sxs-lookup"><span data-stu-id="8de4e-107">This value is also the size of the `indicies` array because its size is equal to the number of dimensions of the `ICorDebugArrayValue` object.</span></span>  
  
 `indicies`  
 <span data-ttu-id="8de4e-108">out Matrice di Integer, ognuno dei quali è l'indice di base, ovvero l'indice iniziale, di una dimensione di questo oggetto `ICorDebugArrayValue`.</span><span class="sxs-lookup"><span data-stu-id="8de4e-108">[out] An array of integers, each of which is the base index (that is, the starting index) of a dimension of this `ICorDebugArrayValue` object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8de4e-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="8de4e-109">Requirements</span></span>  
 <span data-ttu-id="8de4e-110">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8de4e-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8de4e-111">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8de4e-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8de4e-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8de4e-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8de4e-113">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8de4e-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
