---
title: Metodo ISymUnmanagedDocument::HasEmbeddedSource
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedDocument.HasEmbeddedSource
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedDocument::HasEmbeddedSource
helpviewer_keywords:
- HasEmbeddedSource method [.NET Framework debugging]
- ISymUnmanagedDocument::HasEmbeddedSource method [.NET Framework debugging]
ms.assetid: 385fc4d3-365c-4645-b7b0-6c4c5344b79f
topic_type: apiref
caps.latest.revision: "7"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f2a903974ac5ac4182bb6fa1664d0c5954cefdb0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanageddocumenthasembeddedsource-method"></a><span data-ttu-id="ae9ba-102">Metodo ISymUnmanagedDocument::HasEmbeddedSource</span><span class="sxs-lookup"><span data-stu-id="ae9ba-102">ISymUnmanagedDocument::HasEmbeddedSource Method</span></span>
<span data-ttu-id="ae9ba-103">Restituisce `true` se il documento di origine è incorporata nei simboli di debug; in caso contrario, restituisce `false`.</span><span class="sxs-lookup"><span data-stu-id="ae9ba-103">Returns `true` if the document has source embedded in the debugging symbols; otherwise, returns `false`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ae9ba-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ae9ba-104">Syntax</span></span>  
  
```  
HRESULT HasEmbeddedSource(  
   [out, retval]  BOOL  *pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ae9ba-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="ae9ba-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="ae9ba-106">[out] Un puntatore a una variabile che indica se il documento di origine è incorporata nei simboli di debug.</span><span class="sxs-lookup"><span data-stu-id="ae9ba-106">[out] A pointer to a variable that indicates whether the document has source embedded in the debugging symbols.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ae9ba-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="ae9ba-107">Return Value</span></span>  
 <span data-ttu-id="ae9ba-108">S_OK se il metodo ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="ae9ba-108">S_OK if the method succeeds.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ae9ba-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ae9ba-109">See Also</span></span>  
 [<span data-ttu-id="ae9ba-110">Interfaccia ISymUnmanagedDocument</span><span class="sxs-lookup"><span data-stu-id="ae9ba-110">ISymUnmanagedDocument Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-interface.md)
