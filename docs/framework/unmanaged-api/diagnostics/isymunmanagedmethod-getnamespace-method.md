---
title: Metodo ISymUnmanagedMethod::GetNamespace
ms.date: 03/30/2017
api_name:
- ISymUnmanagedMethod.GetNamespace
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedMethod::GetNamespace
helpviewer_keywords:
- ISymUnmanagedMethod::GetNamespace method [.NET Framework debugging]
- GetNamespace method [.NET Framework debugging]
ms.assetid: 7fbbac42-b966-406d-9ae9-67bf3aea74ce
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 676c968bb48e493f9a4514235fbc3246cf395228
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67774654"
---
# <a name="isymunmanagedmethodgetnamespace-method"></a><span data-ttu-id="1e248-102">Metodo ISymUnmanagedMethod::GetNamespace</span><span class="sxs-lookup"><span data-stu-id="1e248-102">ISymUnmanagedMethod::GetNamespace Method</span></span>
<span data-ttu-id="1e248-103">Ottiene lo spazio dei nomi all'interno del quale questo metodo è definito.</span><span class="sxs-lookup"><span data-stu-id="1e248-103">Gets the namespace within which this method is defined.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1e248-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1e248-104">Syntax</span></span>  
  
```cpp  
HRESULT GetNamespace(  
   [out] ISymUnmanagedNamespace  **pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1e248-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="1e248-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="1e248-106">[out] Un puntatore che viene impostato sull'oggetto restituito [ISymUnmanagedNamespace](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagednamespace-interface.md) interfaccia.</span><span class="sxs-lookup"><span data-stu-id="1e248-106">[out] A pointer that is set to the returned [ISymUnmanagedNamespace](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagednamespace-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1e248-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="1e248-107">Return Value</span></span>  
 <span data-ttu-id="1e248-108">S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o qualche altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="1e248-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1e248-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="1e248-109">Requirements</span></span>  
 <span data-ttu-id="1e248-110">**Intestazione:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="1e248-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1e248-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1e248-111">See also</span></span>

- [<span data-ttu-id="1e248-112">Interfaccia ISymUnmanagedMethod</span><span class="sxs-lookup"><span data-stu-id="1e248-112">ISymUnmanagedMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md)
