---
title: Metodo EndMerge
ms.date: 03/30/2017
api_name:
- IALink.EndMerge
- EndMerge
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- EndMerge
helpviewer_keywords:
- EndMerge method
ms.assetid: 1d03bb15-a2c8-4a04-8fc6-b126c89c3778
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 7d4b102485db0199f748f6c5b6c4ab40d21429e9
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57494411"
---
# <a name="endmerge-method"></a><span data-ttu-id="fb57b-102">Metodo EndMerge</span><span class="sxs-lookup"><span data-stu-id="fb57b-102">EndMerge Method</span></span>
<span data-ttu-id="fb57b-103">Indica che tutti gli attributi personalizzati sono stati uniti nell'ambito di emissione.</span><span class="sxs-lookup"><span data-stu-id="fb57b-103">Indicates that all custom attributes have been merged into the emit scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fb57b-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="fb57b-104">Syntax</span></span>  
  
```  
HRESULT EndMerge(  
    mdAssembly AssemblyID  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="fb57b-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="fb57b-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="fb57b-106">ID dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="fb57b-106">ID of the assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="fb57b-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="fb57b-107">Return Value</span></span>  
 <span data-ttu-id="fb57b-108">Restituisce S_OK se il metodo ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="fb57b-108">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fb57b-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="fb57b-109">Requirements</span></span>  
 <span data-ttu-id="fb57b-110">Richiede alink.h</span><span class="sxs-lookup"><span data-stu-id="fb57b-110">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fb57b-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fb57b-111">See also</span></span>
- [<span data-ttu-id="fb57b-112">Interfaccia IALink</span><span class="sxs-lookup"><span data-stu-id="fb57b-112">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="fb57b-113">Interfaccia IALink2</span><span class="sxs-lookup"><span data-stu-id="fb57b-113">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="fb57b-114">Alink (API)</span><span class="sxs-lookup"><span data-stu-id="fb57b-114">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
