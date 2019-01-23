---
title: Metodo ISymUnmanagedWriter3::Commit
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter3.Commit
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter3::Commit
helpviewer_keywords:
- Commit method, ISymUnmanagedWriter3 interface [.NET Framework debugging]
- ISymUnmanagedWriter3::Commit method [.NET Framework debugging]
ms.assetid: f6961922-46ec-4d2c-8369-85f880731f37
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 90ef45650b30fd57fb93d0e16eac6e34079745b1
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54526236"
---
# <a name="isymunmanagedwriter3commit-method"></a><span data-ttu-id="2d5ff-102">Metodo ISymUnmanagedWriter3::Commit</span><span class="sxs-lookup"><span data-stu-id="2d5ff-102">ISymUnmanagedWriter3::Commit Method</span></span>
<span data-ttu-id="2d5ff-103">Conferma le modifiche apportate finora scritte nel flusso.</span><span class="sxs-lookup"><span data-stu-id="2d5ff-103">Commits the changes written so far to the stream.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2d5ff-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2d5ff-104">Syntax</span></span>  
  
```  
HRESULT Commit();  
```  
  
## <a name="return-value"></a><span data-ttu-id="2d5ff-105">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="2d5ff-105">Return Value</span></span>  
 <span data-ttu-id="2d5ff-106">S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o qualche altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="2d5ff-106">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2d5ff-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="2d5ff-107">Requirements</span></span>  
 <span data-ttu-id="2d5ff-108">**Intestazione:** CorSym.idl , CorSym.h</span><span class="sxs-lookup"><span data-stu-id="2d5ff-108">**Header:** CorSym.idl , CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2d5ff-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2d5ff-109">See also</span></span>
- [<span data-ttu-id="2d5ff-110">Interfaccia ISymUnmanagedWriter3</span><span class="sxs-lookup"><span data-stu-id="2d5ff-110">ISymUnmanagedWriter3 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter3-interface.md)
