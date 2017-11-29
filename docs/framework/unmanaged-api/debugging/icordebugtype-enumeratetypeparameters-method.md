---
title: Metodo ICorDebugType::EnumerateTypeParameters
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugType.EnumerateTypeParameters
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugType::EnumerateTypeParameters
helpviewer_keywords:
- EnumerateTypeParameters method, ICorDebugType interface [.NET Framework debugging]
- ICorDebugType::EnumerateTypeParameters method [.NET Framework debugging]
ms.assetid: 1ee1f6e6-1bd7-4ebb-83b8-ff9a08ca03de
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: e9dd00b0a5f28821112621a54c97551c71e1acc6
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugtypeenumeratetypeparameters-method"></a><span data-ttu-id="eae46-102">Metodo ICorDebugType::EnumerateTypeParameters</span><span class="sxs-lookup"><span data-stu-id="eae46-102">ICorDebugType::EnumerateTypeParameters Method</span></span>
<span data-ttu-id="eae46-103">Ottiene un puntatore a interfaccia a un'interfaccia ICorDebugTypeEnum che contiene il <xref:System.Type> parametri della classe indicata da ICorDebugType.</span><span class="sxs-lookup"><span data-stu-id="eae46-103">Gets an interface pointer to an ICorDebugTypeEnum that contains the <xref:System.Type> parameters of the class referenced by this ICorDebugType.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eae46-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="eae46-104">Syntax</span></span>  
  
```  
HRESULT EnumerateTypeParameters (  
    [out] ICorDebugTypeEnum   **ppTyParEnum  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="eae46-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="eae46-105">Parameters</span></span>  
 `ppTyParEnum`  
 <span data-ttu-id="eae46-106">[out] Un puntatore all'indirizzo di un `ICorDebugTypeEnum` che contiene i parametri del tipo.</span><span class="sxs-lookup"><span data-stu-id="eae46-106">[out] A pointer to the address of an `ICorDebugTypeEnum` that contains the parameters of the type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="eae46-107">Note</span><span class="sxs-lookup"><span data-stu-id="eae46-107">Remarks</span></span>  
 <span data-ttu-id="eae46-108">È possibile utilizzare `EnumerateTypeParameters` se il valore di CorElementType restituito da [ICorDebugType:: GetType](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-gettype-method.md) è ELEMENT_TYPE_CLASS, ELEMENT_TYPE_VALUETYPE, ELEMENT_TYPE_ARRAY, ELEMENT_TYPE_SZARRAY, ELEMENT_TYPE_BYREF, ELEMENT_TYPE _ PTR o ELEMENT_TYPE_FNPTR.</span><span class="sxs-lookup"><span data-stu-id="eae46-108">You can use `EnumerateTypeParameters` if the CorElementType value returned by [ICorDebugType::GetType](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-gettype-method.md) is ELEMENT_TYPE_CLASS, ELEMENT_TYPE_VALUETYPE, ELEMENT_TYPE_ARRAY, ELEMENT_TYPE_SZARRAY, ELEMENT_TYPE_BYREF, ELEMENT_TYPE_PTR, or ELEMENT_TYPE_FNPTR.</span></span> <span data-ttu-id="eae46-109">Il numero di parametri e il relativo ordine dipende dal tipo:</span><span class="sxs-lookup"><span data-stu-id="eae46-109">The number of parameters and their order depends on the type:</span></span>  
  
-   <span data-ttu-id="eae46-110">ELEMENT_TYPE_CLASS o un ELEMENT_TYPE_VALUETYPE: il numero di parametri di tipo contenuto nel `ICorDebugTypeEnum` che questo metodo restituisce, variano in base al numero di parametri di tipo formale per la classe corrispondente.</span><span class="sxs-lookup"><span data-stu-id="eae46-110">ELEMENT_TYPE_CLASS or ELEMENT_TYPE_VALUETYPE: The number of type parameters contained in the `ICorDebugTypeEnum` that this method returns, will depend on the number of formal type parameters for the corresponding class.</span></span> <span data-ttu-id="eae46-111">Ad esempio, se il tipo è `class Dict<String,int32>`, quindi `EnumerateTypeParameters` restituirà un `ICorDebugTypeEnum` che contiene oggetti che rappresentano `String` e `int32` nella sequenza.</span><span class="sxs-lookup"><span data-stu-id="eae46-111">For example, if the type is `class Dict<String,int32>`, then `EnumerateTypeParameters` will return an `ICorDebugTypeEnum` that contains objects representing `String` and `int32` in sequence.</span></span>  
  
-   <span data-ttu-id="eae46-112">ELEMENT_TYPE_FNPTR: Il numero di parametri di tipo contenuto nel `ICorDebugTypeEnum` sarà uno maggiore del numero di argomenti accettati dalla funzione.</span><span class="sxs-lookup"><span data-stu-id="eae46-112">ELEMENT_TYPE_FNPTR: The number of type parameters contained in the `ICorDebugTypeEnum` will be one greater than the number of arguments accepted by the function.</span></span> <span data-ttu-id="eae46-113">Il primo parametro di tipo contenuto nel `ICorDebugTypeEnum` è il tipo restituito della funzione e i parametri di tipo successivi sono parametri della funzione.</span><span class="sxs-lookup"><span data-stu-id="eae46-113">The first type parameter contained in the `ICorDebugTypeEnum` is the return type for the function, and the subsequent type parameters are the function's parameters.</span></span>  
  
-   <span data-ttu-id="eae46-114">ELEMENT_TYPE_ARRAY, ELEMENT_TYPE_SZARRAY, ELEMENT_TYPE_BYREF o ELEMENT_TYPE_PTR: verrà restituito un parametro di tipo.</span><span class="sxs-lookup"><span data-stu-id="eae46-114">ELEMENT_TYPE_ARRAY, ELEMENT_TYPE_SZARRAY, ELEMENT_TYPE_BYREF, or ELEMENT_TYPE_PTR: One type parameter will be returned.</span></span> <span data-ttu-id="eae46-115">Ad esempio, se il tipo è un tipo di matrice, ad esempio `int32[]`,`EnumerateTypeParameters` restituirà un `ICorDebugTypeEnum` che contiene un oggetto che rappresenta `int32`.</span><span class="sxs-lookup"><span data-stu-id="eae46-115">For example, if the type is an array type such as `int32[]`,`EnumerateTypeParameters` will return an `ICorDebugTypeEnum` that contains an object representing `int32`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="eae46-116">Requisiti</span><span class="sxs-lookup"><span data-stu-id="eae46-116">Requirements</span></span>  
 <span data-ttu-id="eae46-117">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="eae46-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="eae46-118">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="eae46-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="eae46-119">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="eae46-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="eae46-120">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="eae46-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
