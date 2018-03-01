---
title: Metodo GetFileDef
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
- IALink2.GetFileDef
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- GetFileDef
helpviewer_keywords:
- GetFileDef method
ms.assetid: 4e3fbe6c-b82a-4181-ab17-7faa1263f5b3
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 473cbaba8712ee247733ba3075c0163e259cf4dc
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="getfiledef-method"></a><span data-ttu-id="4fa7b-102">Metodo GetFileDef</span><span class="sxs-lookup"><span data-stu-id="4fa7b-102">GetFileDef Method</span></span>
<span data-ttu-id="4fa7b-103">Recupera il token FileDef effettivamente utilizzato nei metadati (a differenza dei token assegnato da ALink).</span><span class="sxs-lookup"><span data-stu-id="4fa7b-103">Retrieves the actual FileDef token used in metadata (as opposed to the token assigned by ALink).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4fa7b-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4fa7b-104">Syntax</span></span>  
  
```  
HRESULT GetFileDef(  
    mdAssembly AssemblyID,  
    mdFile TargetFile,  
    mdFile* pScope  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4fa7b-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="4fa7b-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="4fa7b-106">ID dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="4fa7b-106">ID of the assembly.</span></span>  
  
 `TargetFile`  
 <span data-ttu-id="4fa7b-107">Token del file aggiunto così come viene recuperato dal metodo AddFile o dal metodo AddImport.</span><span class="sxs-lookup"><span data-stu-id="4fa7b-107">Token of the added file as retrieved from AddFile Method or AddImport Method.</span></span>  
  
 `pScope`  
 <span data-ttu-id="4fa7b-108">Riceve il token FileDef.</span><span class="sxs-lookup"><span data-stu-id="4fa7b-108">Receives the FileDef token.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4fa7b-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="4fa7b-109">Return Value</span></span>  
 <span data-ttu-id="4fa7b-110">Se il metodo ha esito positivo, restituisce S_OK.</span><span class="sxs-lookup"><span data-stu-id="4fa7b-110">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4fa7b-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="4fa7b-111">Requirements</span></span>  
 <span data-ttu-id="4fa7b-112">Richiede alink.h</span><span class="sxs-lookup"><span data-stu-id="4fa7b-112">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4fa7b-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4fa7b-113">See Also</span></span>  
 [<span data-ttu-id="4fa7b-114">Interfaccia IALink2</span><span class="sxs-lookup"><span data-stu-id="4fa7b-114">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="4fa7b-115">Interfaccia IALink</span><span class="sxs-lookup"><span data-stu-id="4fa7b-115">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="4fa7b-116">Alink (API)</span><span class="sxs-lookup"><span data-stu-id="4fa7b-116">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
