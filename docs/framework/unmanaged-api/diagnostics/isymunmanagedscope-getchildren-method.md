---
title: Metodo ISymUnmanagedScope::GetChildren
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedScope.GetChildren
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedScope::GetChildren
helpviewer_keywords:
- ISymUnmanagedScope::GetChildren method [.NET Framework debugging]
- GetChildren method [.NET Framework debugging]
ms.assetid: 0bed524e-cc48-4bf0-b9fa-25d665e63ddb
topic_type: apiref
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: a43a0f46532bfb0eeaa4e385946a5aaa1b50eba8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="isymunmanagedscopegetchildren-method"></a><span data-ttu-id="8cd35-102">Metodo ISymUnmanagedScope::GetChildren</span><span class="sxs-lookup"><span data-stu-id="8cd35-102">ISymUnmanagedScope::GetChildren Method</span></span>
<span data-ttu-id="8cd35-103">Ottiene gli elementi figlio di questo ambito.</span><span class="sxs-lookup"><span data-stu-id="8cd35-103">Gets the children of this scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8cd35-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8cd35-104">Syntax</span></span>  
  
```  
HRESULT GetChildren(  
    [in]  ULONG32  cChildren,  
    [out] ULONG32  *pcChildren,  
    [out, size_is(cChildren),  
        length_is(*pcChildren)] ISymUnmanagedScope* children[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8cd35-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="8cd35-105">Parameters</span></span>  
 `cChildren`  
 <span data-ttu-id="8cd35-106">[in] Oggetto `ULONG32` che indica le dimensioni del `children` matrice.</span><span class="sxs-lookup"><span data-stu-id="8cd35-106">[in] A `ULONG32` that indicates the size of the `children` array.</span></span>  
  
 `pcChildren`  
 <span data-ttu-id="8cd35-107">[out] Un puntatore a un `ULONG32` che riceve le dimensioni del buffer necessaria per contenere gli elementi figlio.</span><span class="sxs-lookup"><span data-stu-id="8cd35-107">[out] A pointer to a `ULONG32` that receives the size of the buffer required to contain the children.</span></span>  
  
 `children`  
 <span data-ttu-id="8cd35-108">[out] La matrice restituita di elementi figlio.</span><span class="sxs-lookup"><span data-stu-id="8cd35-108">[out] The returned array of children.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8cd35-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="8cd35-109">Return Value</span></span>  
 <span data-ttu-id="8cd35-110">S_OK se il metodo ha esito positivo. in caso contrario, E_FAIL o un altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="8cd35-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8cd35-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="8cd35-111">Requirements</span></span>  
 <span data-ttu-id="8cd35-112">**Intestazione:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="8cd35-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8cd35-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8cd35-113">See Also</span></span>  
 [<span data-ttu-id="8cd35-114">ISymUnmanagedScope (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="8cd35-114">ISymUnmanagedScope Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md)  
 [<span data-ttu-id="8cd35-115">GetParent (metodo)</span><span class="sxs-lookup"><span data-stu-id="8cd35-115">GetParent Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-getparent-method.md)
