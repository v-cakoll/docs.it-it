---
title: Metodo GetAssemblyRefHash
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
- IALink.GetAssemblyRefHash
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- GetAssemblyRefHash
helpviewer_keywords:
- GetAssemblyRefHash method
ms.assetid: 091a18bd-e901-46f6-b999-74d71c8a7c41
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 99ae38025f223d669a428738783676ebc0687554
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="getassemblyrefhash-method"></a><span data-ttu-id="75238-102">Metodo GetAssemblyRefHash</span><span class="sxs-lookup"><span data-stu-id="75238-102">GetAssemblyRefHash Method</span></span>
<span data-ttu-id="75238-103">Recupera un blob hash per un determinato assembly.</span><span class="sxs-lookup"><span data-stu-id="75238-103">Retrieves a hash blob for a given assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="75238-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="75238-104">Syntax</span></span>  
  
```  
HRESULT GetAssemblyRefHash(  
    mdToken FileToken,  
    const void** ppvHash,  
    DWORD* pcbHash  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="75238-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="75238-105">Parameters</span></span>  
 `FileToken`  
 <span data-ttu-id="75238-106">ID dell'assembly a cui farà riferimento all'hash.</span><span class="sxs-lookup"><span data-stu-id="75238-106">ID of assembly to which the hash will refer.</span></span>  
  
 `ppvHash`  
 <span data-ttu-id="75238-107">Riceve il blob hash risultante.</span><span class="sxs-lookup"><span data-stu-id="75238-107">Receives the resulting hash blob.</span></span>  
  
 `pcbHash`  
 <span data-ttu-id="75238-108">Riceve le dimensioni, in byte del blob hash.</span><span class="sxs-lookup"><span data-stu-id="75238-108">Receives size, in bytes, of hash blob.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="75238-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="75238-109">Return Value</span></span>  
 <span data-ttu-id="75238-110">Se il metodo ha esito positivo, restituisce S_OK.</span><span class="sxs-lookup"><span data-stu-id="75238-110">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="75238-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="75238-111">Requirements</span></span>  
 <span data-ttu-id="75238-112">Richiede alink.h</span><span class="sxs-lookup"><span data-stu-id="75238-112">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="75238-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="75238-113">See Also</span></span>  
 [<span data-ttu-id="75238-114">Interfaccia IALink</span><span class="sxs-lookup"><span data-stu-id="75238-114">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="75238-115">Interfaccia IALink2</span><span class="sxs-lookup"><span data-stu-id="75238-115">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="75238-116">Alink (API)</span><span class="sxs-lookup"><span data-stu-id="75238-116">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
