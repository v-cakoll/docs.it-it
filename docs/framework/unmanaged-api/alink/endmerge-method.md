---
title: Metodo EndMerge
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
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 58e9cecae43fb69f1ce2e90eb9d6551d287ca7b3
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="endmerge-method"></a><span data-ttu-id="3ae72-102">Metodo EndMerge</span><span class="sxs-lookup"><span data-stu-id="3ae72-102">EndMerge Method</span></span>
<span data-ttu-id="3ae72-103">Indica che tutti gli attributi personalizzati sono stati uniti nell'ambito di emissione.</span><span class="sxs-lookup"><span data-stu-id="3ae72-103">Indicates that all custom attributes have been merged into the emit scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3ae72-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3ae72-104">Syntax</span></span>  
  
```  
HRESULT EndMerge(  
    mdAssembly AssemblyID  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="3ae72-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="3ae72-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="3ae72-106">ID dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="3ae72-106">ID of the assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3ae72-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="3ae72-107">Return Value</span></span>  
 <span data-ttu-id="3ae72-108">Se il metodo ha esito positivo, restituisce S_OK.</span><span class="sxs-lookup"><span data-stu-id="3ae72-108">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3ae72-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="3ae72-109">Requirements</span></span>  
 <span data-ttu-id="3ae72-110">Richiede alink.h</span><span class="sxs-lookup"><span data-stu-id="3ae72-110">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3ae72-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3ae72-111">See Also</span></span>  
 [<span data-ttu-id="3ae72-112">Interfaccia IALink</span><span class="sxs-lookup"><span data-stu-id="3ae72-112">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="3ae72-113">Interfaccia IALink2</span><span class="sxs-lookup"><span data-stu-id="3ae72-113">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="3ae72-114">Alink (API)</span><span class="sxs-lookup"><span data-stu-id="3ae72-114">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
