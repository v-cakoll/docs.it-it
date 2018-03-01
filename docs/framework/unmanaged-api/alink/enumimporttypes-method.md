---
title: Metodo EnumImportTypes
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
- EnumImportTypes
- IALink.EnumImportTypes
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- EnumImportTypes
helpviewer_keywords:
- EnumImportTypes method
ms.assetid: 83a0e4e7-ec06-40cb-9b63-700b9695bb04
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 08644816d3fa11ade5a8ebee1573e8f66d526101
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="enumimporttypes-method"></a><span data-ttu-id="d48af-102">Metodo EnumImportTypes</span><span class="sxs-lookup"><span data-stu-id="d48af-102">EnumImportTypes Method</span></span>
<span data-ttu-id="d48af-103">Enumera ogni tipo di ogni ambito.</span><span class="sxs-lookup"><span data-stu-id="d48af-103">Enumerates each type in each scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d48af-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d48af-104">Syntax</span></span>  
  
```  
HRESULT EnumImportTypes(  
    HALINKENUM   hEnum,  
    DWORD        dwMax,  
    mdTypeDef    aTypeDefs[],  
    DWORD*       pdwCount  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d48af-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="d48af-105">Parameters</span></span>  
 `hEnum`  
 <span data-ttu-id="d48af-106">Handle per l'enumeratore.</span><span class="sxs-lookup"><span data-stu-id="d48af-106">Handle for enumerator.</span></span>  
  
 `dwMax`  
 <span data-ttu-id="d48af-107">Numero massimo di tipi da recuperare.</span><span class="sxs-lookup"><span data-stu-id="d48af-107">Maximum number of types to retrieve.</span></span>  
  
 `aTypeDefs`  
 <span data-ttu-id="d48af-108">Riceve token di tipo, non deve superare `dwMax`.</span><span class="sxs-lookup"><span data-stu-id="d48af-108">Recieves type tokens, not to exceed `dwMax`.</span></span>  
  
 `pdwCount`  
 <span data-ttu-id="d48af-109">Riceve il numero effettivo di tipo in `aTypeDefs`.</span><span class="sxs-lookup"><span data-stu-id="d48af-109">Receives actual number of type in `aTypeDefs`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d48af-110">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="d48af-110">Return Value</span></span>  
 <span data-ttu-id="d48af-111">Se il metodo ha esito positivo, restituisce S_OK.</span><span class="sxs-lookup"><span data-stu-id="d48af-111">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d48af-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="d48af-112">Requirements</span></span>  
 <span data-ttu-id="d48af-113">Richiede alink.h</span><span class="sxs-lookup"><span data-stu-id="d48af-113">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d48af-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d48af-114">See Also</span></span>  
 [<span data-ttu-id="d48af-115">Interfaccia IALink</span><span class="sxs-lookup"><span data-stu-id="d48af-115">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="d48af-116">Interfaccia IALink2</span><span class="sxs-lookup"><span data-stu-id="d48af-116">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="d48af-117">Alink (API)</span><span class="sxs-lookup"><span data-stu-id="d48af-117">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
