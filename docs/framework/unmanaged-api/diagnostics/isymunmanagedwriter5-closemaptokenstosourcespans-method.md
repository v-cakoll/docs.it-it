---
title: Metodo ISymUnmanagedWriter5::CloseMapTokensToSourceSpans
ms.date: 03/30/2017
ms.assetid: f8a0c0a2-a11d-436c-aa85-bc110215cfd6
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 653dd933066898c1954cfbcc57c0c0493e47b4be
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33428612"
---
# <a name="isymunmanagedwriter5closemaptokenstosourcespans-method"></a><span data-ttu-id="a087c-102">Metodo ISymUnmanagedWriter5::CloseMapTokensToSourceSpans</span><span class="sxs-lookup"><span data-stu-id="a087c-102">ISymUnmanagedWriter5::CloseMapTokensToSourceSpans Method</span></span>
<span data-ttu-id="a087c-103">Chiudere la sezione di dati personalizzati speciali per le informazioni di mapping span di token all'origine.</span><span class="sxs-lookup"><span data-stu-id="a087c-103">Close the special custom data section for token-to-source span mapping information.</span></span> <span data-ttu-id="a087c-104">Dopo che è stato chiuso, è possibile aggiungere alcun altre informazioni di mapping.</span><span class="sxs-lookup"><span data-stu-id="a087c-104">After it is closed, no more mapping information can be added.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a087c-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a087c-105">Syntax</span></span>  
  
```idl  
HRESULT CloseMapTokensToSourceSpans();  
```  
  
## <a name="return-value"></a><span data-ttu-id="a087c-106">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="a087c-106">Return Value</span></span>  
 <span data-ttu-id="a087c-107">Restituisce `HRESULT`.</span><span class="sxs-lookup"><span data-stu-id="a087c-107">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a087c-108">Requisiti</span><span class="sxs-lookup"><span data-stu-id="a087c-108">Requirements</span></span>  
 <span data-ttu-id="a087c-109">**Intestazione:** CorSym. idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="a087c-109">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a087c-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a087c-110">See Also</span></span>  
 [<span data-ttu-id="a087c-111">Interfaccia ISymUnmanagedWriter5</span><span class="sxs-lookup"><span data-stu-id="a087c-111">ISymUnmanagedWriter5 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-interface.md)
