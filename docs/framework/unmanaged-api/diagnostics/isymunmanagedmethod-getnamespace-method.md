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
ms.openlocfilehash: b8bbedb4c60a2df6070373f2b6a104fff094869a
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74448974"
---
# <a name="isymunmanagedmethodgetnamespace-method"></a><span data-ttu-id="f2d6c-102">Metodo ISymUnmanagedMethod::GetNamespace</span><span class="sxs-lookup"><span data-stu-id="f2d6c-102">ISymUnmanagedMethod::GetNamespace Method</span></span>
<span data-ttu-id="f2d6c-103">Ottiene lo spazio dei nomi in cui è definito il metodo.</span><span class="sxs-lookup"><span data-stu-id="f2d6c-103">Gets the namespace within which this method is defined.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f2d6c-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f2d6c-104">Syntax</span></span>  
  
```cpp  
HRESULT GetNamespace(  
   [out] ISymUnmanagedNamespace  **pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f2d6c-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="f2d6c-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="f2d6c-106">out Puntatore impostato sull'interfaccia [ISymUnmanagedNamespace](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagednamespace-interface.md) restituita.</span><span class="sxs-lookup"><span data-stu-id="f2d6c-106">[out] A pointer that is set to the returned [ISymUnmanagedNamespace](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagednamespace-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f2d6c-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="f2d6c-107">Return Value</span></span>  
 <span data-ttu-id="f2d6c-108">S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o un altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="f2d6c-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f2d6c-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f2d6c-109">Requirements</span></span>  
 <span data-ttu-id="f2d6c-110">**Intestazione:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="f2d6c-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f2d6c-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f2d6c-111">See also</span></span>

- [<span data-ttu-id="f2d6c-112">Interfaccia ISymUnmanagedMethod</span><span class="sxs-lookup"><span data-stu-id="f2d6c-112">ISymUnmanagedMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md)
