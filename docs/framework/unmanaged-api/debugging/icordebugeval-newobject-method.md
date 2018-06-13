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
ms.openlocfilehash: 5ff378602fc7338263ef49aee6802d2138bab9d2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33413172"
---
# <a name="icordebugevalnewobject-method"></a><span data-ttu-id="76ee9-102">Metodo ICorDebugEval::NewObject</span><span class="sxs-lookup"><span data-stu-id="76ee9-102">ICorDebugEval::NewObject Method</span></span>
<span data-ttu-id="76ee9-103">Alloca una nuova istanza dell'oggetto e chiama il metodo costruttore specificato.</span><span class="sxs-lookup"><span data-stu-id="76ee9-103">Allocates a new object instance and calls the specified constructor method.</span></span>  
  
 <span data-ttu-id="76ee9-104">Questo metodo è obsoleto in .NET Framework versione 2.0.</span><span class="sxs-lookup"><span data-stu-id="76ee9-104">This method is obsolete in the .NET Framework version 2.0.</span></span> <span data-ttu-id="76ee9-105">Utilizzare [ICorDebugEval2::](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newparameterizedobject-method.md) invece.</span><span class="sxs-lookup"><span data-stu-id="76ee9-105">Use [ICorDebugEval2::NewParameterizedObject](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newparameterizedobject-method.md) instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="76ee9-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="76ee9-106">Syntax</span></span>  
  
```  
HRESULT NewObject (  
    [in] ICorDebugFunction  *pConstructor,  
    [in] ULONG32            nArgs,  
    [in, size_is(nArgs)] ICorDebugValue *ppArgs[]  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="76ee9-107">Parametri</span><span class="sxs-lookup"><span data-stu-id="76ee9-107">Parameters</span></span>  
 `pConstructor`  
 <span data-ttu-id="76ee9-108">[in] Il costruttore da chiamare.</span><span class="sxs-lookup"><span data-stu-id="76ee9-108">[in] The constructor to be called.</span></span>  
  
 `nArgs`  
 <span data-ttu-id="76ee9-109">[in] Dimensione della matrice `ppArgs`.</span><span class="sxs-lookup"><span data-stu-id="76ee9-109">[in] The size of the `ppArgs` array.</span></span>  
  
 `ppArgs`  
 <span data-ttu-id="76ee9-110">[in] Matrice di oggetti ICorDebugValue, ognuno dei quali rappresenta un argomento deve essere passato al costruttore.</span><span class="sxs-lookup"><span data-stu-id="76ee9-110">[in] An array of ICorDebugValue objects, each of which represents an argument to be passed to the constructor.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="76ee9-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="76ee9-111">Requirements</span></span>  
 <span data-ttu-id="76ee9-112">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="76ee9-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="76ee9-113">**Intestazione:** Cordebug. idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="76ee9-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="76ee9-114">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="76ee9-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="76ee9-115">**Versioni di .NET framework:** 1.1, 1.0</span><span class="sxs-lookup"><span data-stu-id="76ee9-115">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="76ee9-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="76ee9-116">See Also</span></span>  
 [<span data-ttu-id="76ee9-117">Metodo NewParameterizedObject</span><span class="sxs-lookup"><span data-stu-id="76ee9-117">NewParameterizedObject Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newparameterizedobject-method.md)
