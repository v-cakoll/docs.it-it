---
title: Metodo ISymUnmanagedWriter5::CloseMapTokensToSourceSpans
ms.date: 03/30/2017
ms.assetid: f8a0c0a2-a11d-436c-aa85-bc110215cfd6
ms.openlocfilehash: 053727604c795bf43a9b1658d5841fe85f53090a
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83614630"
---
# <a name="isymunmanagedwriter5closemaptokenstosourcespans-method"></a><span data-ttu-id="c5516-102">Metodo ISymUnmanagedWriter5::CloseMapTokensToSourceSpans</span><span class="sxs-lookup"><span data-stu-id="c5516-102">ISymUnmanagedWriter5::CloseMapTokensToSourceSpans Method</span></span>
<span data-ttu-id="c5516-103">Chiudere la sezione relativa ai dati personalizzati speciali per informazioni sul mapping di intervalli da token a origine.</span><span class="sxs-lookup"><span data-stu-id="c5516-103">Close the special custom data section for token-to-source span mapping information.</span></span> <span data-ttu-id="c5516-104">Al termine della chiusura, non è possibile aggiungere altre informazioni sul mapping.</span><span class="sxs-lookup"><span data-stu-id="c5516-104">After it is closed, no more mapping information can be added.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c5516-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c5516-105">Syntax</span></span>  
  
```idl  
HRESULT CloseMapTokensToSourceSpans();  
```  
  
## <a name="return-value"></a><span data-ttu-id="c5516-106">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="c5516-106">Return Value</span></span>  
 <span data-ttu-id="c5516-107">Restituisce `HRESULT`.</span><span class="sxs-lookup"><span data-stu-id="c5516-107">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c5516-108">Requisiti</span><span class="sxs-lookup"><span data-stu-id="c5516-108">Requirements</span></span>  
 <span data-ttu-id="c5516-109">**Intestazione:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="c5516-109">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c5516-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c5516-110">See also</span></span>

- [<span data-ttu-id="c5516-111">Interfaccia ISymUnmanagedWriter5</span><span class="sxs-lookup"><span data-stu-id="c5516-111">ISymUnmanagedWriter5 Interface</span></span>](isymunmanagedwriter5-interface.md)
