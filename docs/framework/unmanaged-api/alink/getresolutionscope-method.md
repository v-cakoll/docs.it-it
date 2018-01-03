---
title: Metodo GetResolutionScope
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IALink.GetResolutionScope
api_location: alink.dll
api_type: COM
f1_keywords: GetResolutionScope
helpviewer_keywords: GetResolutionScope method
ms.assetid: 5b48ca60-dacd-44b2-9979-4a5122f00812
topic_type: apiref
caps.latest.revision: "5"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f9dc63a7165ab472e973e0bc4f3e4cbb99e5d828
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="getresolutionscope-method"></a><span data-ttu-id="4d1d9-102">Metodo GetResolutionScope</span><span class="sxs-lookup"><span data-stu-id="4d1d9-102">GetResolutionScope Method</span></span>
<span data-ttu-id="4d1d9-103">Recupera l'ambito di un determinato tipo.</span><span class="sxs-lookup"><span data-stu-id="4d1d9-103">Retrieves the scope of a given type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4d1d9-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4d1d9-104">Syntax</span></span>  
  
```  
HRESULT GetResolutionScope(  
    mdAssembly  AssemblyID,  
    mdToken     FileToken,  
    mdToken     TargetFile,  
    mdToken*    pScope  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4d1d9-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="4d1d9-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="4d1d9-106">ID dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="4d1d9-106">ID of the assembly.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="4d1d9-107">File che richiede un riferimento.</span><span class="sxs-lookup"><span data-stu-id="4d1d9-107">File that is in need of a reference.</span></span>  
  
 `TargetFile`  
 <span data-ttu-id="4d1d9-108">Token del file di tale tipo è definito, in genere recuperato con [metodo ImportFile](../../../../docs/framework/unmanaged-api/alink/importfile-method.md).</span><span class="sxs-lookup"><span data-stu-id="4d1d9-108">Token of file that type is defined in, usually retrieved with [ImportFile Method](../../../../docs/framework/unmanaged-api/alink/importfile-method.md).</span></span>  
  
 `pScope`  
 <span data-ttu-id="4d1d9-109">Riceve il riferimento all'assembly o modulo.</span><span class="sxs-lookup"><span data-stu-id="4d1d9-109">Receives the assembly or module reference.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4d1d9-110">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="4d1d9-110">Return Value</span></span>  
 <span data-ttu-id="4d1d9-111">Se il metodo ha esito positivo, restituisce S_OK.</span><span class="sxs-lookup"><span data-stu-id="4d1d9-111">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4d1d9-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="4d1d9-112">Requirements</span></span>  
 <span data-ttu-id="4d1d9-113">Richiede alink.h.</span><span class="sxs-lookup"><span data-stu-id="4d1d9-113">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4d1d9-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4d1d9-114">See Also</span></span>  
 [<span data-ttu-id="4d1d9-115">Interfaccia IALink</span><span class="sxs-lookup"><span data-stu-id="4d1d9-115">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="4d1d9-116">Interfaccia IALink2</span><span class="sxs-lookup"><span data-stu-id="4d1d9-116">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="4d1d9-117">Alink (API)</span><span class="sxs-lookup"><span data-stu-id="4d1d9-117">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
