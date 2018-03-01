---
title: Metodo ICorDebugEval2::CreateValueForType
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorDebugEval2.CreateValueForType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval2::CreateValueForType
helpviewer_keywords:
- CreateValueForType method [.NET Framework debugging]
- ICorDebugEval2::CreateValueForType method [.NET Framework debugging]
ms.assetid: ea38ae20-7e0a-427a-be77-d78fae719d82
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 18e7eb5fc30c27fd2c4865dc61e2f75dc9e96068
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugeval2createvaluefortype-method"></a><span data-ttu-id="44e26-102">Metodo ICorDebugEval2::CreateValueForType</span><span class="sxs-lookup"><span data-stu-id="44e26-102">ICorDebugEval2::CreateValueForType Method</span></span>
<span data-ttu-id="44e26-103">Ottiene un puntatore a un nuovo oggetto ICorDebugValue del tipo specificato, con un valore iniziale pari a zero o null.</span><span class="sxs-lookup"><span data-stu-id="44e26-103">Gets a pointer to a new ICorDebugValue of the specified type, with an initial value of zero or null.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="44e26-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="44e26-104">Syntax</span></span>  
  
```  
HRESULT CreateValueForType (  
    [in] ICorDebugType         *pType,  
    [out] ICorDebugValue       **ppValue  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="44e26-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="44e26-105">Parameters</span></span>  
 `pType`  
 <span data-ttu-id="44e26-106">[in] Puntatore a un oggetto ICorDebugType che rappresenta il tipo.</span><span class="sxs-lookup"><span data-stu-id="44e26-106">[in] Pointer to an ICorDebugType object that represents the type.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="44e26-107">[out] Puntatore all'indirizzo di un `ICorDebugValue` oggetto che rappresenta il valore.</span><span class="sxs-lookup"><span data-stu-id="44e26-107">[out] Pointer to the address of an `ICorDebugValue` object that represents the value.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="44e26-108">Note</span><span class="sxs-lookup"><span data-stu-id="44e26-108">Remarks</span></span>  
 <span data-ttu-id="44e26-109">`CreateValueForType`Consente di generalizzare [ICorDebugEval:: CreateValue](../../../../docs/framework/unmanaged-api/debugging/icordebugeval-createvalue-method.md) , consentendo di specificare un tipo di oggetto arbitrario, inclusi i tipi costruiti, ad esempio `List<int>`.</span><span class="sxs-lookup"><span data-stu-id="44e26-109">`CreateValueForType` generalizes [ICorDebugEval::CreateValue](../../../../docs/framework/unmanaged-api/debugging/icordebugeval-createvalue-method.md) by allowing you to specify an arbitrary object type, including constructed types such as `List<int>`.</span></span> <span data-ttu-id="44e26-110">L'unico scopo di questo metodo consiste nel generare un valore che può essere passato a una valutazione della funzione.</span><span class="sxs-lookup"><span data-stu-id="44e26-110">The only purpose of this method is to generate a value that can be passed to a function evaluation.</span></span>  
  
 <span data-ttu-id="44e26-111">Il tipo deve essere una classe o un tipo di valore.</span><span class="sxs-lookup"><span data-stu-id="44e26-111">The type must be a class or a value type.</span></span> <span data-ttu-id="44e26-112">È possibile utilizzare questo metodo per creare valori di matrice o stringa.</span><span class="sxs-lookup"><span data-stu-id="44e26-112">You cannot use this method to create array values or string values.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="44e26-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="44e26-113">Requirements</span></span>  
 <span data-ttu-id="44e26-114">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="44e26-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="44e26-115">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="44e26-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="44e26-116">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="44e26-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="44e26-117">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="44e26-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
