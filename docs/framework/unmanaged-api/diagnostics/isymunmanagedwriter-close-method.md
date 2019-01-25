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
ms.openlocfilehash: 780c19acd3d6980c0fb3e31d01e569a61fd04d6d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54647309"
---
# <a name="isymunmanagedwriterclose-method"></a><span data-ttu-id="772f7-102">Metodo ISymUnmanagedWriter::Close</span><span class="sxs-lookup"><span data-stu-id="772f7-102">ISymUnmanagedWriter::Close Method</span></span>
<span data-ttu-id="772f7-103">Chiude il writer di simboli dopo il commit i simboli per l'archivio dei simboli.</span><span class="sxs-lookup"><span data-stu-id="772f7-103">Closes the symbol writer after committing the symbols to the symbol store.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="772f7-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="772f7-104">Syntax</span></span>  
  
```  
HRESULT Close();  
```  
  
## <a name="return-value"></a><span data-ttu-id="772f7-105">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="772f7-105">Return Value</span></span>  
 <span data-ttu-id="772f7-106">S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o qualche altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="772f7-106">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="772f7-107">Note</span><span class="sxs-lookup"><span data-stu-id="772f7-107">Remarks</span></span>  
 <span data-ttu-id="772f7-108">Dopo questa chiamata, il writer di simboli viene invalidato per altri aggiornamenti.</span><span class="sxs-lookup"><span data-stu-id="772f7-108">After this call, the symbol writer becomes invalid for further updates.</span></span> <span data-ttu-id="772f7-109">Per chiudere il writer di simboli senza eseguire il commit i simboli, usare il [ISymUnmanagedWriter](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-abort-method.md) metodo invece.</span><span class="sxs-lookup"><span data-stu-id="772f7-109">To close the symbol writer without committing the symbols, use the [ISymUnmanagedWriter::Abort](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-abort-method.md) method instead.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="772f7-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="772f7-110">Requirements</span></span>  
 <span data-ttu-id="772f7-111">**Intestazione:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="772f7-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="772f7-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="772f7-112">See also</span></span>
- [<span data-ttu-id="772f7-113">Interfaccia ISymUnmanagedWriter</span><span class="sxs-lookup"><span data-stu-id="772f7-113">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
