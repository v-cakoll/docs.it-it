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
ms.openlocfilehash: f531b96211a1dd6072d62937b9f93fc17f105d4d
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59149045"
---
# <a name="isymunmanagedwriter3commit-method"></a><span data-ttu-id="5b0de-102">Metodo ISymUnmanagedWriter3::Commit</span><span class="sxs-lookup"><span data-stu-id="5b0de-102">ISymUnmanagedWriter3::Commit Method</span></span>
<span data-ttu-id="5b0de-103">Conferma le modifiche apportate finora scritte nel flusso.</span><span class="sxs-lookup"><span data-stu-id="5b0de-103">Commits the changes written so far to the stream.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5b0de-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5b0de-104">Syntax</span></span>  
  
```  
HRESULT Commit();  
```  
  
## <a name="return-value"></a><span data-ttu-id="5b0de-105">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="5b0de-105">Return Value</span></span>  
 <span data-ttu-id="5b0de-106">S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o qualche altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="5b0de-106">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5b0de-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="5b0de-107">Requirements</span></span>  
 <span data-ttu-id="5b0de-108">**Intestazione:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="5b0de-108">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5b0de-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5b0de-109">See also</span></span>

- [<span data-ttu-id="5b0de-110">Interfaccia ISymUnmanagedWriter3</span><span class="sxs-lookup"><span data-stu-id="5b0de-110">ISymUnmanagedWriter3 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter3-interface.md)
