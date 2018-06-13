---
title: Metodo ICorDebugEval2::CreateValueForType
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 683457c249915708becadaeda9dec265666e2023
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33412107"
---
# <a name="icordebugeval2createvaluefortype-method"></a><span data-ttu-id="e6b49-102">Metodo ICorDebugEval2::CreateValueForType</span><span class="sxs-lookup"><span data-stu-id="e6b49-102">ICorDebugEval2::CreateValueForType Method</span></span>
<span data-ttu-id="e6b49-103">Ottiene un puntatore a un nuovo oggetto ICorDebugValue del tipo specificato, con un valore iniziale pari a zero o null.</span><span class="sxs-lookup"><span data-stu-id="e6b49-103">Gets a pointer to a new ICorDebugValue of the specified type, with an initial value of zero or null.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e6b49-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e6b49-104">Syntax</span></span>  
  
```  
HRESULT CreateValueForType (  
    [in] ICorDebugType         *pType,  
    [out] ICorDebugValue       **ppValue  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e6b49-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="e6b49-105">Parameters</span></span>  
 `pType`  
 <span data-ttu-id="e6b49-106">[in] Puntatore a un oggetto ICorDebugType che rappresenta il tipo.</span><span class="sxs-lookup"><span data-stu-id="e6b49-106">[in] Pointer to an ICorDebugType object that represents the type.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="e6b49-107">[out] Puntatore all'indirizzo di un `ICorDebugValue` oggetto che rappresenta il valore.</span><span class="sxs-lookup"><span data-stu-id="e6b49-107">[out] Pointer to the address of an `ICorDebugValue` object that represents the value.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e6b49-108">Note</span><span class="sxs-lookup"><span data-stu-id="e6b49-108">Remarks</span></span>  
 <span data-ttu-id="e6b49-109">`CreateValueForType` Consente di generalizzare [ICorDebugEval:: CreateValue](../../../../docs/framework/unmanaged-api/debugging/icordebugeval-createvalue-method.md) consentendo di specificare un tipo di oggetto arbitrario, inclusi i tipi costruiti, ad esempio `List<int>`.</span><span class="sxs-lookup"><span data-stu-id="e6b49-109">`CreateValueForType` generalizes [ICorDebugEval::CreateValue](../../../../docs/framework/unmanaged-api/debugging/icordebugeval-createvalue-method.md) by allowing you to specify an arbitrary object type, including constructed types such as `List<int>`.</span></span> <span data-ttu-id="e6b49-110">L'unico scopo di questo metodo consiste nel generare un valore che può essere passato a una valutazione della funzione.</span><span class="sxs-lookup"><span data-stu-id="e6b49-110">The only purpose of this method is to generate a value that can be passed to a function evaluation.</span></span>  
  
 <span data-ttu-id="e6b49-111">Il tipo deve essere una classe o un tipo di valore.</span><span class="sxs-lookup"><span data-stu-id="e6b49-111">The type must be a class or a value type.</span></span> <span data-ttu-id="e6b49-112">È possibile utilizzare questo metodo per creare valori di matrice o stringa.</span><span class="sxs-lookup"><span data-stu-id="e6b49-112">You cannot use this method to create array values or string values.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e6b49-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="e6b49-113">Requirements</span></span>  
 <span data-ttu-id="e6b49-114">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e6b49-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e6b49-115">**Intestazione:** Cordebug. idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="e6b49-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e6b49-116">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="e6b49-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e6b49-117">**Versioni di .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e6b49-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
