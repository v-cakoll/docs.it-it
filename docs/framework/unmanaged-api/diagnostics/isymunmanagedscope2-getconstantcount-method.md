---
title: Metodo ISymUnmanagedScope2::GetConstantCount
ms.date: 03/30/2017
api_name:
- ISymUnmanagedScope2.GetConstantCount
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedScope2::GetConstantCount
helpviewer_keywords:
- ISymUnmanagedScope2::GetConstantCount method [.NET Framework debugging]
- GetConstantCount method [.NET Framework debugging]
ms.assetid: 1e1f0be6-c4e8-4d6c-98cd-d5fa9f686e87
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 2a063d25e180be466421c14ca65a5b4cea881fc8
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59127328"
---
# <a name="isymunmanagedscope2getconstantcount-method"></a><span data-ttu-id="b6c32-102">Metodo ISymUnmanagedScope2::GetConstantCount</span><span class="sxs-lookup"><span data-stu-id="b6c32-102">ISymUnmanagedScope2::GetConstantCount Method</span></span>
<span data-ttu-id="b6c32-103">Ottiene un conteggio delle costanti definite all'interno di questo ambito.</span><span class="sxs-lookup"><span data-stu-id="b6c32-103">Gets a count of the constants defined within this scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b6c32-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b6c32-104">Syntax</span></span>  
  
```  
HRESULT GetConstantCount(  
    [out, retval] ULONG32 *pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b6c32-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="b6c32-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="b6c32-106">[out] Un puntatore a un `ULONG32` che riceve le dimensioni, in caratteri, del buffer necessaria per contenere le costanti.</span><span class="sxs-lookup"><span data-stu-id="b6c32-106">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the constants.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b6c32-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="b6c32-107">Return Value</span></span>  
 <span data-ttu-id="b6c32-108">S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o qualche altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="b6c32-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b6c32-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="b6c32-109">Requirements</span></span>  
 <span data-ttu-id="b6c32-110">**Intestazione:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="b6c32-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b6c32-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b6c32-111">See also</span></span>

- [<span data-ttu-id="b6c32-112">Interfaccia ISymUnmanagedScope2</span><span class="sxs-lookup"><span data-stu-id="b6c32-112">ISymUnmanagedScope2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope2-interface.md)
