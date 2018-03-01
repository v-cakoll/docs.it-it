---
title: Metodo EmitAssembly
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
- IALink2.EmitAssembly
- EmitAssembly
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- EmitAssembly
helpviewer_keywords:
- EmitAssembly method
ms.assetid: 605ff39e-e5cc-4bff-8196-e8d68a9715b9
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: f012ea89fec0e64bc1639e6c47fb79249c25411a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="emitassembly-method"></a><span data-ttu-id="61ccd-102">Metodo EmitAssembly</span><span class="sxs-lookup"><span data-stu-id="61ccd-102">EmitAssembly Method</span></span>
<span data-ttu-id="61ccd-103">Crea l'assembly.</span><span class="sxs-lookup"><span data-stu-id="61ccd-103">Creates the assembly.</span></span> <span data-ttu-id="61ccd-104">Chiamare questo metodo dopo la chiusura di tutti gli altri file ad eccezione del file di assembly.</span><span class="sxs-lookup"><span data-stu-id="61ccd-104">Call this method after all other files are closed except for the assembly file.</span></span> <span data-ttu-id="61ccd-105">Non chiamare questo metodo durante la creazione di moduli non associati.</span><span class="sxs-lookup"><span data-stu-id="61ccd-105">Do not call this method when producing unbound modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="61ccd-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="61ccd-106">Syntax</span></span>  
  
```  
HRESULT EmitAssembly(  
    mdAssembly AssemblyID  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="61ccd-107">Parametri</span><span class="sxs-lookup"><span data-stu-id="61ccd-107">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="61ccd-108">ID dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="61ccd-108">ID of the assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="61ccd-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="61ccd-109">Return Value</span></span>  
 <span data-ttu-id="61ccd-110">Se il metodo ha esito positivo, restituisce S_OK.</span><span class="sxs-lookup"><span data-stu-id="61ccd-110">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="61ccd-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="61ccd-111">Requirements</span></span>  
 <span data-ttu-id="61ccd-112">Richiede alink.h</span><span class="sxs-lookup"><span data-stu-id="61ccd-112">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="61ccd-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="61ccd-113">See Also</span></span>  
 [<span data-ttu-id="61ccd-114">Interfaccia IALink</span><span class="sxs-lookup"><span data-stu-id="61ccd-114">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="61ccd-115">Interfaccia IALink2</span><span class="sxs-lookup"><span data-stu-id="61ccd-115">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="61ccd-116">Alink (API)</span><span class="sxs-lookup"><span data-stu-id="61ccd-116">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
