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
ms.openlocfilehash: d124ce5dd38bed7eb439a055ff9e30a75efe5891
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33400744"
---
# <a name="freewin32resblob-method"></a><span data-ttu-id="08148-102">Metodo FreeWin32ResBlob</span><span class="sxs-lookup"><span data-stu-id="08148-102">FreeWin32ResBlob Method</span></span>
<span data-ttu-id="08148-103">Rilascia le risorse associate e il blob di risorse Win32.</span><span class="sxs-lookup"><span data-stu-id="08148-103">Releases the Win32 resource blob and associated resources.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="08148-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="08148-104">Syntax</span></span>  
  
```  
HRESULT FreeWin32ResBlob(  
    const void** ppResBlob  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="08148-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="08148-105">Parameters</span></span>  
 `ppResBlob`  
 <span data-ttu-id="08148-106">Il blob di risorse da rilasciare.</span><span class="sxs-lookup"><span data-stu-id="08148-106">The resource blob to be released.</span></span> <span data-ttu-id="08148-107">Questo metodo assegna il puntatore del blob a NULL.</span><span class="sxs-lookup"><span data-stu-id="08148-107">This method assigns the blob pointer to NULL.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="08148-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="08148-108">Return Value</span></span>  
 <span data-ttu-id="08148-109">Se il metodo ha esito positivo, restituisce S_OK.</span><span class="sxs-lookup"><span data-stu-id="08148-109">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="08148-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="08148-110">Requirements</span></span>  
 <span data-ttu-id="08148-111">Richiede alink.h</span><span class="sxs-lookup"><span data-stu-id="08148-111">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="08148-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="08148-112">See Also</span></span>  
 [<span data-ttu-id="08148-113">Interfaccia IALink</span><span class="sxs-lookup"><span data-stu-id="08148-113">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="08148-114">Interfaccia IALink2</span><span class="sxs-lookup"><span data-stu-id="08148-114">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="08148-115">Alink (API)</span><span class="sxs-lookup"><span data-stu-id="08148-115">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
