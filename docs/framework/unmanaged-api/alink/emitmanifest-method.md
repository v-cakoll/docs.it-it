---
title: Metodo EmitManifest
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- EmitManifest
- IALink.EmitManifest
api_location: alink.dll
api_type: COM
f1_keywords: EmitManifest
helpviewer_keywords: EmitManifest method
ms.assetid: fdebc1f3-b62e-4d9e-b775-8ccaa8ecb250
topic_type: apiref
caps.latest.revision: "6"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 03ef815f03a65cbf7e2dc936b21848e206132add
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="emitmanifest-method"></a><span data-ttu-id="8a056-102">Metodo EmitManifest</span><span class="sxs-lookup"><span data-stu-id="8a056-102">EmitManifest Method</span></span>
<span data-ttu-id="8a056-103">Genera manifesto finale.</span><span class="sxs-lookup"><span data-stu-id="8a056-103">Emits the final manifest.</span></span> <span data-ttu-id="8a056-104">Chiamare questo metodo dopo l'importazione di tutti gli altri file e tutte le opzioni di impostazione.</span><span class="sxs-lookup"><span data-stu-id="8a056-104">Call this method after importing all other files and setting all options.</span></span> <span data-ttu-id="8a056-105">Non chiamare questo metodo per i moduli non associati.</span><span class="sxs-lookup"><span data-stu-id="8a056-105">Do not call this method for unbound modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8a056-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8a056-106">Syntax</span></span>  
  
```  
HRESULT EmitManifest(  
    mdAssembly   AssemblyID,  
    DWORD*       pdwReserveSize,  
    mdAssembly*  ptkManifest  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8a056-107">Parametri</span><span class="sxs-lookup"><span data-stu-id="8a056-107">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="8a056-108">ID dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="8a056-108">ID of the assembly.</span></span>  
  
 `pdwReserveSize`  
 <span data-ttu-id="8a056-109">Riceve le dimensioni di riservare nel file di assembly, recuperati da [funzione StrongNameSignatureSize](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignaturesize-function.md).</span><span class="sxs-lookup"><span data-stu-id="8a056-109">Receives the size to reserve in the assembly file, retrieved from [StrongNameSignatureSize Function](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignaturesize-function.md).</span></span>  
  
 `ptkManifest`  
 <span data-ttu-id="8a056-110">Facoltativamente, riceve il token del manifesto assembly.</span><span class="sxs-lookup"><span data-stu-id="8a056-110">Optionally receives the assembly manifest token.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8a056-111">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="8a056-111">Return Value</span></span>  
 <span data-ttu-id="8a056-112">Se il metodo ha esito positivo, restituisce S_OK.</span><span class="sxs-lookup"><span data-stu-id="8a056-112">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8a056-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="8a056-113">Requirements</span></span>  
 <span data-ttu-id="8a056-114">Richiede alink.h.</span><span class="sxs-lookup"><span data-stu-id="8a056-114">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8a056-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8a056-115">See Also</span></span>  
 [<span data-ttu-id="8a056-116">Interfaccia IALink</span><span class="sxs-lookup"><span data-stu-id="8a056-116">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="8a056-117">Interfaccia IALink2</span><span class="sxs-lookup"><span data-stu-id="8a056-117">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="8a056-118">ALink (API)</span><span class="sxs-lookup"><span data-stu-id="8a056-118">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
