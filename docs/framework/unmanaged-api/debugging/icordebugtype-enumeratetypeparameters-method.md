---
title: Metodo ICorDebugType::EnumerateTypeParameters
ms.date: 03/30/2017
api_name:
- ICorDebugType.EnumerateTypeParameters
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugType::EnumerateTypeParameters
helpviewer_keywords:
- EnumerateTypeParameters method, ICorDebugType interface [.NET Framework debugging]
- ICorDebugType::EnumerateTypeParameters method [.NET Framework debugging]
ms.assetid: 1ee1f6e6-1bd7-4ebb-83b8-ff9a08ca03de
topic_type:
- apiref
ms.openlocfilehash: b2c381d093069f5ee86be1b19d75f5c2d69ad9fa
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791303"
---
# <a name="icordebugtypeenumeratetypeparameters-method"></a><span data-ttu-id="7b695-102">Metodo ICorDebugType::EnumerateTypeParameters</span><span class="sxs-lookup"><span data-stu-id="7b695-102">ICorDebugType::EnumerateTypeParameters Method</span></span>
<span data-ttu-id="7b695-103">Ottiene un puntatore a interfaccia a un ICorDebugTypeEnum che contiene i parametri di <xref:System.Type> della classe a cui fa riferimento ICorDebugType.</span><span class="sxs-lookup"><span data-stu-id="7b695-103">Gets an interface pointer to an ICorDebugTypeEnum that contains the <xref:System.Type> parameters of the class referenced by this ICorDebugType.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7b695-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7b695-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateTypeParameters (  
    [out] ICorDebugTypeEnum   **ppTyParEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7b695-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="7b695-105">Parameters</span></span>  
 `ppTyParEnum`  
 <span data-ttu-id="7b695-106">out Puntatore all'indirizzo di un `ICorDebugTypeEnum` che contiene i parametri del tipo.</span><span class="sxs-lookup"><span data-stu-id="7b695-106">[out] A pointer to the address of an `ICorDebugTypeEnum` that contains the parameters of the type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7b695-107">Note</span><span class="sxs-lookup"><span data-stu-id="7b695-107">Remarks</span></span>  
 <span data-ttu-id="7b695-108">È possibile utilizzare `EnumerateTypeParameters` se il valore CorElementType restituito da [ICorDebugType:: GetType](icordebugtype-gettype-method.md) è ELEMENT_TYPE_CLASS, ELEMENT_TYPE_VALUETYPE, ELEMENT_TYPE_ARRAY, ELEMENT_TYPE_SZARRAY, ELEMENT_TYPE_BYREF, ELEMENT_TYPE_PTR o ELEMENT_TYPE_FNPTR.</span><span class="sxs-lookup"><span data-stu-id="7b695-108">You can use `EnumerateTypeParameters` if the CorElementType value returned by [ICorDebugType::GetType](icordebugtype-gettype-method.md) is ELEMENT_TYPE_CLASS, ELEMENT_TYPE_VALUETYPE, ELEMENT_TYPE_ARRAY, ELEMENT_TYPE_SZARRAY, ELEMENT_TYPE_BYREF, ELEMENT_TYPE_PTR, or ELEMENT_TYPE_FNPTR.</span></span> <span data-ttu-id="7b695-109">Il numero di parametri e il relativo ordine dipendono dal tipo:</span><span class="sxs-lookup"><span data-stu-id="7b695-109">The number of parameters and their order depends on the type:</span></span>  
  
- <span data-ttu-id="7b695-110">ELEMENT_TYPE_CLASS o ELEMENT_TYPE_VALUETYPE: il numero di parametri di tipo contenuti nel `ICorDebugTypeEnum` restituito da questo metodo dipende dal numero di parametri di tipo formale per la classe corrispondente.</span><span class="sxs-lookup"><span data-stu-id="7b695-110">ELEMENT_TYPE_CLASS or ELEMENT_TYPE_VALUETYPE: The number of type parameters contained in the `ICorDebugTypeEnum` that this method returns, will depend on the number of formal type parameters for the corresponding class.</span></span> <span data-ttu-id="7b695-111">Se, ad esempio, il tipo è `class Dict<String,int32>`, `EnumerateTypeParameters` restituirà un `ICorDebugTypeEnum` contenente oggetti che rappresentano `String` e `int32` in sequenza.</span><span class="sxs-lookup"><span data-stu-id="7b695-111">For example, if the type is `class Dict<String,int32>`, then `EnumerateTypeParameters` will return an `ICorDebugTypeEnum` that contains objects representing `String` and `int32` in sequence.</span></span>  
  
- <span data-ttu-id="7b695-112">ELEMENT_TYPE_FNPTR: il numero di parametri di tipo contenuti nel `ICorDebugTypeEnum` sarà maggiore di uno rispetto al numero di argomenti accettati dalla funzione.</span><span class="sxs-lookup"><span data-stu-id="7b695-112">ELEMENT_TYPE_FNPTR: The number of type parameters contained in the `ICorDebugTypeEnum` will be one greater than the number of arguments accepted by the function.</span></span> <span data-ttu-id="7b695-113">Il primo parametro di tipo contenuto nell'`ICorDebugTypeEnum` è il tipo restituito per la funzione e i parametri di tipo successivi sono i parametri della funzione.</span><span class="sxs-lookup"><span data-stu-id="7b695-113">The first type parameter contained in the `ICorDebugTypeEnum` is the return type for the function, and the subsequent type parameters are the function's parameters.</span></span>  
  
- <span data-ttu-id="7b695-114">ELEMENT_TYPE_ARRAY, ELEMENT_TYPE_SZARRAY, ELEMENT_TYPE_BYREF o ELEMENT_TYPE_PTR: verrà restituito un parametro di tipo.</span><span class="sxs-lookup"><span data-stu-id="7b695-114">ELEMENT_TYPE_ARRAY, ELEMENT_TYPE_SZARRAY, ELEMENT_TYPE_BYREF, or ELEMENT_TYPE_PTR: One type parameter will be returned.</span></span> <span data-ttu-id="7b695-115">Se, ad esempio, il tipo è un tipo di matrice, ad esempio `int32[]`,`EnumerateTypeParameters` restituirà un `ICorDebugTypeEnum` contenente un oggetto che rappresenta `int32`.</span><span class="sxs-lookup"><span data-stu-id="7b695-115">For example, if the type is an array type such as `int32[]`,`EnumerateTypeParameters` will return an `ICorDebugTypeEnum` that contains an object representing `int32`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7b695-116">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="7b695-116">Requirements</span></span>  
 <span data-ttu-id="7b695-117">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7b695-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7b695-118">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7b695-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7b695-119">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7b695-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7b695-120">**Versioni .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7b695-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
