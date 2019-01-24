---
title: Metodo ISymUnmanagedVariable::GetEndOffset
ms.date: 03/30/2017
api_name:
- ISymUnmanagedVariable.GetEndOffset
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedVariable::GetEndOffset
helpviewer_keywords:
- ISymUnmanagedVariable::GetEndOffset method [.NET Framework debugging]
- GetEndOffset method, ISymUnmanagedVariable interface [.NET Framework debugging]
ms.assetid: e5d777c5-d450-4c0f-999c-b3953ee22cfb
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a4c474b2ea9bc80be156c8e1424eabe3d2384666
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54585269"
---
# <a name="isymunmanagedvariablegetendoffset-method"></a><span data-ttu-id="6e6d2-102">Metodo ISymUnmanagedVariable::GetEndOffset</span><span class="sxs-lookup"><span data-stu-id="6e6d2-102">ISymUnmanagedVariable::GetEndOffset Method</span></span>
<span data-ttu-id="6e6d2-103">Ottiene l'offset finale della variabile all'interno di relativo elemento padre.</span><span class="sxs-lookup"><span data-stu-id="6e6d2-103">Gets the end offset of this variable within its parent.</span></span> <span data-ttu-id="6e6d2-104">Se si tratta di una variabile locale all'interno di un ambito, l'offset finale rientrerà negli offset definiti per l'ambito.</span><span class="sxs-lookup"><span data-stu-id="6e6d2-104">If this is a local variable within a scope, the end offset will fall within the offsets defined for the scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6e6d2-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6e6d2-105">Syntax</span></span>  
  
```  
HRESULT GetEndOffset(  
    [out, retval] ULONG32* pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="6e6d2-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="6e6d2-106">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="6e6d2-107">[out] Un puntatore a un `ULONG32` che riceve l'offset finale.</span><span class="sxs-lookup"><span data-stu-id="6e6d2-107">[out] A pointer to a `ULONG32` that receives the end offset.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6e6d2-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="6e6d2-108">Return Value</span></span>  
 <span data-ttu-id="6e6d2-109">S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o qualche altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="6e6d2-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6e6d2-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="6e6d2-110">Requirements</span></span>  
 <span data-ttu-id="6e6d2-111">**Intestazione:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="6e6d2-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6e6d2-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6e6d2-112">See also</span></span>
- [<span data-ttu-id="6e6d2-113">Interfaccia ISymUnmanagedVariable</span><span class="sxs-lookup"><span data-stu-id="6e6d2-113">ISymUnmanagedVariable Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-interface.md)
- [<span data-ttu-id="6e6d2-114">Metodo GetStartOffset</span><span class="sxs-lookup"><span data-stu-id="6e6d2-114">GetStartOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getstartoffset-method.md)
