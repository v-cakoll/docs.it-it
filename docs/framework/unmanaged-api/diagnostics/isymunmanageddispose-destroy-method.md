---
title: Metodo ISymUnmanagedDispose::Destroy
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedDispose.Destroy
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedDispose::Destroy
helpviewer_keywords:
- ISymUnmanagedDispose::Destroy method [.NET Framework debugging]
- Destroy method [.NET Framework debugging]
ms.assetid: a854ab9f-d2ba-470e-867f-808c1e7bd07a
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: d808392d883d1168d6aad8d16ab50ce072b1d9f7
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="isymunmanageddisposedestroy-method"></a><span data-ttu-id="e5dce-102">Metodo ISymUnmanagedDispose::Destroy</span><span class="sxs-lookup"><span data-stu-id="e5dce-102">ISymUnmanagedDispose::Destroy Method</span></span>
<span data-ttu-id="e5dce-103">Fa sì che l'oggetto sottostante rilasciare tutti i riferimenti interni e restituito un errore in tutte le chiamate successive.</span><span class="sxs-lookup"><span data-stu-id="e5dce-103">Causes the underlying object to release all internal references and return failure on any subsequent method calls.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e5dce-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e5dce-104">Syntax</span></span>  
  
```  
HRESULT Destroy();  
```  
  
## <a name="return-value"></a><span data-ttu-id="e5dce-105">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="e5dce-105">Return Value</span></span>  
 <span data-ttu-id="e5dce-106">S_OK se il metodo ha esito positivo. in caso contrario, E_FAIL o un altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="e5dce-106">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e5dce-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="e5dce-107">Requirements</span></span>  
 <span data-ttu-id="e5dce-108">**Intestazione:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="e5dce-108">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e5dce-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e5dce-109">See Also</span></span>  
 [<span data-ttu-id="e5dce-110">ISymUnmanagedDispose (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="e5dce-110">ISymUnmanagedDispose Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddispose-interface.md)
