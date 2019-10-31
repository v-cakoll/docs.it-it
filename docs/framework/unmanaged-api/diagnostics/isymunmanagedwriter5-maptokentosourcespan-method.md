---
title: Metodo ISymUnmanagedWriter5::MapTokenToSourceSpan
ms.date: 03/30/2017
ms.assetid: d0fbbf61-71c6-4fb1-8c9f-d619ca5d7d68
ms.openlocfilehash: 876804e7b825443116b1f44a02a685a73153915c
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73121631"
---
# <a name="isymunmanagedwriter5maptokentosourcespan-method"></a><span data-ttu-id="8f23b-102">Metodo ISymUnmanagedWriter5::MapTokenToSourceSpan</span><span class="sxs-lookup"><span data-stu-id="8f23b-102">ISymUnmanagedWriter5::MapTokenToSourceSpan Method</span></span>
<span data-ttu-id="8f23b-103">Esegue il mapping del token di metadati specificato all'intervallo di righe di origine specificato nel file di origine specificato.</span><span class="sxs-lookup"><span data-stu-id="8f23b-103">Maps the given metadata token to the given source line span in the specified source file.</span></span>  
  
 <span data-ttu-id="8f23b-104">Deve essere chiamato tra le chiamate al [Metodo OpenMapTokensToSourceSpans](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-openmaptokenstosourcespans-method.md) e al [Metodo CloseMapTokensToSourceSpans](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-closemaptokenstosourcespans-method.md).</span><span class="sxs-lookup"><span data-stu-id="8f23b-104">Must be called between calls to [OpenMapTokensToSourceSpans Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-openmaptokenstosourcespans-method.md) and [CloseMapTokensToSourceSpans Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-closemaptokenstosourcespans-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8f23b-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8f23b-105">Syntax</span></span>  
  
```idl  
HRESULT MapTokenToSourceSpan(    [in] mdToken token,    [in] ISymUnmanagedDocumentWriter* document,    [in] ULONG32 line,    [in] ULONG32 column,    [in] ULONG32 endLine,    [in] ULONG32 endColumn);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8f23b-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="8f23b-106">Parameters</span></span>  
  
|<span data-ttu-id="8f23b-107">Parametro</span><span class="sxs-lookup"><span data-stu-id="8f23b-107">Parameter</span></span>|<span data-ttu-id="8f23b-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8f23b-108">Description</span></span>|  
|---------------|-----------------|  
|`token`||  
|`document`||  
|`line`||  
|`column`||  
|`endLine`||  
|`endColumn`||  
  
## <a name="return-value"></a><span data-ttu-id="8f23b-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="8f23b-109">Return Value</span></span>  
 <span data-ttu-id="8f23b-110">Restituisce `HRESULT`.</span><span class="sxs-lookup"><span data-stu-id="8f23b-110">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8f23b-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="8f23b-111">Requirements</span></span>  
 <span data-ttu-id="8f23b-112">**Intestazione:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="8f23b-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8f23b-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8f23b-113">See also</span></span>

- [<span data-ttu-id="8f23b-114">Interfaccia ISymUnmanagedWriter5</span><span class="sxs-lookup"><span data-stu-id="8f23b-114">ISymUnmanagedWriter5 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-interface.md)
