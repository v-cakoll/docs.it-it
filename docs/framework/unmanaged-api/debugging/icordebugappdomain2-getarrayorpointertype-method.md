---
title: Metodo ICorDebugAppDomain2::GetArrayOrPointerType
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugAppDomain2.GetArrayOrPointerType
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugAppDomain2::GetArrayOrPointerType
helpviewer_keywords:
- GetArrayOrPointerType method [.NET Framework debugging]
- ICorDebugAppDomain2::GetArrayOrPointerType method [.NET Framework debugging]
ms.assetid: 97e493f5-3a62-4ec7-b42f-4af57bf71f57
topic_type: apiref
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: c08a56ff7f6bd109c5568a7f992850708a22a4b0
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugappdomain2getarrayorpointertype-method"></a><span data-ttu-id="9dd9d-102">Metodo ICorDebugAppDomain2::GetArrayOrPointerType</span><span class="sxs-lookup"><span data-stu-id="9dd9d-102">ICorDebugAppDomain2::GetArrayOrPointerType Method</span></span>
<span data-ttu-id="9dd9d-103">Ottiene una matrice di tipo specificato, o un puntatore o un riferimento al tipo specificato.</span><span class="sxs-lookup"><span data-stu-id="9dd9d-103">Gets an array of the specified type, or a pointer or reference to the specified type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9dd9d-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9dd9d-104">Syntax</span></span>  
  
```  
HRESULT GetArrayOrPointerType (  
    [in]  CorElementType    elementType,  
    [in]  ULONG32           nRank,  
    [in]  ICorDebugType     *pTypeArg,  
    [out] ICorDebugType     **ppType  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9dd9d-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="9dd9d-105">Parameters</span></span>  
 `elementType`  
 <span data-ttu-id="9dd9d-106">[in] Valore dell'enumerazione CorElementType che specifica il tipo nativo sottostante (una matrice, un puntatore o riferimento) da creare.</span><span class="sxs-lookup"><span data-stu-id="9dd9d-106">[in] A value of the CorElementType enumeration that specifies the underlying native type (an array, pointer, or reference) to be created.</span></span>  
  
 `nRank`  
 <span data-ttu-id="9dd9d-107">[in] La classificazione (numero di dimensioni) della matrice.</span><span class="sxs-lookup"><span data-stu-id="9dd9d-107">[in] The rank (that is, number of dimensions) of the array.</span></span> <span data-ttu-id="9dd9d-108">Questo valore deve essere 0 se `elementType` specifica un tipo puntatore o riferimento.</span><span class="sxs-lookup"><span data-stu-id="9dd9d-108">This value must be 0 if `elementType` specifies a pointer or reference type.</span></span>  
  
 `pTypeArg`  
 <span data-ttu-id="9dd9d-109">[in] Un puntatore a un oggetto ICorDebugType che rappresenta il tipo di matrice, puntatore o riferimento da creare.</span><span class="sxs-lookup"><span data-stu-id="9dd9d-109">[in] A pointer to an ICorDebugType object that represents the type of array, pointer, or reference to be created.</span></span>  
  
 `ppType`  
 <span data-ttu-id="9dd9d-110">[out] Un puntatore all'indirizzo di un `ICorDebugType` tipo di oggetto che rappresenta la matrice costruito, il tipo di puntatore o riferimento.</span><span class="sxs-lookup"><span data-stu-id="9dd9d-110">[out] A pointer to the address of an `ICorDebugType` object that represents the constructed array, pointer type, or reference type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9dd9d-111">Note</span><span class="sxs-lookup"><span data-stu-id="9dd9d-111">Remarks</span></span>  
 <span data-ttu-id="9dd9d-112">Il valore di *elementType* deve essere uno dei seguenti:</span><span class="sxs-lookup"><span data-stu-id="9dd9d-112">The value of *elementType* must be one of the following:</span></span>  
  
-   <span data-ttu-id="9dd9d-113">ELEMENT_TYPE_PTR</span><span class="sxs-lookup"><span data-stu-id="9dd9d-113">ELEMENT_TYPE_PTR</span></span>  
  
-   <span data-ttu-id="9dd9d-114">ELEMENT_TYPE_BYREF</span><span class="sxs-lookup"><span data-stu-id="9dd9d-114">ELEMENT_TYPE_BYREF</span></span>  
  
-   <span data-ttu-id="9dd9d-115">ELEMENT_TYPE_ARRAY o ELEMENT_TYPE_SZARRAY</span><span class="sxs-lookup"><span data-stu-id="9dd9d-115">ELEMENT_TYPE_ARRAY or ELEMENT_TYPE_SZARRAY</span></span>  
  
 <span data-ttu-id="9dd9d-116">Se il valore di *elementType* è ELEMENT_TYPE_PTR o ELEMENT_TYPE_BYREF, *nDimensioni* deve essere zero.</span><span class="sxs-lookup"><span data-stu-id="9dd9d-116">If the value of *elementType* is ELEMENT_TYPE_PTR or ELEMENT_TYPE_BYREF, *nRank* must be zero.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9dd9d-117">Requisiti</span><span class="sxs-lookup"><span data-stu-id="9dd9d-117">Requirements</span></span>  
 <span data-ttu-id="9dd9d-118">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9dd9d-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9dd9d-119">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="9dd9d-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9dd9d-120">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9dd9d-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9dd9d-121">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9dd9d-121">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
