---
title: Metodo GetFileDef
ms.date: 03/30/2017
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 9153c9b3735e265d59ba072f747c92434c95d9ed
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59184496"
---
# <a name="getfiledef-method"></a><span data-ttu-id="780bc-102">Metodo GetFileDef</span><span class="sxs-lookup"><span data-stu-id="780bc-102">GetFileDef Method</span></span>
<span data-ttu-id="780bc-103">Recupera il token FileDef effettivo utilizzato nei metadati (anziché i token assegnati da ALink).</span><span class="sxs-lookup"><span data-stu-id="780bc-103">Retrieves the actual FileDef token used in metadata (as opposed to the token assigned by ALink).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="780bc-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="780bc-104">Syntax</span></span>  
  
```  
HRESULT GetFileDef(  
    mdAssembly AssemblyID,  
    mdFile TargetFile,  
    mdFile* pScope  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="780bc-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="780bc-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="780bc-106">ID dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="780bc-106">ID of the assembly.</span></span>  
  
 `TargetFile`  
 <span data-ttu-id="780bc-107">Token del file aggiunto come recuperati dal metodo AddFile o AddImport (metodo).</span><span class="sxs-lookup"><span data-stu-id="780bc-107">Token of the added file as retrieved from AddFile Method or AddImport Method.</span></span>  
  
 `pScope`  
 <span data-ttu-id="780bc-108">Riceve il token FileDef.</span><span class="sxs-lookup"><span data-stu-id="780bc-108">Receives the FileDef token.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="780bc-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="780bc-109">Return Value</span></span>  
 <span data-ttu-id="780bc-110">Restituisce S_OK se il metodo ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="780bc-110">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="780bc-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="780bc-111">Requirements</span></span>  
 <span data-ttu-id="780bc-112">Richiede alink.h</span><span class="sxs-lookup"><span data-stu-id="780bc-112">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="780bc-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="780bc-113">See also</span></span>

- [<span data-ttu-id="780bc-114">Interfaccia IALink2</span><span class="sxs-lookup"><span data-stu-id="780bc-114">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="780bc-115">Interfaccia IALink</span><span class="sxs-lookup"><span data-stu-id="780bc-115">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="780bc-116">API Alink</span><span class="sxs-lookup"><span data-stu-id="780bc-116">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
