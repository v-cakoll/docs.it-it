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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b4c79cb3df37a9ed10e46567be63aad29fee37c4
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54550188"
---
# <a name="isymunmanagedwriterabort-method"></a><span data-ttu-id="30dd3-102">Metodo ISymUnmanagedWriter::Abort</span><span class="sxs-lookup"><span data-stu-id="30dd3-102">ISymUnmanagedWriter::Abort Method</span></span>
<span data-ttu-id="30dd3-103">Chiude il writer di simboli senza eseguire il commit i simboli per l'archivio dei simboli.</span><span class="sxs-lookup"><span data-stu-id="30dd3-103">Closes the symbol writer without committing the symbols to the symbol store.</span></span> <span data-ttu-id="30dd3-104">Dopo questa chiamata, il writer di simboli viene invalidato per altri aggiornamenti.</span><span class="sxs-lookup"><span data-stu-id="30dd3-104">After this call, the symbol writer becomes invalid for further updates.</span></span> <span data-ttu-id="30dd3-105">Per eseguire il commit i simboli e chiudere il writer di simboli, usare il [ISymUnmanagedWriter](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-close-method.md) metodo invece.</span><span class="sxs-lookup"><span data-stu-id="30dd3-105">To commit the symbols and close the symbol writer, use the [ISymUnmanagedWriter::Close](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-close-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="30dd3-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="30dd3-106">Syntax</span></span>  
  
```  
HRESULT Abort();  
```  
  
## <a name="return-value"></a><span data-ttu-id="30dd3-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="30dd3-107">Return Value</span></span>  
 <span data-ttu-id="30dd3-108">S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o qualche altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="30dd3-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="30dd3-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="30dd3-109">Requirements</span></span>  
 <span data-ttu-id="30dd3-110">**Intestazione:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="30dd3-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="30dd3-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="30dd3-111">See also</span></span>
- [<span data-ttu-id="30dd3-112">Interfaccia ISymUnmanagedWriter</span><span class="sxs-lookup"><span data-stu-id="30dd3-112">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
