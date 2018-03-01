---
title: Metodo SetNonAssemblyFlags
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
- IALink.SetNonAssemblyFlags
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- SetNonAssemblyFlags
helpviewer_keywords:
- SetNonAssemblyFlags method
ms.assetid: f8ba6fc8-f5aa-4066-ac96-56332758f5ec
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 7e944f285ee0925b76fdd9b95c824deee38cead2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="setnonassemblyflags-method"></a><span data-ttu-id="934f7-102">Metodo SetNonAssemblyFlags</span><span class="sxs-lookup"><span data-stu-id="934f7-102">SetNonAssemblyFlags Method</span></span>
<span data-ttu-id="934f7-103">Imposta i flag che non sono specifici dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="934f7-103">Sets flags that are not assembly-specific.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="934f7-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="934f7-104">Syntax</span></span>  
  
```  
HRESULT SetNonAssemblyFlags(  
    AssemblyFlags afFlags  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="934f7-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="934f7-105">Parameters</span></span>  
 `afFlags`  
 <span data-ttu-id="934f7-106">Flag ALink.</span><span class="sxs-lookup"><span data-stu-id="934f7-106">ALink flags.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="934f7-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="934f7-107">Return Value</span></span>  
 <span data-ttu-id="934f7-108">Se il metodo ha esito positivo, restituisce S_OK.</span><span class="sxs-lookup"><span data-stu-id="934f7-108">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="934f7-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="934f7-109">Requirements</span></span>  
 <span data-ttu-id="934f7-110">Richiede alink.h</span><span class="sxs-lookup"><span data-stu-id="934f7-110">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="934f7-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="934f7-111">See Also</span></span>  
 [<span data-ttu-id="934f7-112">Interfaccia IALink</span><span class="sxs-lookup"><span data-stu-id="934f7-112">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="934f7-113">Interfaccia IALink2</span><span class="sxs-lookup"><span data-stu-id="934f7-113">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="934f7-114">Alink (API)</span><span class="sxs-lookup"><span data-stu-id="934f7-114">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
