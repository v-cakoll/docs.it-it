---
title: Metodo ISymUnmanagedWriter5::MapTokenToSourceSpan
ms.date: 03/30/2017
ms.assetid: d0fbbf61-71c6-4fb1-8c9f-d619ca5d7d68
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 158ff204d57c3b08ced91d397ef71f24c5f44248
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54499210"
---
# <a name="isymunmanagedwriter5maptokentosourcespan-method"></a><span data-ttu-id="f8d47-102">Metodo ISymUnmanagedWriter5::MapTokenToSourceSpan</span><span class="sxs-lookup"><span data-stu-id="f8d47-102">ISymUnmanagedWriter5::MapTokenToSourceSpan Method</span></span>
<span data-ttu-id="f8d47-103">Mappe estendono il token di metadati specificati alla riga di origine specificato nel file di origine specificato.</span><span class="sxs-lookup"><span data-stu-id="f8d47-103">Maps the given metadata token to the given source line span in the specified source file.</span></span>  
  
 <span data-ttu-id="f8d47-104">Deve essere chiamato tra le chiamate a [metodo OpenMapTokensToSourceSpans](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-openmaptokenstosourcespans-method.md) e [metodo CloseMapTokensToSourceSpans](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-closemaptokenstosourcespans-method.md).</span><span class="sxs-lookup"><span data-stu-id="f8d47-104">Must be called between calls to [OpenMapTokensToSourceSpans Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-openmaptokenstosourcespans-method.md) and [CloseMapTokensToSourceSpans Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-closemaptokenstosourcespans-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f8d47-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f8d47-105">Syntax</span></span>  
  
```idl  
HRESULT MapTokenToSourceSpan(    [in] mdToken token,    [in] ISymUnmanagedDocumentWriter* document,    [in] ULONG32 line,    [in] ULONG32 column,    [in] ULONG32 endLine,    [in] ULONG32 endColumn);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f8d47-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="f8d47-106">Parameters</span></span>  
  
|<span data-ttu-id="f8d47-107">Parametro</span><span class="sxs-lookup"><span data-stu-id="f8d47-107">Parameter</span></span>|<span data-ttu-id="f8d47-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f8d47-108">Description</span></span>|  
|---------------|-----------------|  
|`token`||  
|`document`||  
|`line`||  
|`column`||  
|`endLine`||  
|`endColumn`||  
  
## <a name="return-value"></a><span data-ttu-id="f8d47-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="f8d47-109">Return Value</span></span>  
 <span data-ttu-id="f8d47-110">Restituisce `HRESULT`.</span><span class="sxs-lookup"><span data-stu-id="f8d47-110">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f8d47-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f8d47-111">Requirements</span></span>  
 <span data-ttu-id="f8d47-112">**Intestazione:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="f8d47-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f8d47-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f8d47-113">See also</span></span>
- [<span data-ttu-id="f8d47-114">Interfaccia ISymUnmanagedWriter5</span><span class="sxs-lookup"><span data-stu-id="f8d47-114">ISymUnmanagedWriter5 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-interface.md)
