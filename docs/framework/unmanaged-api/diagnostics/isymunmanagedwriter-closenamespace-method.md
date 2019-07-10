---
title: Metodo ISymUnmanagedWriter::CloseNamespace
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.CloseNamespace
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::CloseNamespace
helpviewer_keywords:
- ISymUnmanagedWriter::CloseNamespace method [.NET Framework debugging]
- CloseNamespace method [.NET Framework debugging]
ms.assetid: 7f74d9c5-1377-4958-b842-6306d611cbd5
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3ed618847d398bb4dcccb8ecebabdc947390c874
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67778171"
---
# <a name="isymunmanagedwriterclosenamespace-method"></a><span data-ttu-id="1d9da-102">Metodo ISymUnmanagedWriter::CloseNamespace</span><span class="sxs-lookup"><span data-stu-id="1d9da-102">ISymUnmanagedWriter::CloseNamespace Method</span></span>
<span data-ttu-id="1d9da-103">Chiude l'ultimo aperto lo spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="1d9da-103">Closes the most recently opened namespace.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1d9da-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1d9da-104">Syntax</span></span>  
  
```cpp  
HRESULT CloseNamespace();  
```  
  
## <a name="return-value"></a><span data-ttu-id="1d9da-105">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="1d9da-105">Return Value</span></span>  
 <span data-ttu-id="1d9da-106">S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o qualche altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="1d9da-106">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1d9da-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="1d9da-107">Requirements</span></span>  
 <span data-ttu-id="1d9da-108">**Intestazione:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="1d9da-108">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1d9da-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1d9da-109">See also</span></span>

- [<span data-ttu-id="1d9da-110">Interfaccia ISymUnmanagedWriter</span><span class="sxs-lookup"><span data-stu-id="1d9da-110">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
- [<span data-ttu-id="1d9da-111">Metodo OpenNamespace</span><span class="sxs-lookup"><span data-stu-id="1d9da-111">OpenNamespace Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-opennamespace-method.md)
