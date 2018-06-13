---
title: Metodo ICorDebugEval::NewObjectNoConstructor
ms.date: 03/30/2017
api_name:
- ICorDebugEval.NewObjectNoConstructor
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval::NewObjectNoConstructor
helpviewer_keywords:
- NewObjectNoConstructor method [.NET Framework debugging]
- ICorDebugEval::NewObjectNoConstructor method [.NET Framework debugging]
ms.assetid: 80d509ca-b5e3-4c46-9c14-800db73d9bf7
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3e99cafe39a030a412bf33aeb9d96d5006ca02df
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33415961"
---
# <a name="icordebugevalnewobjectnoconstructor-method"></a><span data-ttu-id="745d8-102">Metodo ICorDebugEval::NewObjectNoConstructor</span><span class="sxs-lookup"><span data-stu-id="745d8-102">ICorDebugEval::NewObjectNoConstructor Method</span></span>
<span data-ttu-id="745d8-103">Alloca una nuova istanza dell'oggetto del tipo specificato, senza tentare di chiamare un metodo del costruttore.</span><span class="sxs-lookup"><span data-stu-id="745d8-103">Allocates a new object instance of the specified type, without attempting to call a constructor method.</span></span>  
  
 <span data-ttu-id="745d8-104">Questo metodo è obsoleto in .NET Framework versione 2.0.</span><span class="sxs-lookup"><span data-stu-id="745d8-104">This method is obsolete in the .NET Framework version 2.0.</span></span> <span data-ttu-id="745d8-105">Utilizzare [ICorDebugEval2:: NewParameterizedObjectNoConstructor](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newparameterizedobjectnoconstructor-method.md) invece.</span><span class="sxs-lookup"><span data-stu-id="745d8-105">Use [ICorDebugEval2::NewParameterizedObjectNoConstructor](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newparameterizedobjectnoconstructor-method.md) instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="745d8-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="745d8-106">Syntax</span></span>  
  
```  
HRESULT NewObjectNoConstructor (  
    [in] ICorDebugClass     *pClass  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="745d8-107">Parametri</span><span class="sxs-lookup"><span data-stu-id="745d8-107">Parameters</span></span>  
 `pClass`  
 <span data-ttu-id="745d8-108">[in] Puntatore a un oggetto ICorDebugClass che rappresenta il tipo di oggetto deve essere creata un'istanza.</span><span class="sxs-lookup"><span data-stu-id="745d8-108">[in] Pointer to an ICorDebugClass object that represents the type of object to be instantiated.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="745d8-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="745d8-109">Requirements</span></span>  
 <span data-ttu-id="745d8-110">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="745d8-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="745d8-111">**Intestazione:** Cordebug. idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="745d8-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="745d8-112">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="745d8-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="745d8-113">**Versioni di .NET framework:** 1.1, 1.0</span><span class="sxs-lookup"><span data-stu-id="745d8-113">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="745d8-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="745d8-114">See Also</span></span>  
 [<span data-ttu-id="745d8-115">Metodo NewParameterizedObjectNoConstructor</span><span class="sxs-lookup"><span data-stu-id="745d8-115">NewParameterizedObjectNoConstructor Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newparameterizedobjectnoconstructor-method.md)
