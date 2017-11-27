---
title: Metodo ISymUnmanagedWriter5::MapTokenToSourceSpan
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: d0fbbf61-71c6-4fb1-8c9f-d619ca5d7d68
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: adcdf44582aaf801a39c9beb9831c493a9945fd0
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="isymunmanagedwriter5maptokentosourcespan-method"></a><span data-ttu-id="f3302-102">Metodo ISymUnmanagedWriter5::MapTokenToSourceSpan</span><span class="sxs-lookup"><span data-stu-id="f3302-102">ISymUnmanagedWriter5::MapTokenToSourceSpan Method</span></span>
<span data-ttu-id="f3302-103">Le mappe sono estese al token di metadati specificato alla riga di origine specificato nel file di origine specificato.</span><span class="sxs-lookup"><span data-stu-id="f3302-103">Maps the given metadata token to the given source line span in the specified source file.</span></span>  
  
 <span data-ttu-id="f3302-104">Deve essere chiamato tra le chiamate a [metodo OpenMapTokensToSourceSpans](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-openmaptokenstosourcespans-method.md) e [metodo CloseMapTokensToSourceSpans](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-closemaptokenstosourcespans-method.md).</span><span class="sxs-lookup"><span data-stu-id="f3302-104">Must be called between calls to [OpenMapTokensToSourceSpans Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-openmaptokenstosourcespans-method.md) and [CloseMapTokensToSourceSpans Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-closemaptokenstosourcespans-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f3302-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f3302-105">Syntax</span></span>  
  
```idl  
HRESULT MapTokenToSourceSpan(    [in] mdToken token,    [in] ISymUnmanagedDocumentWriter* document,    [in] ULONG32 line,    [in] ULONG32 column,    [in] ULONG32 endLine,    [in] ULONG32 endColumn);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f3302-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="f3302-106">Parameters</span></span>  
  
|<span data-ttu-id="f3302-107">Parametro</span><span class="sxs-lookup"><span data-stu-id="f3302-107">Parameter</span></span>|<span data-ttu-id="f3302-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f3302-108">Description</span></span>|  
|---------------|-----------------|  
|`token`||  
|`document`||  
|`line`||  
|`column`||  
|`endLine`||  
|`endColumn`||  
  
## <a name="return-value"></a><span data-ttu-id="f3302-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="f3302-109">Return Value</span></span>  
 <span data-ttu-id="f3302-110">Restituisce `HRESULT`.</span><span class="sxs-lookup"><span data-stu-id="f3302-110">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f3302-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f3302-111">Requirements</span></span>  
 <span data-ttu-id="f3302-112">**Intestazione:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="f3302-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f3302-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f3302-113">See Also</span></span>  
 [<span data-ttu-id="f3302-114">Interfaccia ISymUnmanagedWriter5</span><span class="sxs-lookup"><span data-stu-id="f3302-114">ISymUnmanagedWriter5 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-interface.md)
