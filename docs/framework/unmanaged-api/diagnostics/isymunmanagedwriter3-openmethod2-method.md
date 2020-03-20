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
ms.openlocfilehash: 0c112819ef3bc4f9a7146ee80f55202ff89d689a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178326"
---
# <a name="isymunmanagedwriter3openmethod2-method"></a><span data-ttu-id="08704-102">Metodo ISymUnmanagedWriter3::OpenMethod2</span><span class="sxs-lookup"><span data-stu-id="08704-102">ISymUnmanagedWriter3::OpenMethod2 Method</span></span>
<span data-ttu-id="08704-103">Apre un metodo e fornisce l'offset di sezione reale nell'immagine.</span><span class="sxs-lookup"><span data-stu-id="08704-103">Opens a method and provides its real section offset in the image.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="08704-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="08704-104">Syntax</span></span>  
  
```cpp  
HRESULT OpenMethod2(
    [in] mdMethodDef method,  
    [in] ULONG32 isect,  
    [in] ULONG32 offset);  
```  
  
## <a name="parameters"></a><span data-ttu-id="08704-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="08704-105">Parameters</span></span>  
 `method`  
 <span data-ttu-id="08704-106">[in] Token di metadati per il metodo da aprire.</span><span class="sxs-lookup"><span data-stu-id="08704-106">[in] The metadata token for the method to be opened.</span></span>  
  
 `isect`  
 <span data-ttu-id="08704-107">[in] Offset di sezione nell'immagine.</span><span class="sxs-lookup"><span data-stu-id="08704-107">[in] The section offset in the image.</span></span>  
  
 `offset`  
 <span data-ttu-id="08704-108">[in] Offset nell'immagine.</span><span class="sxs-lookup"><span data-stu-id="08704-108">[in] The offset in the image.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="08704-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="08704-109">Return Value</span></span>  
 <span data-ttu-id="08704-110">S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o qualche altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="08704-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="08704-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="08704-111">Requirements</span></span>  
 <span data-ttu-id="08704-112">**Intestazione:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="08704-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="08704-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="08704-113">See also</span></span>

- [<span data-ttu-id="08704-114">Interfaccia ISymUnmanagedWriter3</span><span class="sxs-lookup"><span data-stu-id="08704-114">ISymUnmanagedWriter3 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter3-interface.md)
- [<span data-ttu-id="08704-115">Metodo OpenMethod</span><span class="sxs-lookup"><span data-stu-id="08704-115">OpenMethod Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openmethod-method.md)
