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
ms.openlocfilehash: 2e686e332cf1d35537e5d4306a3a9cbf9d46c47e
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67752374"
---
# <a name="isymunmanagedwriter3openmethod2-method"></a><span data-ttu-id="31a92-102">Metodo ISymUnmanagedWriter3::OpenMethod2</span><span class="sxs-lookup"><span data-stu-id="31a92-102">ISymUnmanagedWriter3::OpenMethod2 Method</span></span>
<span data-ttu-id="31a92-103">Apre un metodo e fornisce l'offset di sezione reali nell'immagine.</span><span class="sxs-lookup"><span data-stu-id="31a92-103">Opens a method and provides its real section offset in the image.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="31a92-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="31a92-104">Syntax</span></span>  
  
```cpp  
HRESULT OpenMethod2(   
    [in] mdMethodDef method,  
    [in] ULONG32 isect,  
    [in] ULONG32 offset);  
```  
  
## <a name="parameters"></a><span data-ttu-id="31a92-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="31a92-105">Parameters</span></span>  
 `method`  
 <span data-ttu-id="31a92-106">[in] Il token di metadati per il metodo da aprire.</span><span class="sxs-lookup"><span data-stu-id="31a92-106">[in] The metadata token for the method to be opened.</span></span>  
  
 `isect`  
 <span data-ttu-id="31a92-107">[in] L'offset della sezione nell'immagine.</span><span class="sxs-lookup"><span data-stu-id="31a92-107">[in] The section offset in the image.</span></span>  
  
 `offset`  
 <span data-ttu-id="31a92-108">[in] L'offset dell'immagine.</span><span class="sxs-lookup"><span data-stu-id="31a92-108">[in] The offset in the image.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="31a92-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="31a92-109">Return Value</span></span>  
 <span data-ttu-id="31a92-110">S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o qualche altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="31a92-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="31a92-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="31a92-111">Requirements</span></span>  
 <span data-ttu-id="31a92-112">**Intestazione:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="31a92-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="31a92-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="31a92-113">See also</span></span>

- [<span data-ttu-id="31a92-114">Interfaccia ISymUnmanagedWriter3</span><span class="sxs-lookup"><span data-stu-id="31a92-114">ISymUnmanagedWriter3 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter3-interface.md)
- [<span data-ttu-id="31a92-115">Metodo OpenMethod</span><span class="sxs-lookup"><span data-stu-id="31a92-115">OpenMethod Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openmethod-method.md)
