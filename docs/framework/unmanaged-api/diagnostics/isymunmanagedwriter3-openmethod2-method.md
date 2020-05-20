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
ms.openlocfilehash: e88a844a7f79f14c717a5966b345588b3b3b9f81
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83609417"
---
# <a name="isymunmanagedwriter3openmethod2-method"></a><span data-ttu-id="165fd-102">Metodo ISymUnmanagedWriter3::OpenMethod2</span><span class="sxs-lookup"><span data-stu-id="165fd-102">ISymUnmanagedWriter3::OpenMethod2 Method</span></span>
<span data-ttu-id="165fd-103">Apre un metodo e fornisce la relativa offset della sezione reale nell'immagine.</span><span class="sxs-lookup"><span data-stu-id="165fd-103">Opens a method and provides its real section offset in the image.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="165fd-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="165fd-104">Syntax</span></span>  
  
```cpp  
HRESULT OpenMethod2(
    [in] mdMethodDef method,  
    [in] ULONG32 isect,  
    [in] ULONG32 offset);  
```  
  
## <a name="parameters"></a><span data-ttu-id="165fd-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="165fd-105">Parameters</span></span>  
 `method`  
 <span data-ttu-id="165fd-106">in Token di metadati per il metodo da aprire.</span><span class="sxs-lookup"><span data-stu-id="165fd-106">[in] The metadata token for the method to be opened.</span></span>  
  
 `isect`  
 <span data-ttu-id="165fd-107">in Offset della sezione nell'immagine.</span><span class="sxs-lookup"><span data-stu-id="165fd-107">[in] The section offset in the image.</span></span>  
  
 `offset`  
 <span data-ttu-id="165fd-108">in Offset nell'immagine.</span><span class="sxs-lookup"><span data-stu-id="165fd-108">[in] The offset in the image.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="165fd-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="165fd-109">Return Value</span></span>  
 <span data-ttu-id="165fd-110">S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o un altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="165fd-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="165fd-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="165fd-111">Requirements</span></span>  
 <span data-ttu-id="165fd-112">**Intestazione:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="165fd-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="165fd-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="165fd-113">See also</span></span>

- [<span data-ttu-id="165fd-114">Interfaccia ISymUnmanagedWriter3</span><span class="sxs-lookup"><span data-stu-id="165fd-114">ISymUnmanagedWriter3 Interface</span></span>](isymunmanagedwriter3-interface.md)
- [<span data-ttu-id="165fd-115">Metodo OpenMethod</span><span class="sxs-lookup"><span data-stu-id="165fd-115">OpenMethod Method</span></span>](isymunmanagedwriter-openmethod-method.md)
