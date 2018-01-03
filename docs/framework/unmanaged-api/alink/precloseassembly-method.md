---
title: Metodo PreCloseAssembly
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IALink.PreCloseAssembly
api_location: alink.dll
api_type: COM
f1_keywords: PreCloseAssembly
helpviewer_keywords: PreCloseAssembly method
ms.assetid: 6d23ac54-15ea-4027-a172-9ebef43e8f56
topic_type: apiref
caps.latest.revision: "6"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 5a4d1f2eed036552ab17b6768b7b2d84f4a52c9c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="precloseassembly-method"></a><span data-ttu-id="53d90-102">Metodo PreCloseAssembly</span><span class="sxs-lookup"><span data-stu-id="53d90-102">PreCloseAssembly Method</span></span>
<span data-ttu-id="53d90-103">Chiude il file di assembly.</span><span class="sxs-lookup"><span data-stu-id="53d90-103">Closes the assembly file.</span></span> <span data-ttu-id="53d90-104">Chiamare questo metodo dopo la chiusura di tutti gli altri file, ma prima di chiudere il file di assembly.</span><span class="sxs-lookup"><span data-stu-id="53d90-104">Call this method after closing all other files, but before closing the assembly file.</span></span> <span data-ttu-id="53d90-105">Non chiamare questo metodo per i moduli non associati.</span><span class="sxs-lookup"><span data-stu-id="53d90-105">Do not call this method for unbound modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="53d90-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="53d90-106">Syntax</span></span>  
  
```  
HRESULT PreCloseAssembly(  
    mdAssembly AssemblyID  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="53d90-107">Parametri</span><span class="sxs-lookup"><span data-stu-id="53d90-107">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="53d90-108">ID dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="53d90-108">ID of the assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="53d90-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="53d90-109">Return Value</span></span>  
 <span data-ttu-id="53d90-110">Se il metodo ha esito positivo, restituisce S_OK.</span><span class="sxs-lookup"><span data-stu-id="53d90-110">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="53d90-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="53d90-111">Requirements</span></span>  
 <span data-ttu-id="53d90-112">Richiede alink.h.</span><span class="sxs-lookup"><span data-stu-id="53d90-112">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="53d90-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="53d90-113">See Also</span></span>  
 [<span data-ttu-id="53d90-114">Interfaccia IALink</span><span class="sxs-lookup"><span data-stu-id="53d90-114">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="53d90-115">Interfaccia IALink2</span><span class="sxs-lookup"><span data-stu-id="53d90-115">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="53d90-116">Alink (API)</span><span class="sxs-lookup"><span data-stu-id="53d90-116">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
