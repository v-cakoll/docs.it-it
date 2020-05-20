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
ms.openlocfilehash: 5bd94cb851d4bb044d4ce03b97d6342a2c9652e4
ms.sourcegitcommit: 7b1497c1927cb449cefd313bc5126ae37df30746
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/16/2020
ms.locfileid: "83441318"
---
# <a name="isymunmanageddisposedestroy-method"></a><span data-ttu-id="80d75-102">Metodo ISymUnmanagedDispose::Destroy</span><span class="sxs-lookup"><span data-stu-id="80d75-102">ISymUnmanagedDispose::Destroy Method</span></span>
<span data-ttu-id="80d75-103">Fa in modo che l'oggetto sottostante rilasci tutti i riferimenti interni e restituisca un errore in tutte le chiamate al metodo successive.</span><span class="sxs-lookup"><span data-stu-id="80d75-103">Causes the underlying object to release all internal references and return failure on any subsequent method calls.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="80d75-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="80d75-104">Syntax</span></span>  
  
```cpp  
HRESULT Destroy();  
```  
  
## <a name="return-value"></a><span data-ttu-id="80d75-105">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="80d75-105">Return Value</span></span>  
 <span data-ttu-id="80d75-106">S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o un altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="80d75-106">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="80d75-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="80d75-107">Requirements</span></span>  
 <span data-ttu-id="80d75-108">**Intestazione:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="80d75-108">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="80d75-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="80d75-109">See also</span></span>

- [<span data-ttu-id="80d75-110">Interfaccia ISymUnmanagedDispose</span><span class="sxs-lookup"><span data-stu-id="80d75-110">ISymUnmanagedDispose Interface</span></span>](isymunmanageddispose-interface.md)
