---
title: Metodo FreeWin32ResBlob
ms.date: 03/30/2017
api_name:
- IALink.FreeWin32ResBlob
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- FreeWin32ResBlob
helpviewer_keywords:
- FreeWin32ResBlob method
ms.assetid: d941102b-2679-4c49-b15e-c0fc9c53e11f
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: e52984e12f22486212f0a2ec02d452a77242400e
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57491828"
---
# <a name="freewin32resblob-method"></a><span data-ttu-id="701f1-102">Metodo FreeWin32ResBlob</span><span class="sxs-lookup"><span data-stu-id="701f1-102">FreeWin32ResBlob Method</span></span>
<span data-ttu-id="701f1-103">Rilascia le risorse associate e il blob di risorse Win32.</span><span class="sxs-lookup"><span data-stu-id="701f1-103">Releases the Win32 resource blob and associated resources.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="701f1-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="701f1-104">Syntax</span></span>  
  
```  
HRESULT FreeWin32ResBlob(  
    const void** ppResBlob  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="701f1-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="701f1-105">Parameters</span></span>  
 `ppResBlob`  
 <span data-ttu-id="701f1-106">Il blob di risorse da rilasciare.</span><span class="sxs-lookup"><span data-stu-id="701f1-106">The resource blob to be released.</span></span> <span data-ttu-id="701f1-107">Questo metodo assegna il puntatore di blob su NULL.</span><span class="sxs-lookup"><span data-stu-id="701f1-107">This method assigns the blob pointer to NULL.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="701f1-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="701f1-108">Return Value</span></span>  
 <span data-ttu-id="701f1-109">Restituisce S_OK se il metodo ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="701f1-109">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="701f1-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="701f1-110">Requirements</span></span>  
 <span data-ttu-id="701f1-111">Richiede alink.h</span><span class="sxs-lookup"><span data-stu-id="701f1-111">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="701f1-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="701f1-112">See also</span></span>
- [<span data-ttu-id="701f1-113">Interfaccia IALink</span><span class="sxs-lookup"><span data-stu-id="701f1-113">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="701f1-114">Interfaccia IALink2</span><span class="sxs-lookup"><span data-stu-id="701f1-114">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="701f1-115">Alink (API)</span><span class="sxs-lookup"><span data-stu-id="701f1-115">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
