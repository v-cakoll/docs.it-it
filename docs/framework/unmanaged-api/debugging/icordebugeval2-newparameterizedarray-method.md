---
title: Metodo ICorDebugEval2::NewParameterizedArray
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugEval2.NewParameterizedArray
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugEval2::NewParameterizedArray
helpviewer_keywords:
- ICorDebugEval2::NewParameterizedArray method [.NET Framework debugging]
- NewParameterizedArray method [.NET Framework debugging]
ms.assetid: 45efb8ba-c4de-4109-945f-e734d376b43c
topic_type: apiref
caps.latest.revision: "15"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: cf7f8fb0d3418f863f2cd1531dc32b7e64c2b8a5
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugeval2newparameterizedarray-method"></a><span data-ttu-id="97565-102">Metodo ICorDebugEval2::NewParameterizedArray</span><span class="sxs-lookup"><span data-stu-id="97565-102">ICorDebugEval2::NewParameterizedArray Method</span></span>
<span data-ttu-id="97565-103">Alloca una nuova matrice del tipo di elemento specificato e le dimensioni.</span><span class="sxs-lookup"><span data-stu-id="97565-103">Allocates a new array of the specified element type and dimensions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="97565-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="97565-104">Syntax</span></span>  
  
```  
HRESULT NewParameterizedArray(  
    [in] ICorDebugType          *pElementType,  
    [in] ULONG32                rank,  
    [in, size_is(rank)] ULONG32 dims[],  
    [in, size_is(rank)] ULONG32 lowBounds[]  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="97565-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="97565-105">Parameters</span></span>  
 `pElementType`  
 <span data-ttu-id="97565-106">[in] Un puntatore a un oggetto ICorDebugType che rappresenta il tipo di elemento memorizzato nella matrice.</span><span class="sxs-lookup"><span data-stu-id="97565-106">[in] A pointer to an ICorDebugType object that represents the type of element stored in the array.</span></span>  
  
 `rank`  
 <span data-ttu-id="97565-107">[in] Il numero di dimensioni della matrice.</span><span class="sxs-lookup"><span data-stu-id="97565-107">[in] The number of dimensions of the array.</span></span> <span data-ttu-id="97565-108">In .NET Framework versione 2.0, questo valore deve essere 1.</span><span class="sxs-lookup"><span data-stu-id="97565-108">In the .NET Framework version 2.0, this value must be 1.</span></span>  
  
 `dims`  
 <span data-ttu-id="97565-109">[in] Le dimensioni in byte, di ciascuna dimensione della matrice.</span><span class="sxs-lookup"><span data-stu-id="97565-109">[in] The size, in bytes, of each dimension of the array.</span></span>  
  
 `lowBounds`  
 <span data-ttu-id="97565-110">[in] Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="97565-110">[in] Optional.</span></span> <span data-ttu-id="97565-111">Il limite inferiore di ogni dimensione della matrice.</span><span class="sxs-lookup"><span data-stu-id="97565-111">The lower bound of each dimension of the array.</span></span> <span data-ttu-id="97565-112">Se questo valore viene omesso, per ogni dimensione viene utilizzato un limite inferiore pari a zero.</span><span class="sxs-lookup"><span data-stu-id="97565-112">If this value is omitted, a lower bound of zero is assumed for each dimension.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="97565-113">Note</span><span class="sxs-lookup"><span data-stu-id="97565-113">Remarks</span></span>  
 <span data-ttu-id="97565-114">Gli elementi della matrice possono essere istanze di un tipo generico.</span><span class="sxs-lookup"><span data-stu-id="97565-114">The elements of the array may be instances of a generic type.</span></span> <span data-ttu-id="97565-115">La matrice viene sempre creata nel dominio dell'applicazione in cui il thread attualmente in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="97565-115">The array is always created in the application domain in which the thread is currently running.</span></span> <span data-ttu-id="97565-116">In .NET Framework 2.0, il valore di `rank` deve essere 1.</span><span class="sxs-lookup"><span data-stu-id="97565-116">In the .NET Framework 2.0, the value of `rank` must be 1.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="97565-117">Requisiti</span><span class="sxs-lookup"><span data-stu-id="97565-117">Requirements</span></span>  
 <span data-ttu-id="97565-118">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="97565-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="97565-119">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="97565-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="97565-120">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="97565-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="97565-121">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="97565-121">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
