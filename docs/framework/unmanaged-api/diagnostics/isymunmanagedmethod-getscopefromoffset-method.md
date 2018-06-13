---
title: Metodo ISymUnmanagedMethod::GetScopeFromOffset
ms.date: 03/30/2017
api_name:
- ISymUnmanagedMethod.GetScopeFromOffset
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedMethod::GetScopeFromOffset
helpviewer_keywords:
- GetScopeFromOffset method [.NET Framework debugging]
- ISymUnmanagedMethod::GetScopeFromOffset method [.NET Framework debugging]
ms.assetid: d14cf210-81f8-46e1-8b19-6ddec0ba8b11
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 0898d554a2602a1139f2e37eb67f3aa00c5bd79e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33436085"
---
# <a name="isymunmanagedmethodgetscopefromoffset-method"></a><span data-ttu-id="b22ee-102">Metodo ISymUnmanagedMethod::GetScopeFromOffset</span><span class="sxs-lookup"><span data-stu-id="b22ee-102">ISymUnmanagedMethod::GetScopeFromOffset Method</span></span>
<span data-ttu-id="b22ee-103">Ottiene l'ambito lessicale di maggiore inclusione all'interno del metodo che racchiude un offset specificato.</span><span class="sxs-lookup"><span data-stu-id="b22ee-103">Gets the most enclosing lexical scope within this method that encloses the given offset.</span></span> <span data-ttu-id="b22ee-104">Questo può essere utilizzato per avviare ricerche delle variabili locali.</span><span class="sxs-lookup"><span data-stu-id="b22ee-104">This can be used to start local variable searches.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b22ee-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b22ee-105">Syntax</span></span>  
  
```  
HRESULT GetScopeFromOffset(  
    [in]  ULONG32 offset,  
    [out, retval] ISymUnmanagedScope**  pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b22ee-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="b22ee-106">Parameters</span></span>  
 `offset`  
 <span data-ttu-id="b22ee-107">[in] Oggetto `ULONG` che contiene l'offset.</span><span class="sxs-lookup"><span data-stu-id="b22ee-107">[in] A `ULONG` that contains the offset.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="b22ee-108">[out] Un puntatore che viene impostato sull'oggetto restituito [ISymUnmanagedScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md) interfaccia.</span><span class="sxs-lookup"><span data-stu-id="b22ee-108">[out] A pointer that is set to the returned [ISymUnmanagedScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b22ee-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="b22ee-109">Return Value</span></span>  
 <span data-ttu-id="b22ee-110">S_OK se il metodo ha esito positivo. in caso contrario, E_FAIL o un altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="b22ee-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b22ee-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="b22ee-111">Requirements</span></span>  
 <span data-ttu-id="b22ee-112">**Intestazione:** CorSym. idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="b22ee-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b22ee-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b22ee-113">See Also</span></span>  
 [<span data-ttu-id="b22ee-114">Interfaccia ISymUnmanagedMethod</span><span class="sxs-lookup"><span data-stu-id="b22ee-114">ISymUnmanagedMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md)
