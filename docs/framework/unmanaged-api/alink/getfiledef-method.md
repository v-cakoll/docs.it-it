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
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59184496"
---
# <a name="getfiledef-method"></a><span data-ttu-id="460ee-102">Metodo GetFileDef</span><span class="sxs-lookup"><span data-stu-id="460ee-102">GetFileDef Method</span></span>
<span data-ttu-id="460ee-103">Recupera il token FileDef effettivo utilizzato nei metadati (anziché i token assegnati da ALink).</span><span class="sxs-lookup"><span data-stu-id="460ee-103">Retrieves the actual FileDef token used in metadata (as opposed to the token assigned by ALink).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="460ee-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="460ee-104">Syntax</span></span>  
  
```  
HRESULT GetFileDef(  
    mdAssembly AssemblyID,  
    mdFile TargetFile,  
    mdFile* pScope  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="460ee-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="460ee-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="460ee-106">ID dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="460ee-106">ID of the assembly.</span></span>  
  
 `TargetFile`  
 <span data-ttu-id="460ee-107">Token del file aggiunto come recuperati dal metodo AddFile o AddImport (metodo).</span><span class="sxs-lookup"><span data-stu-id="460ee-107">Token of the added file as retrieved from AddFile Method or AddImport Method.</span></span>  
  
 `pScope`  
 <span data-ttu-id="460ee-108">Riceve il token FileDef.</span><span class="sxs-lookup"><span data-stu-id="460ee-108">Receives the FileDef token.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="460ee-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="460ee-109">Return Value</span></span>  
 <span data-ttu-id="460ee-110">Restituisce S_OK se il metodo ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="460ee-110">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="460ee-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="460ee-111">Requirements</span></span>  
 <span data-ttu-id="460ee-112">Richiede alink.h</span><span class="sxs-lookup"><span data-stu-id="460ee-112">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="460ee-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="460ee-113">See also</span></span>

- [<span data-ttu-id="460ee-114">Interfaccia IALink2</span><span class="sxs-lookup"><span data-stu-id="460ee-114">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="460ee-115">Interfaccia IALink</span><span class="sxs-lookup"><span data-stu-id="460ee-115">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="460ee-116">Alink (API)</span><span class="sxs-lookup"><span data-stu-id="460ee-116">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
