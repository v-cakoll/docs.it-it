---
title: Metodo ISymUnmanagedWriter::Close
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.Close
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::Close
helpviewer_keywords:
- Close method, ISymUnmanagedWriter interface [.NET Framework debugging]
- ISymUnmanagedWriter::Close method [.NET Framework debugging]
ms.assetid: 4cce59e1-80b9-4fc4-b3aa-126f1c5876bc
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 4d3497d3167715d3e8a04f10a6687260949e4a36
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59104702"
---
# <a name="isymunmanagedwriterclose-method"></a><span data-ttu-id="df6f3-102">Metodo ISymUnmanagedWriter::Close</span><span class="sxs-lookup"><span data-stu-id="df6f3-102">ISymUnmanagedWriter::Close Method</span></span>
<span data-ttu-id="df6f3-103">Chiude il writer di simboli dopo il commit i simboli per l'archivio dei simboli.</span><span class="sxs-lookup"><span data-stu-id="df6f3-103">Closes the symbol writer after committing the symbols to the symbol store.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="df6f3-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="df6f3-104">Syntax</span></span>  
  
```  
HRESULT Close();  
```  
  
## <a name="return-value"></a><span data-ttu-id="df6f3-105">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="df6f3-105">Return Value</span></span>  
 <span data-ttu-id="df6f3-106">S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o qualche altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="df6f3-106">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="df6f3-107">Note</span><span class="sxs-lookup"><span data-stu-id="df6f3-107">Remarks</span></span>  
 <span data-ttu-id="df6f3-108">Dopo questa chiamata, il writer di simboli viene invalidato per altri aggiornamenti.</span><span class="sxs-lookup"><span data-stu-id="df6f3-108">After this call, the symbol writer becomes invalid for further updates.</span></span> <span data-ttu-id="df6f3-109">Per chiudere il writer di simboli senza eseguire il commit i simboli, usare il [ISymUnmanagedWriter](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-abort-method.md) metodo invece.</span><span class="sxs-lookup"><span data-stu-id="df6f3-109">To close the symbol writer without committing the symbols, use the [ISymUnmanagedWriter::Abort](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-abort-method.md) method instead.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="df6f3-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="df6f3-110">Requirements</span></span>  
 <span data-ttu-id="df6f3-111">**Intestazione:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="df6f3-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="df6f3-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="df6f3-112">See also</span></span>

- [<span data-ttu-id="df6f3-113">Interfaccia ISymUnmanagedWriter</span><span class="sxs-lookup"><span data-stu-id="df6f3-113">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
