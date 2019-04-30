---
title: Metodo ISymUnmanagedScope::GetMethod
ms.date: 03/30/2017
api_name:
- ISymUnmanagedScope.GetMethod
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedScope::GetMethod
helpviewer_keywords:
- GetMethod method, ISymUnmanagedScope interface [.NET Framework debugging]
- ISymUnmanagedScope::GetMethod method [.NET Framework debugging]
ms.assetid: a61866ee-221a-45b9-a1b7-395825b77872
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 954b1d91f33fe9a7e4df1ef51ee3666047836a17
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61986128"
---
# <a name="isymunmanagedscopegetmethod-method"></a><span data-ttu-id="82a0c-102">Metodo ISymUnmanagedScope::GetMethod</span><span class="sxs-lookup"><span data-stu-id="82a0c-102">ISymUnmanagedScope::GetMethod Method</span></span>
<span data-ttu-id="82a0c-103">Ottiene il metodo che contiene questo ambito.</span><span class="sxs-lookup"><span data-stu-id="82a0c-103">Gets the method that contains this scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="82a0c-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="82a0c-104">Syntax</span></span>  
  
```  
HRESULT GetMethod(  
    [out, retval] ISymUnmanagedMethod** pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="82a0c-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="82a0c-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="82a0c-106">[out] Un puntatore al valore restituito [ISymUnmanagedMethod](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md) interfaccia.</span><span class="sxs-lookup"><span data-stu-id="82a0c-106">[out] A pointer to the returned [ISymUnmanagedMethod](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="82a0c-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="82a0c-107">Return Value</span></span>  
 <span data-ttu-id="82a0c-108">S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o qualche altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="82a0c-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="82a0c-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="82a0c-109">Requirements</span></span>  
 <span data-ttu-id="82a0c-110">**Intestazione:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="82a0c-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="82a0c-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="82a0c-111">See also</span></span>

- [<span data-ttu-id="82a0c-112">Interfaccia ISymUnmanagedScope</span><span class="sxs-lookup"><span data-stu-id="82a0c-112">ISymUnmanagedScope Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md)
