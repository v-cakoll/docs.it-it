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
ms.openlocfilehash: 255d88dcdd880c73a7535cddcad410dcfdcf1d70
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132654"
---
# <a name="icordebugevalnewobjectnoconstructor-method"></a><span data-ttu-id="9d51c-102">Metodo ICorDebugEval::NewObjectNoConstructor</span><span class="sxs-lookup"><span data-stu-id="9d51c-102">ICorDebugEval::NewObjectNoConstructor Method</span></span>
<span data-ttu-id="9d51c-103">Alloca una nuova istanza dell'oggetto del tipo specificato, senza tentare di chiamare un metodo del costruttore.</span><span class="sxs-lookup"><span data-stu-id="9d51c-103">Allocates a new object instance of the specified type, without attempting to call a constructor method.</span></span>  
  
 <span data-ttu-id="9d51c-104">Questo metodo è obsoleto nella versione .NET Framework 2,0.</span><span class="sxs-lookup"><span data-stu-id="9d51c-104">This method is obsolete in the .NET Framework version 2.0.</span></span> <span data-ttu-id="9d51c-105">Usare invece [ICorDebugEval2:: NewParameterizedObjectNoConstructor](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newparameterizedobjectnoconstructor-method.md) .</span><span class="sxs-lookup"><span data-stu-id="9d51c-105">Use [ICorDebugEval2::NewParameterizedObjectNoConstructor](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newparameterizedobjectnoconstructor-method.md) instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9d51c-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9d51c-106">Syntax</span></span>  
  
```cpp  
HRESULT NewObjectNoConstructor (  
    [in] ICorDebugClass     *pClass  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9d51c-107">Parametri</span><span class="sxs-lookup"><span data-stu-id="9d51c-107">Parameters</span></span>  
 `pClass`  
 <span data-ttu-id="9d51c-108">in Puntatore a un oggetto ICorDebugClass che rappresenta il tipo di oggetto di cui creare un'istanza.</span><span class="sxs-lookup"><span data-stu-id="9d51c-108">[in] Pointer to an ICorDebugClass object that represents the type of object to be instantiated.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9d51c-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="9d51c-109">Requirements</span></span>  
 <span data-ttu-id="9d51c-110">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9d51c-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9d51c-111">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9d51c-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9d51c-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9d51c-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9d51c-113">**Versioni .NET Framework:** 1,1, 1,0</span><span class="sxs-lookup"><span data-stu-id="9d51c-113">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9d51c-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9d51c-114">See also</span></span>

- [<span data-ttu-id="9d51c-115">Metodo NewParameterizedObjectNoConstructor</span><span class="sxs-lookup"><span data-stu-id="9d51c-115">NewParameterizedObjectNoConstructor Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newparameterizedobjectnoconstructor-method.md)
