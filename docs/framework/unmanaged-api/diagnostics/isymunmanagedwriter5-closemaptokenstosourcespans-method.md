---
title: Metodo ISymUnmanagedWriter5::CloseMapTokensToSourceSpans
ms.date: 03/30/2017
ms.assetid: f8a0c0a2-a11d-436c-aa85-bc110215cfd6
ms.openlocfilehash: 43c35596d31842b85bbdc96a63413a176a59a172
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73121646"
---
# <a name="isymunmanagedwriter5closemaptokenstosourcespans-method"></a><span data-ttu-id="d0324-102">Metodo ISymUnmanagedWriter5::CloseMapTokensToSourceSpans</span><span class="sxs-lookup"><span data-stu-id="d0324-102">ISymUnmanagedWriter5::CloseMapTokensToSourceSpans Method</span></span>
<span data-ttu-id="d0324-103">Chiudere la sezione relativa ai dati personalizzati speciali per informazioni sul mapping di intervalli da token a origine.</span><span class="sxs-lookup"><span data-stu-id="d0324-103">Close the special custom data section for token-to-source span mapping information.</span></span> <span data-ttu-id="d0324-104">Al termine della chiusura, non è possibile aggiungere altre informazioni sul mapping.</span><span class="sxs-lookup"><span data-stu-id="d0324-104">After it is closed, no more mapping information can be added.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d0324-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d0324-105">Syntax</span></span>  
  
```idl  
HRESULT CloseMapTokensToSourceSpans();  
```  
  
## <a name="return-value"></a><span data-ttu-id="d0324-106">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="d0324-106">Return Value</span></span>  
 <span data-ttu-id="d0324-107">Restituisce `HRESULT`.</span><span class="sxs-lookup"><span data-stu-id="d0324-107">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d0324-108">Requisiti</span><span class="sxs-lookup"><span data-stu-id="d0324-108">Requirements</span></span>  
 <span data-ttu-id="d0324-109">**Intestazione:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="d0324-109">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d0324-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d0324-110">See also</span></span>

- [<span data-ttu-id="d0324-111">Interfaccia ISymUnmanagedWriter5</span><span class="sxs-lookup"><span data-stu-id="d0324-111">ISymUnmanagedWriter5 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-interface.md)
