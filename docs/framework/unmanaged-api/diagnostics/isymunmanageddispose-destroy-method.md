---
title: Metodo ISymUnmanagedDispose::Destroy
ms.date: 03/30/2017
api_name:
- ISymUnmanagedDispose.Destroy
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedDispose::Destroy
helpviewer_keywords:
- ISymUnmanagedDispose::Destroy method [.NET Framework debugging]
- Destroy method [.NET Framework debugging]
ms.assetid: a854ab9f-d2ba-470e-867f-808c1e7bd07a
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 51d2f0aedffdd88974a8184954ecbb9a231b70c6
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61939945"
---
# <a name="isymunmanageddisposedestroy-method"></a><span data-ttu-id="0cbed-102">Metodo ISymUnmanagedDispose::Destroy</span><span class="sxs-lookup"><span data-stu-id="0cbed-102">ISymUnmanagedDispose::Destroy Method</span></span>
<span data-ttu-id="0cbed-103">Fa sì che l'oggetto sottostante rilasciare tutti i riferimenti interni e restituito un errore in tutte le chiamate successive.</span><span class="sxs-lookup"><span data-stu-id="0cbed-103">Causes the underlying object to release all internal references and return failure on any subsequent method calls.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0cbed-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0cbed-104">Syntax</span></span>  
  
```  
HRESULT Destroy();  
```  
  
## <a name="return-value"></a><span data-ttu-id="0cbed-105">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="0cbed-105">Return Value</span></span>  
 <span data-ttu-id="0cbed-106">S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o qualche altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="0cbed-106">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0cbed-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="0cbed-107">Requirements</span></span>  
 <span data-ttu-id="0cbed-108">**Intestazione:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="0cbed-108">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0cbed-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0cbed-109">See also</span></span>

- [<span data-ttu-id="0cbed-110">Interfaccia ISymUnmanagedDispose</span><span class="sxs-lookup"><span data-stu-id="0cbed-110">ISymUnmanagedDispose Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddispose-interface.md)
