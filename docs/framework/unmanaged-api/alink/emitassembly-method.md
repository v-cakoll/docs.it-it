---
title: Metodo EmitAssembly
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- IALink2.EmitAssembly
- EmitAssembly
api_location: alink.dll
api_type: COM
f1_keywords: EmitAssembly
helpviewer_keywords: EmitAssembly method
ms.assetid: 605ff39e-e5cc-4bff-8196-e8d68a9715b9
topic_type: apiref
caps.latest.revision: "4"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 3471c4ad2d06443e0f05dc344be5f791817f2d2f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="emitassembly-method"></a><span data-ttu-id="d73ae-102">Metodo EmitAssembly</span><span class="sxs-lookup"><span data-stu-id="d73ae-102">EmitAssembly Method</span></span>
<span data-ttu-id="d73ae-103">Crea l'assembly.</span><span class="sxs-lookup"><span data-stu-id="d73ae-103">Creates the assembly.</span></span> <span data-ttu-id="d73ae-104">Chiamare questo metodo dopo la chiusura di tutti gli altri file ad eccezione del file di assembly.</span><span class="sxs-lookup"><span data-stu-id="d73ae-104">Call this method after all other files are closed except for the assembly file.</span></span> <span data-ttu-id="d73ae-105">Non chiamare questo metodo durante la creazione di moduli non associati.</span><span class="sxs-lookup"><span data-stu-id="d73ae-105">Do not call this method when producing unbound modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d73ae-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d73ae-106">Syntax</span></span>  
  
```  
HRESULT EmitAssembly(  
    mdAssembly AssemblyID  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d73ae-107">Parametri</span><span class="sxs-lookup"><span data-stu-id="d73ae-107">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="d73ae-108">ID dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="d73ae-108">ID of the assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d73ae-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="d73ae-109">Return Value</span></span>  
 <span data-ttu-id="d73ae-110">Se il metodo ha esito positivo, restituisce S_OK.</span><span class="sxs-lookup"><span data-stu-id="d73ae-110">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d73ae-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="d73ae-111">Requirements</span></span>  
 <span data-ttu-id="d73ae-112">Richiede alink.h</span><span class="sxs-lookup"><span data-stu-id="d73ae-112">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d73ae-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d73ae-113">See Also</span></span>  
 [<span data-ttu-id="d73ae-114">Interfaccia IALink</span><span class="sxs-lookup"><span data-stu-id="d73ae-114">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="d73ae-115">Interfaccia IALink2</span><span class="sxs-lookup"><span data-stu-id="d73ae-115">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="d73ae-116">ALink (API)</span><span class="sxs-lookup"><span data-stu-id="d73ae-116">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
