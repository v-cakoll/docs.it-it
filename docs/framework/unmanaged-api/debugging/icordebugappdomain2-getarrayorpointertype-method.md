---
title: Metodo ICorDebugAppDomain2::GetArrayOrPointerType
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomain2.GetArrayOrPointerType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAppDomain2::GetArrayOrPointerType
helpviewer_keywords:
- GetArrayOrPointerType method [.NET Framework debugging]
- ICorDebugAppDomain2::GetArrayOrPointerType method [.NET Framework debugging]
ms.assetid: 97e493f5-3a62-4ec7-b42f-4af57bf71f57
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6cc38ef23a8b802d674a7a6dc4807371e432f73d
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64593511"
---
# <a name="icordebugappdomain2getarrayorpointertype-method"></a><span data-ttu-id="06da3-102">Metodo ICorDebugAppDomain2::GetArrayOrPointerType</span><span class="sxs-lookup"><span data-stu-id="06da3-102">ICorDebugAppDomain2::GetArrayOrPointerType Method</span></span>
<span data-ttu-id="06da3-103">Ottiene una matrice di tipo specificato, o un puntatore o riferimento al tipo specificato.</span><span class="sxs-lookup"><span data-stu-id="06da3-103">Gets an array of the specified type, or a pointer or reference to the specified type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="06da3-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="06da3-104">Syntax</span></span>  
  
```  
HRESULT GetArrayOrPointerType (  
    [in]  CorElementType    elementType,  
    [in]  ULONG32           nRank,  
    [in]  ICorDebugType     *pTypeArg,  
    [out] ICorDebugType     **ppType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="06da3-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="06da3-105">Parameters</span></span>  
 `elementType`  
 <span data-ttu-id="06da3-106">[in] Valore dell'enumerazione CorElementType che specifica il tipo nativo sottostante (una matrice, un puntatore o riferimento) deve essere creato.</span><span class="sxs-lookup"><span data-stu-id="06da3-106">[in] A value of the CorElementType enumeration that specifies the underlying native type (an array, pointer, or reference) to be created.</span></span>  
  
 `nRank`  
 <span data-ttu-id="06da3-107">[in] La classificazione (vale a dire, numero di dimensioni) della matrice.</span><span class="sxs-lookup"><span data-stu-id="06da3-107">[in] The rank (that is, number of dimensions) of the array.</span></span> <span data-ttu-id="06da3-108">Questo valore deve essere 0 se `elementType` specifica un tipo puntatore o riferimento.</span><span class="sxs-lookup"><span data-stu-id="06da3-108">This value must be 0 if `elementType` specifies a pointer or reference type.</span></span>  
  
 `pTypeArg`  
 <span data-ttu-id="06da3-109">[in] Un puntatore a un oggetto ICorDebugType che rappresenta il tipo di matrice, puntatore o riferimento deve essere creato.</span><span class="sxs-lookup"><span data-stu-id="06da3-109">[in] A pointer to an ICorDebugType object that represents the type of array, pointer, or reference to be created.</span></span>  
  
 `ppType`  
 <span data-ttu-id="06da3-110">[out] Un puntatore all'indirizzo di un `ICorDebugType` il tipo di oggetto che rappresenta la matrice costruita, tipo di puntatore o riferimento.</span><span class="sxs-lookup"><span data-stu-id="06da3-110">[out] A pointer to the address of an `ICorDebugType` object that represents the constructed array, pointer type, or reference type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="06da3-111">Note</span><span class="sxs-lookup"><span data-stu-id="06da3-111">Remarks</span></span>  
 <span data-ttu-id="06da3-112">Il valore di *elementType* deve essere uno dei seguenti:</span><span class="sxs-lookup"><span data-stu-id="06da3-112">The value of *elementType* must be one of the following:</span></span>  
  
- <span data-ttu-id="06da3-113">ELEMENT_TYPE_PTR</span><span class="sxs-lookup"><span data-stu-id="06da3-113">ELEMENT_TYPE_PTR</span></span>  
  
- <span data-ttu-id="06da3-114">ELEMENT_TYPE_BYREF</span><span class="sxs-lookup"><span data-stu-id="06da3-114">ELEMENT_TYPE_BYREF</span></span>  
  
- <span data-ttu-id="06da3-115">ELEMENT_TYPE_ARRAY o ELEMENT_TYPE_SZARRAY</span><span class="sxs-lookup"><span data-stu-id="06da3-115">ELEMENT_TYPE_ARRAY or ELEMENT_TYPE_SZARRAY</span></span>  
  
 <span data-ttu-id="06da3-116">Se il valore di *elementType* rappresenti ELEMENT_TYPE_BYREF, ELEMENT_TYPE_PTR *nDimensioni* deve essere zero.</span><span class="sxs-lookup"><span data-stu-id="06da3-116">If the value of *elementType* is ELEMENT_TYPE_PTR or ELEMENT_TYPE_BYREF, *nRank* must be zero.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="06da3-117">Requisiti</span><span class="sxs-lookup"><span data-stu-id="06da3-117">Requirements</span></span>  
 <span data-ttu-id="06da3-118">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="06da3-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="06da3-119">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="06da3-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="06da3-120">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="06da3-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="06da3-121">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="06da3-121">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
