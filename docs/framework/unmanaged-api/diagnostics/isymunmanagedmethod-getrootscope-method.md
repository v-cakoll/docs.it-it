---
title: Metodo ISymUnmanagedMethod::GetRootScope
ms.date: 03/30/2017
api_name:
- ISymUnmanagedMethod.GetRootScope
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedMethod::GetRootScope
helpviewer_keywords:
- ISymUnmanagedMethod::GetRootScope method [.NET Framework debugging]
- GetRootScope method [.NET Framework debugging]
ms.assetid: 7d58caac-2e75-4dfa-9249-32d8a624b247
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 7c77be0dde950693d3943e41c392dcdcd9bc995e
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59096075"
---
# <a name="isymunmanagedmethodgetrootscope-method"></a><span data-ttu-id="53f8f-102">Metodo ISymUnmanagedMethod::GetRootScope</span><span class="sxs-lookup"><span data-stu-id="53f8f-102">ISymUnmanagedMethod::GetRootScope Method</span></span>
<span data-ttu-id="53f8f-103">Ottiene l'ambito lessicale di primo livello all'interno di questo metodo.</span><span class="sxs-lookup"><span data-stu-id="53f8f-103">Gets the root lexical scope within this method.</span></span> <span data-ttu-id="53f8f-104">Questo ambito racchiude l'intero metodo.</span><span class="sxs-lookup"><span data-stu-id="53f8f-104">This scope encloses the entire method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="53f8f-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="53f8f-105">Syntax</span></span>  
  
```  
HRESULT GetRootScope(  
    [out, retval] ISymUnmanagedScope** pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="53f8f-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="53f8f-106">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="53f8f-107">[out] Un puntatore che viene impostato sull'oggetto restituito [ISymUnmanagedScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md) interfaccia.</span><span class="sxs-lookup"><span data-stu-id="53f8f-107">[out] A pointer that is set to the returned [ISymUnmanagedScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="53f8f-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="53f8f-108">Return Value</span></span>  
 <span data-ttu-id="53f8f-109">S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o qualche altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="53f8f-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="53f8f-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="53f8f-110">Requirements</span></span>  
 <span data-ttu-id="53f8f-111">**Intestazione:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="53f8f-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="53f8f-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="53f8f-112">See also</span></span>

- [<span data-ttu-id="53f8f-113">Interfaccia ISymUnmanagedMethod</span><span class="sxs-lookup"><span data-stu-id="53f8f-113">ISymUnmanagedMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md)
