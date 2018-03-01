---
title: Metodo CloseAssembly
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
- IALink.CloseAssembly
- CloseAssembly
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- CloseAssembly
helpviewer_keywords:
- CloseAssembly method
ms.assetid: f66a43bc-a5c5-4190-acbe-63fd27640634
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 160ec53440f4ecdb924537c732a367881e75acf9
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="closeassembly-method"></a><span data-ttu-id="6ce00-102">Metodo CloseAssembly</span><span class="sxs-lookup"><span data-stu-id="6ce00-102">CloseAssembly Method</span></span>
<span data-ttu-id="6ce00-103">Consente di finalizzare le operazioni di assembly.</span><span class="sxs-lookup"><span data-stu-id="6ce00-103">Finalizes assembly operations.</span></span> <span data-ttu-id="6ce00-104">Chiamare questo metodo prima di iniziare un nuovo assembly o il modulo non associato.</span><span class="sxs-lookup"><span data-stu-id="6ce00-104">Call this method before beginning a new assembly or unbound module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6ce00-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6ce00-105">Syntax</span></span>  
  
```  
HRESULT CloseAssembly(  
    mdAssembly AssemblyID  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="6ce00-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="6ce00-106">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="6ce00-107">ID dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="6ce00-107">ID of the assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6ce00-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="6ce00-108">Return Value</span></span>  
 <span data-ttu-id="6ce00-109">Se il metodo ha esito positivo, restituisce S_OK.</span><span class="sxs-lookup"><span data-stu-id="6ce00-109">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6ce00-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="6ce00-110">Requirements</span></span>  
 <span data-ttu-id="6ce00-111">Richiede alink.h.</span><span class="sxs-lookup"><span data-stu-id="6ce00-111">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6ce00-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6ce00-112">See Also</span></span>  
 [<span data-ttu-id="6ce00-113">Interfaccia IALink</span><span class="sxs-lookup"><span data-stu-id="6ce00-113">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="6ce00-114">Interfaccia IALink2</span><span class="sxs-lookup"><span data-stu-id="6ce00-114">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="6ce00-115">Alink (API)</span><span class="sxs-lookup"><span data-stu-id="6ce00-115">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
