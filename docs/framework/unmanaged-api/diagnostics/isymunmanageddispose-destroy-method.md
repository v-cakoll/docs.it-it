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
ms.openlocfilehash: 23228c1414f5f6327cfb326c95a3224ae231a033
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67776778"
---
# <a name="isymunmanageddisposedestroy-method"></a><span data-ttu-id="6b14f-102">Metodo ISymUnmanagedDispose::Destroy</span><span class="sxs-lookup"><span data-stu-id="6b14f-102">ISymUnmanagedDispose::Destroy Method</span></span>
<span data-ttu-id="6b14f-103">Fa sì che l'oggetto sottostante rilasciare tutti i riferimenti interni e restituito un errore in tutte le chiamate successive.</span><span class="sxs-lookup"><span data-stu-id="6b14f-103">Causes the underlying object to release all internal references and return failure on any subsequent method calls.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6b14f-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6b14f-104">Syntax</span></span>  
  
```cpp  
HRESULT Destroy();  
```  
  
## <a name="return-value"></a><span data-ttu-id="6b14f-105">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="6b14f-105">Return Value</span></span>  
 <span data-ttu-id="6b14f-106">S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o qualche altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="6b14f-106">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6b14f-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="6b14f-107">Requirements</span></span>  
 <span data-ttu-id="6b14f-108">**Intestazione:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="6b14f-108">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6b14f-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6b14f-109">See also</span></span>

- [<span data-ttu-id="6b14f-110">Interfaccia ISymUnmanagedDispose</span><span class="sxs-lookup"><span data-stu-id="6b14f-110">ISymUnmanagedDispose Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddispose-interface.md)
