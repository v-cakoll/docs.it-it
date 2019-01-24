---
title: Metodo ISymUnmanagedWriter3::OpenMethod2
ms.date: 03/30/2017
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b641f463eb9b664597b4806a6353278e8027d5b8
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54709104"
---
# <a name="isymunmanagedwriter3openmethod2-method"></a><span data-ttu-id="d8b4c-102">Metodo ISymUnmanagedWriter3::OpenMethod2</span><span class="sxs-lookup"><span data-stu-id="d8b4c-102">ISymUnmanagedWriter3::OpenMethod2 Method</span></span>
<span data-ttu-id="d8b4c-103">Apre un metodo e fornisce l'offset di sezione reali nell'immagine.</span><span class="sxs-lookup"><span data-stu-id="d8b4c-103">Opens a method and provides its real section offset in the image.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d8b4c-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d8b4c-104">Syntax</span></span>  
  
```  
HRESULT OpenMethod2(   
    [in] mdMethodDef method,  
    [in] ULONG32 isect,  
    [in] ULONG32 offset);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d8b4c-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="d8b4c-105">Parameters</span></span>  
 `method`  
 <span data-ttu-id="d8b4c-106">[in] Il token di metadati per il metodo da aprire.</span><span class="sxs-lookup"><span data-stu-id="d8b4c-106">[in] The metadata token for the method to be opened.</span></span>  
  
 `isect`  
 <span data-ttu-id="d8b4c-107">[in] L'offset della sezione nell'immagine.</span><span class="sxs-lookup"><span data-stu-id="d8b4c-107">[in] The section offset in the image.</span></span>  
  
 `offset`  
 <span data-ttu-id="d8b4c-108">[in] L'offset dell'immagine.</span><span class="sxs-lookup"><span data-stu-id="d8b4c-108">[in] The offset in the image.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d8b4c-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="d8b4c-109">Return Value</span></span>  
 <span data-ttu-id="d8b4c-110">S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o qualche altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="d8b4c-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d8b4c-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="d8b4c-111">Requirements</span></span>  
 <span data-ttu-id="d8b4c-112">**Intestazione:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="d8b4c-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d8b4c-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d8b4c-113">See also</span></span>
- [<span data-ttu-id="d8b4c-114">Interfaccia ISymUnmanagedWriter3</span><span class="sxs-lookup"><span data-stu-id="d8b4c-114">ISymUnmanagedWriter3 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter3-interface.md)
- [<span data-ttu-id="d8b4c-115">Metodo OpenMethod</span><span class="sxs-lookup"><span data-stu-id="d8b4c-115">OpenMethod Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openmethod-method.md)
