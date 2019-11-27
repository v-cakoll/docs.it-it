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
ms.openlocfilehash: e930a9a3753ccf2b8aff798916c876fbedad4df4
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74430709"
---
# <a name="isymunmanageddisposedestroy-method"></a><span data-ttu-id="70aba-102">Metodo ISymUnmanagedDispose::Destroy</span><span class="sxs-lookup"><span data-stu-id="70aba-102">ISymUnmanagedDispose::Destroy Method</span></span>
<span data-ttu-id="70aba-103">Fa in modo che l'oggetto sottostante rilasci tutti i riferimenti interni e restituisca un errore in tutte le chiamate al metodo successive.</span><span class="sxs-lookup"><span data-stu-id="70aba-103">Causes the underlying object to release all internal references and return failure on any subsequent method calls.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="70aba-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="70aba-104">Syntax</span></span>  
  
```cpp  
HRESULT Destroy();  
```  
  
## <a name="return-value"></a><span data-ttu-id="70aba-105">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="70aba-105">Return Value</span></span>  
 <span data-ttu-id="70aba-106">S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o un altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="70aba-106">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="70aba-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="70aba-107">Requirements</span></span>  
 <span data-ttu-id="70aba-108">**Intestazione:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="70aba-108">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="70aba-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="70aba-109">See also</span></span>

- [<span data-ttu-id="70aba-110">Interfaccia ISymUnmanagedDispose</span><span class="sxs-lookup"><span data-stu-id="70aba-110">ISymUnmanagedDispose Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddispose-interface.md)
