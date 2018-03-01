---
title: Metodo ISymUnmanagedWriter3::OpenMethod2
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
- ISymUnmanagedWriter3.OpenMethod2
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter3::OpenMethod2
helpviewer_keywords:
- ISymUnmanagedWriter3::OpenMethod2 method [.NET Framework debugging]
- OpenMethod2 method [.NET Framework debugging]
ms.assetid: 025e358c-448f-4423-a2f2-57acf437c8a5
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 8da6de0271ddce5b956e667420a206c09cc291d8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedwriter3openmethod2-method"></a><span data-ttu-id="79b6d-102">Metodo ISymUnmanagedWriter3::OpenMethod2</span><span class="sxs-lookup"><span data-stu-id="79b6d-102">ISymUnmanagedWriter3::OpenMethod2 Method</span></span>
<span data-ttu-id="79b6d-103">Apre un metodo e fornisce l'offset di sezione reale nell'immagine.</span><span class="sxs-lookup"><span data-stu-id="79b6d-103">Opens a method and provides its real section offset in the image.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="79b6d-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="79b6d-104">Syntax</span></span>  
  
```  
HRESULT OpenMethod2(   
    [in] mdMethodDef method,  
    [in] ULONG32 isect,  
    [in] ULONG32 offset);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="79b6d-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="79b6d-105">Parameters</span></span>  
 `method`  
 <span data-ttu-id="79b6d-106">[in] Il token di metadati per il metodo da aprire.</span><span class="sxs-lookup"><span data-stu-id="79b6d-106">[in] The metadata token for the method to be opened.</span></span>  
  
 `isect`  
 <span data-ttu-id="79b6d-107">[in] L'offset della sezione dell'immagine.</span><span class="sxs-lookup"><span data-stu-id="79b6d-107">[in] The section offset in the image.</span></span>  
  
 `offset`  
 <span data-ttu-id="79b6d-108">[in] Offset nell'immagine.</span><span class="sxs-lookup"><span data-stu-id="79b6d-108">[in] The offset in the image.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="79b6d-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="79b6d-109">Return Value</span></span>  
 <span data-ttu-id="79b6d-110">S_OK se il metodo ha esito positivo. in caso contrario, E_FAIL o un altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="79b6d-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="79b6d-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="79b6d-111">Requirements</span></span>  
 <span data-ttu-id="79b6d-112">**Intestazione:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="79b6d-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="79b6d-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="79b6d-113">See Also</span></span>  
 [<span data-ttu-id="79b6d-114">Interfaccia ISymUnmanagedWriter3</span><span class="sxs-lookup"><span data-stu-id="79b6d-114">ISymUnmanagedWriter3 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter3-interface.md)  
 [<span data-ttu-id="79b6d-115">Metodo OpenMethod</span><span class="sxs-lookup"><span data-stu-id="79b6d-115">OpenMethod Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openmethod-method.md)
