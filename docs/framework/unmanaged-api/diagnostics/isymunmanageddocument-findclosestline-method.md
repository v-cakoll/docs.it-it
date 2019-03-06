---
title: Metodo ISymUnmanagedDocument::FindClosestLine
ms.date: 03/30/2017
api_name:
- ISymUnmanagedDocument.FindClosestLine
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedDocument::FindClosestLine
helpviewer_keywords:
- FindClosestLine method [.NET Framework debugging]
- ISymUnmanagedDocument::FindClosestLine method [.NET Framework debugging]
ms.assetid: 628f2a04-e529-407d-841e-3b3da219a9cb
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 760a6feb8400e60b7e14bf244d66c9026031e5dc
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57474237"
---
# <a name="isymunmanageddocumentfindclosestline-method"></a><span data-ttu-id="f22a9-102">Metodo ISymUnmanagedDocument::FindClosestLine</span><span class="sxs-lookup"><span data-stu-id="f22a9-102">ISymUnmanagedDocument::FindClosestLine Method</span></span>
<span data-ttu-id="f22a9-103">Restituisce la riga più vicina che rappresenta un punto di sequenza, data una riga in questo documento che possa o non sia un punto di sequenza.</span><span class="sxs-lookup"><span data-stu-id="f22a9-103">Returns the closest line that is a sequence point, given a line in this document that may or may not be a sequence point.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f22a9-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f22a9-104">Syntax</span></span>  
  
```  
HRESULT FindClosestLine(  
    [in]  ULONG32  line,  
    [out, retval] ULONG32*  pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f22a9-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="f22a9-105">Parameters</span></span>  
 `line`  
 <span data-ttu-id="f22a9-106">[in] Una riga in questo documento.</span><span class="sxs-lookup"><span data-stu-id="f22a9-106">[in] A line in this document.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="f22a9-107">[out] Puntatore a una variabile che riceve la riga.</span><span class="sxs-lookup"><span data-stu-id="f22a9-107">[out] A pointer to a variable that receives the line.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f22a9-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="f22a9-108">Return Value</span></span>  
 <span data-ttu-id="f22a9-109">S_OK se il metodo ha esito positivo; in caso contrario, un codice di errore.</span><span class="sxs-lookup"><span data-stu-id="f22a9-109">S_OK if the method succeeds; otherwise, an error code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f22a9-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f22a9-110">See also</span></span>
- [<span data-ttu-id="f22a9-111">Interfaccia ISymUnmanagedDocument</span><span class="sxs-lookup"><span data-stu-id="f22a9-111">ISymUnmanagedDocument Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-interface.md)
