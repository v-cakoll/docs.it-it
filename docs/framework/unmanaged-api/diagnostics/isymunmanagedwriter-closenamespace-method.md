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
ms.openlocfilehash: 7a4ffc0c417ae839e5c97ffe6884bc3230a603b7
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83610106"
---
# <a name="isymunmanagedwriterclosenamespace-method"></a><span data-ttu-id="fdd47-102">Metodo ISymUnmanagedWriter::CloseNamespace</span><span class="sxs-lookup"><span data-stu-id="fdd47-102">ISymUnmanagedWriter::CloseNamespace Method</span></span>
<span data-ttu-id="fdd47-103">Chiude lo spazio dei nomi aperto più di recente.</span><span class="sxs-lookup"><span data-stu-id="fdd47-103">Closes the most recently opened namespace.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fdd47-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="fdd47-104">Syntax</span></span>  
  
```cpp  
HRESULT CloseNamespace();  
```  
  
## <a name="return-value"></a><span data-ttu-id="fdd47-105">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="fdd47-105">Return Value</span></span>  
 <span data-ttu-id="fdd47-106">S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o un altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="fdd47-106">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fdd47-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="fdd47-107">Requirements</span></span>  
 <span data-ttu-id="fdd47-108">**Intestazione:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="fdd47-108">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fdd47-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fdd47-109">See also</span></span>

- [<span data-ttu-id="fdd47-110">Interfaccia ISymUnmanagedWriter</span><span class="sxs-lookup"><span data-stu-id="fdd47-110">ISymUnmanagedWriter Interface</span></span>](isymunmanagedwriter-interface.md)
- [<span data-ttu-id="fdd47-111">Metodo OpenNamespace</span><span class="sxs-lookup"><span data-stu-id="fdd47-111">OpenNamespace Method</span></span>](isymunmanagedwriter-opennamespace-method.md)
