---
title: Metodo ISymUnmanagedMethod::GetRootScope
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: e7fe3d2934345fbc89b4a2c7747abb867a20df20
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedmethodgetrootscope-method"></a><span data-ttu-id="32a0c-102">Metodo ISymUnmanagedMethod::GetRootScope</span><span class="sxs-lookup"><span data-stu-id="32a0c-102">ISymUnmanagedMethod::GetRootScope Method</span></span>
<span data-ttu-id="32a0c-103">Ottiene l'ambito lessicale di primo livello all'interno del metodo.</span><span class="sxs-lookup"><span data-stu-id="32a0c-103">Gets the root lexical scope within this method.</span></span> <span data-ttu-id="32a0c-104">Questo ambito racchiude l'intero metodo.</span><span class="sxs-lookup"><span data-stu-id="32a0c-104">This scope encloses the entire method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="32a0c-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="32a0c-105">Syntax</span></span>  
  
```  
HRESULT GetRootScope(  
    [out, retval] ISymUnmanagedScope** pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="32a0c-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="32a0c-106">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="32a0c-107">[out] Un puntatore che viene impostato sull'oggetto restituito [ISymUnmanagedScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md) interfaccia.</span><span class="sxs-lookup"><span data-stu-id="32a0c-107">[out] A pointer that is set to the returned [ISymUnmanagedScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="32a0c-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="32a0c-108">Return Value</span></span>  
 <span data-ttu-id="32a0c-109">S_OK se il metodo ha esito positivo. in caso contrario, E_FAIL o un altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="32a0c-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="32a0c-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="32a0c-110">Requirements</span></span>  
 <span data-ttu-id="32a0c-111">**Intestazione:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="32a0c-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="32a0c-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="32a0c-112">See Also</span></span>  
 [<span data-ttu-id="32a0c-113">Interfaccia ISymUnmanagedMethod</span><span class="sxs-lookup"><span data-stu-id="32a0c-113">ISymUnmanagedMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md)
