---
title: Metodo ISymUnmanagedScope::GetNamespaces
ms.date: 03/30/2017
api_name:
- ISymUnmanagedScope.GetNamespaces
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedScope::GetNamespaces
helpviewer_keywords:
- GetNamespaces method, ISymUnmanagedScope interface [.NET Framework debugging]
- ISymUnmanagedScope::GetNamespaces method [.NET Framework debugging]
ms.assetid: c44b0440-04bd-460a-84fb-41afecf44503
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3dc3c842bbb4b86b82d03848751673400bed193b
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59213038"
---
# <a name="isymunmanagedscopegetnamespaces-method"></a><span data-ttu-id="7c9a7-102">Metodo ISymUnmanagedScope::GetNamespaces</span><span class="sxs-lookup"><span data-stu-id="7c9a7-102">ISymUnmanagedScope::GetNamespaces Method</span></span>
<span data-ttu-id="7c9a7-103">Ottiene gli spazi dei nomi utilizzati all'interno di questo ambito.</span><span class="sxs-lookup"><span data-stu-id="7c9a7-103">Gets the namespaces that are being used within this scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7c9a7-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7c9a7-104">Syntax</span></span>  
  
```  
HRESULT GetNamespaces(  
    [in]  ULONG32  cNameSpaces,  
    [out] ULONG32  *pcNameSpaces,  
    [out, size_is(cNameSpaces),  
        length_is(*pcNameSpaces)]  
        ISymUnmanagedNamespace* namespaces[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7c9a7-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="7c9a7-105">Parameters</span></span>  
 `cNameSpaces`  
 <span data-ttu-id="7c9a7-106">[in] Dimensione della matrice `namespaces`.</span><span class="sxs-lookup"><span data-stu-id="7c9a7-106">[in] The size of the `namespaces` array.</span></span>  
  
 `pcNameSpaces`  
 <span data-ttu-id="7c9a7-107">[out] Un puntatore a un `ULONG32` che riceve le dimensioni del buffer necessaria per contenere gli spazi dei nomi.</span><span class="sxs-lookup"><span data-stu-id="7c9a7-107">[out] A pointer to a `ULONG32` that receives the size of the buffer required to contain the namespaces.</span></span>  
  
 `namespaces`  
 <span data-ttu-id="7c9a7-108">[out] Matrice che riceve gli spazi dei nomi.</span><span class="sxs-lookup"><span data-stu-id="7c9a7-108">[out] The array that receives the namespaces.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7c9a7-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="7c9a7-109">Return Value</span></span>  
 <span data-ttu-id="7c9a7-110">S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o qualche altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="7c9a7-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7c9a7-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="7c9a7-111">Requirements</span></span>  
 <span data-ttu-id="7c9a7-112">**Intestazione:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="7c9a7-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7c9a7-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7c9a7-113">See also</span></span>

- [<span data-ttu-id="7c9a7-114">Interfaccia ISymUnmanagedScope</span><span class="sxs-lookup"><span data-stu-id="7c9a7-114">ISymUnmanagedScope Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md)
