---
title: Metodo ISymUnmanagedMethod::GetToken
ms.date: 03/30/2017
api_name:
- ISymUnmanagedMethod.GetToken
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedMethod::GetToken
helpviewer_keywords:
- ISymUnmanagedMethod::GetToken method [.NET Framework debugging]
- GetToken method, ISymUnmanagedMethod interface [.NET Framework debugging]
ms.assetid: 4effbe95-c36e-4a45-8b2a-ee21339415fb
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 5b0acee31017fd02ac3e51f9e585669b9c90ec48
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57467017"
---
# <a name="isymunmanagedmethodgettoken-method"></a><span data-ttu-id="69e87-102">Metodo ISymUnmanagedMethod::GetToken</span><span class="sxs-lookup"><span data-stu-id="69e87-102">ISymUnmanagedMethod::GetToken Method</span></span>
<span data-ttu-id="69e87-103">Restituisce il token di metadati per questo metodo.</span><span class="sxs-lookup"><span data-stu-id="69e87-103">Returns the metadata token for this method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="69e87-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="69e87-104">Syntax</span></span>  
  
```  
HRESULT GetToken(  
   [out, retval]  mdMethodDef  *pToken);  
```  
  
## <a name="parameters"></a><span data-ttu-id="69e87-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="69e87-105">Parameters</span></span>  
 `pToken`  
 <span data-ttu-id="69e87-106">[out] Un puntatore a un `mdMethodDef` che riceve le dimensioni, in caratteri, del buffer necessaria per contenere i metadati.</span><span class="sxs-lookup"><span data-stu-id="69e87-106">[out] A pointer to a `mdMethodDef` that receives the size, in characters, of the buffer required to contain the metadata.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="69e87-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="69e87-107">Return Value</span></span>  
 <span data-ttu-id="69e87-108">S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o qualche altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="69e87-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="69e87-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="69e87-109">Requirements</span></span>  
 <span data-ttu-id="69e87-110">**Intestazione:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="69e87-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="69e87-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="69e87-111">See also</span></span>
- [<span data-ttu-id="69e87-112">Interfaccia ISymUnmanagedMethod</span><span class="sxs-lookup"><span data-stu-id="69e87-112">ISymUnmanagedMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md)
