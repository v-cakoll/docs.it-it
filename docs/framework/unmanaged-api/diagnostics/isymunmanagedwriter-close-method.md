---
title: Metodo ISymUnmanagedWriter::Close
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 70f710802862c3237cbd67693f8366946926891e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedwriterclose-method"></a><span data-ttu-id="fc39c-102">Metodo ISymUnmanagedWriter::Close</span><span class="sxs-lookup"><span data-stu-id="fc39c-102">ISymUnmanagedWriter::Close Method</span></span>
<span data-ttu-id="fc39c-103">Chiude il writer di simboli dopo il commit i simboli per l'archivio dei simboli.</span><span class="sxs-lookup"><span data-stu-id="fc39c-103">Closes the symbol writer after committing the symbols to the symbol store.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fc39c-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="fc39c-104">Syntax</span></span>  
  
```  
HRESULT Close();  
```  
  
## <a name="return-value"></a><span data-ttu-id="fc39c-105">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="fc39c-105">Return Value</span></span>  
 <span data-ttu-id="fc39c-106">S_OK se il metodo ha esito positivo. in caso contrario, E_FAIL o un altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="fc39c-106">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fc39c-107">Note</span><span class="sxs-lookup"><span data-stu-id="fc39c-107">Remarks</span></span>  
 <span data-ttu-id="fc39c-108">Dopo questa chiamata, il writer di simboli diventa non valido per ulteriori aggiornamenti.</span><span class="sxs-lookup"><span data-stu-id="fc39c-108">After this call, the symbol writer becomes invalid for further updates.</span></span> <span data-ttu-id="fc39c-109">Per chiudere il writer di simboli senza eseguire il commit i simboli, utilizzare il [ISymUnmanagedWriter:: Abort](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-abort-method.md) metodo invece.</span><span class="sxs-lookup"><span data-stu-id="fc39c-109">To close the symbol writer without committing the symbols, use the [ISymUnmanagedWriter::Abort](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-abort-method.md) method instead.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fc39c-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="fc39c-110">Requirements</span></span>  
 <span data-ttu-id="fc39c-111">**Intestazione:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="fc39c-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fc39c-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fc39c-112">See Also</span></span>  
 [<span data-ttu-id="fc39c-113">Interfaccia ISymUnmanagedWriter</span><span class="sxs-lookup"><span data-stu-id="fc39c-113">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
