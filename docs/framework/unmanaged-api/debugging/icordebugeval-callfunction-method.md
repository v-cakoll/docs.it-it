---
title: Metodo ICorDebugEval::CallFunction
ms.date: 03/30/2017
api_name:
- ICorDebugEval.CallFunction
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval::CallFunction
helpviewer_keywords:
- ICorDebugEval::CallFunction method [.NET Framework debugging]
- CallFunction method [.NET Framework debugging]
ms.assetid: 7f470c5c-e1c0-4d8d-aad8-830f113ae751
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 86d48461c601b53d4461331a11a0e0ac7ddc6e7c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33412552"
---
# <a name="icordebugevalcallfunction-method"></a><span data-ttu-id="a7d97-102">Metodo ICorDebugEval::CallFunction</span><span class="sxs-lookup"><span data-stu-id="a7d97-102">ICorDebugEval::CallFunction Method</span></span>
<span data-ttu-id="a7d97-103">Imposta una chiamata alla funzione specificata.</span><span class="sxs-lookup"><span data-stu-id="a7d97-103">Sets up a call to the specified function.</span></span>  
  
 <span data-ttu-id="a7d97-104">Questo metodo è obsoleto in .NET Framework versione 2.0.</span><span class="sxs-lookup"><span data-stu-id="a7d97-104">This method is obsolete in the .NET Framework version 2.0.</span></span> <span data-ttu-id="a7d97-105">Utilizzare [ICorDebugEval2:: CallParameterizedFunction](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-callparameterizedfunction-method.md) invece.</span><span class="sxs-lookup"><span data-stu-id="a7d97-105">Use [ICorDebugEval2::CallParameterizedFunction](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-callparameterizedfunction-method.md) instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a7d97-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a7d97-106">Syntax</span></span>  
  
```  
HRESULT CallFunction (  
    [in] ICorDebugFunction  *pFunction,  
    [in] ULONG32            nArgs,  
    [in, size_is(nArgs)] ICorDebugValue *ppArgs[]  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a7d97-107">Parametri</span><span class="sxs-lookup"><span data-stu-id="a7d97-107">Parameters</span></span>  
 `pFunction`  
 <span data-ttu-id="a7d97-108">[in] Puntatore a un oggetto ICorDebugFunction che specifica la funzione da chiamare.</span><span class="sxs-lookup"><span data-stu-id="a7d97-108">[in] Pointer to an ICorDebugFunction object that specifies the function to be called.</span></span>  
  
 `nArgs`  
 <span data-ttu-id="a7d97-109">[in] Il numero di argomenti per la funzione.</span><span class="sxs-lookup"><span data-stu-id="a7d97-109">[in] The number of arguments for the function.</span></span>  
  
 `ppArgs`  
 <span data-ttu-id="a7d97-110">[in] Matrice di puntatori, ognuno dei quali punta a un oggetto ICorDebugValue che specifica un argomento deve essere passato alla funzione.</span><span class="sxs-lookup"><span data-stu-id="a7d97-110">[in] An array of pointers, each of which points to an ICorDebugValue object that specifies an argument to be passed to the function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a7d97-111">Note</span><span class="sxs-lookup"><span data-stu-id="a7d97-111">Remarks</span></span>  
 <span data-ttu-id="a7d97-112">Se la funzione è virtuale, `CallFunction` eseguirà invio virtuale.</span><span class="sxs-lookup"><span data-stu-id="a7d97-112">If the function is virtual, `CallFunction` will perform virtual dispatch.</span></span> <span data-ttu-id="a7d97-113">Se la funzione è in un altro dominio applicazione, si verificherà una transizione, purché tutti gli argomenti sono anche nel dominio dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="a7d97-113">If the function is in a different application domain, a transition will occur as long as all arguments are also in that application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a7d97-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="a7d97-114">Requirements</span></span>  
 <span data-ttu-id="a7d97-115">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a7d97-115">**Platforms:** WindowSee [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a7d97-116">**Intestazione:** Cordebug. idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="a7d97-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a7d97-117">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="a7d97-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a7d97-118">**Versioni di .NET framework:** 1.1, 1.0</span><span class="sxs-lookup"><span data-stu-id="a7d97-118">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a7d97-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a7d97-119">See Also</span></span>  
 [<span data-ttu-id="a7d97-120">Metodo CallParameterizedFunction</span><span class="sxs-lookup"><span data-stu-id="a7d97-120">CallParameterizedFunction Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-callparameterizedfunction-method.md)
