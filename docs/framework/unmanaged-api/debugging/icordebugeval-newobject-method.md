---
title: Metodo ICorDebugEval::NewObject
ms.date: 03/30/2017
api_name:
- ICorDebugEval.NewObject
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval::NewObject
helpviewer_keywords:
- NewObject method [.NET Framework debugging]
- ICorDebugEval::NewObject method [.NET Framework debugging]
ms.assetid: ce3025e8-defa-4c5e-8298-f49d71fa5736
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9c2d6a66eca080b480b508afea36c33b3e0aeec0
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59178230"
---
# <a name="icordebugevalnewobject-method"></a><span data-ttu-id="6d1a3-102">Metodo ICorDebugEval::NewObject</span><span class="sxs-lookup"><span data-stu-id="6d1a3-102">ICorDebugEval::NewObject Method</span></span>
<span data-ttu-id="6d1a3-103">Consente di allocare una nuova istanza dell'oggetto e chiama il metodo costruttore specificato.</span><span class="sxs-lookup"><span data-stu-id="6d1a3-103">Allocates a new object instance and calls the specified constructor method.</span></span>  
  
 <span data-ttu-id="6d1a3-104">Questo metodo è obsoleto in .NET Framework versione 2.0.</span><span class="sxs-lookup"><span data-stu-id="6d1a3-104">This method is obsolete in the .NET Framework version 2.0.</span></span> <span data-ttu-id="6d1a3-105">Uso [ICorDebugEval2::NewParameterizedObject](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newparameterizedobject-method.md) invece.</span><span class="sxs-lookup"><span data-stu-id="6d1a3-105">Use [ICorDebugEval2::NewParameterizedObject](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newparameterizedobject-method.md) instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6d1a3-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6d1a3-106">Syntax</span></span>  
  
```  
HRESULT NewObject (  
    [in] ICorDebugFunction  *pConstructor,  
    [in] ULONG32            nArgs,  
    [in, size_is(nArgs)] ICorDebugValue *ppArgs[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6d1a3-107">Parametri</span><span class="sxs-lookup"><span data-stu-id="6d1a3-107">Parameters</span></span>  
 `pConstructor`  
 <span data-ttu-id="6d1a3-108">[in] Il costruttore da chiamare.</span><span class="sxs-lookup"><span data-stu-id="6d1a3-108">[in] The constructor to be called.</span></span>  
  
 `nArgs`  
 <span data-ttu-id="6d1a3-109">[in] Dimensione della matrice `ppArgs`.</span><span class="sxs-lookup"><span data-stu-id="6d1a3-109">[in] The size of the `ppArgs` array.</span></span>  
  
 `ppArgs`  
 <span data-ttu-id="6d1a3-110">[in] Matrice di oggetti ICorDebugValue, ognuno dei quali rappresenta un argomento da passare al costruttore.</span><span class="sxs-lookup"><span data-stu-id="6d1a3-110">[in] An array of ICorDebugValue objects, each of which represents an argument to be passed to the constructor.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6d1a3-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="6d1a3-111">Requirements</span></span>  
 <span data-ttu-id="6d1a3-112">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6d1a3-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6d1a3-113">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6d1a3-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6d1a3-114">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6d1a3-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6d1a3-115">**Versioni di .NET framework:** 1.1, 1.0</span><span class="sxs-lookup"><span data-stu-id="6d1a3-115">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6d1a3-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6d1a3-116">See also</span></span>

- [<span data-ttu-id="6d1a3-117">Metodo NewParameterizedObject</span><span class="sxs-lookup"><span data-stu-id="6d1a3-117">NewParameterizedObject Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newparameterizedobject-method.md)
