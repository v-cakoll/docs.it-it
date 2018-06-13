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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e3fe9edf7a635e54aac881a242aca3bc32e21fe1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33408125"
---
# <a name="icordebugarrayvaluegetbaseindicies-method"></a><span data-ttu-id="12973-102">Metodo ICorDebugArrayValue::GetBaseIndicies</span><span class="sxs-lookup"><span data-stu-id="12973-102">ICorDebugArrayValue::GetBaseIndicies Method</span></span>
<span data-ttu-id="12973-103">Ottiene l'indice di base di ciascuna dimensione della matrice.</span><span class="sxs-lookup"><span data-stu-id="12973-103">Gets the base index of each dimension in the array.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="12973-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="12973-104">Syntax</span></span>  
  
```  
HRESULT GetBaseIndicies (  
    [in] ULONG32          cdim,  
    [out, size_is(cdim), length_is(cdim)]   
        ULONG32           indicies[]  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="12973-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="12973-105">Parameters</span></span>  
 `cdim`  
 <span data-ttu-id="12973-106">[in] Il numero di dimensioni di questo `ICorDebugArrayValue` oggetto.</span><span class="sxs-lookup"><span data-stu-id="12973-106">[in] The number of dimensions of this `ICorDebugArrayValue` object.</span></span> <span data-ttu-id="12973-107">Questo valore corrisponde anche alla dimensione del `indicies` matrice perché la dimensione è uguale al numero di dimensioni del `ICorDebugArrayValue` oggetto.</span><span class="sxs-lookup"><span data-stu-id="12973-107">This value is also the size of the `indicies` array because its size is equal to the number of dimensions of the `ICorDebugArrayValue` object.</span></span>  
  
 `indicies`  
 <span data-ttu-id="12973-108">[out] Una matrice di interi, ognuno dei quali è l'indice di base (ovvero, l'indice iniziale) di una dimensione di questo `ICorDebugArrayValue` oggetto.</span><span class="sxs-lookup"><span data-stu-id="12973-108">[out] An array of integers, each of which is the base index (that is, the starting index) of a dimension of this `ICorDebugArrayValue` object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="12973-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="12973-109">Requirements</span></span>  
 <span data-ttu-id="12973-110">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="12973-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="12973-111">**Intestazione:** Cordebug. idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="12973-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="12973-112">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="12973-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="12973-113">**Versioni di .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="12973-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
