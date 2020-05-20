---
title: Metodo ISymUnmanagedWriter::Abort
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.Abort
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::Abort
helpviewer_keywords:
- ISymUnmanagedWriter::Abort method [.NET Framework debugging]
- Abort method, ISymUnmanagedWriter interface [.NET Framework debugging]
ms.assetid: 416b220f-38d4-48e0-bb49-d2faa7366702
topic_type:
- apiref
ms.openlocfilehash: 09f39d3b6486e2ec3c04c5d1858a85ce56895527
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83610158"
---
# <a name="isymunmanagedwriterabort-method"></a><span data-ttu-id="c496b-102">Metodo ISymUnmanagedWriter::Abort</span><span class="sxs-lookup"><span data-stu-id="c496b-102">ISymUnmanagedWriter::Abort Method</span></span>
<span data-ttu-id="c496b-103">Chiude il writer di simboli senza eseguire il commit dei simboli nell'archivio dei simboli.</span><span class="sxs-lookup"><span data-stu-id="c496b-103">Closes the symbol writer without committing the symbols to the symbol store.</span></span> <span data-ttu-id="c496b-104">Dopo questa chiamata, il writer di simboli diventa non valido per ulteriori aggiornamenti.</span><span class="sxs-lookup"><span data-stu-id="c496b-104">After this call, the symbol writer becomes invalid for further updates.</span></span> <span data-ttu-id="c496b-105">Per eseguire il commit dei simboli e chiudere il writer di simboli, usare invece il metodo [ISymUnmanagedWriter:: Close](isymunmanagedwriter-close-method.md) .</span><span class="sxs-lookup"><span data-stu-id="c496b-105">To commit the symbols and close the symbol writer, use the [ISymUnmanagedWriter::Close](isymunmanagedwriter-close-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c496b-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c496b-106">Syntax</span></span>  
  
```cpp  
HRESULT Abort();  
```  
  
## <a name="return-value"></a><span data-ttu-id="c496b-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="c496b-107">Return Value</span></span>  
 <span data-ttu-id="c496b-108">S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o un altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="c496b-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c496b-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="c496b-109">Requirements</span></span>  
 <span data-ttu-id="c496b-110">**Intestazione:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="c496b-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c496b-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c496b-111">See also</span></span>

- [<span data-ttu-id="c496b-112">Interfaccia ISymUnmanagedWriter</span><span class="sxs-lookup"><span data-stu-id="c496b-112">ISymUnmanagedWriter Interface</span></span>](isymunmanagedwriter-interface.md)
