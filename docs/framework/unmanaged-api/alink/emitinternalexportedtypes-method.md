---
title: Metodo EmitInternalExportedTypes
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
- EmitInternalExportedTypes
- IALink2.EmitInternalExportedTypes
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- EmitInternalExportedTypes
helpviewer_keywords:
- EmitInternalExportedTypes method
ms.assetid: 28c8b00d-2c14-40b4-aed5-a1db0e2428eb
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 48ad5e34b926cf3dab562f57bb9206fa0ba70e6b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="emitinternalexportedtypes-method"></a><span data-ttu-id="2a436-102">Metodo EmitInternalExportedTypes</span><span class="sxs-lookup"><span data-stu-id="2a436-102">EmitInternalExportedTypes Method</span></span>
<span data-ttu-id="2a436-103">Genera tipi aggiunti all'assembly.</span><span class="sxs-lookup"><span data-stu-id="2a436-103">Emits types added to the assembly.</span></span> <span data-ttu-id="2a436-104">Chiamare questo metodo una volta noto tipi interni sono stati aggiunti.</span><span class="sxs-lookup"><span data-stu-id="2a436-104">Call this method after known internal types have been added.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2a436-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2a436-105">Syntax</span></span>  
  
```  
HRESULT EmitInternalExportedTypes(  
    mdAssembly AssemblyID  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="2a436-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="2a436-106">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="2a436-107">ID dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="2a436-107">ID of assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2a436-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="2a436-108">Return Value</span></span>  
 <span data-ttu-id="2a436-109">Se il metodo ha esito positivo, restituisce S_OK.</span><span class="sxs-lookup"><span data-stu-id="2a436-109">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2a436-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="2a436-110">Requirements</span></span>  
 <span data-ttu-id="2a436-111">Richiede alink.h</span><span class="sxs-lookup"><span data-stu-id="2a436-111">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2a436-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2a436-112">See Also</span></span>  
 [<span data-ttu-id="2a436-113">Interfaccia IALink2</span><span class="sxs-lookup"><span data-stu-id="2a436-113">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="2a436-114">Interfaccia IALink</span><span class="sxs-lookup"><span data-stu-id="2a436-114">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="2a436-115">Alink (API)</span><span class="sxs-lookup"><span data-stu-id="2a436-115">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
