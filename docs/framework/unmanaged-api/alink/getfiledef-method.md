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
ms.openlocfilehash: b772ae37baed44b90e4f5420e0f7724201a56abe
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33401811"
---
# <a name="getfiledef-method"></a><span data-ttu-id="e56cb-102">Metodo GetFileDef</span><span class="sxs-lookup"><span data-stu-id="e56cb-102">GetFileDef Method</span></span>
<span data-ttu-id="e56cb-103">Recupera il token FileDef effettivamente utilizzato nei metadati (a differenza dei token assegnato da ALink).</span><span class="sxs-lookup"><span data-stu-id="e56cb-103">Retrieves the actual FileDef token used in metadata (as opposed to the token assigned by ALink).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e56cb-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e56cb-104">Syntax</span></span>  
  
```  
HRESULT GetFileDef(  
    mdAssembly AssemblyID,  
    mdFile TargetFile,  
    mdFile* pScope  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e56cb-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="e56cb-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="e56cb-106">ID dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="e56cb-106">ID of the assembly.</span></span>  
  
 `TargetFile`  
 <span data-ttu-id="e56cb-107">Token del file aggiunto così come viene recuperato dal metodo AddFile o dal metodo AddImport.</span><span class="sxs-lookup"><span data-stu-id="e56cb-107">Token of the added file as retrieved from AddFile Method or AddImport Method.</span></span>  
  
 `pScope`  
 <span data-ttu-id="e56cb-108">Riceve il token FileDef.</span><span class="sxs-lookup"><span data-stu-id="e56cb-108">Receives the FileDef token.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e56cb-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="e56cb-109">Return Value</span></span>  
 <span data-ttu-id="e56cb-110">Se il metodo ha esito positivo, restituisce S_OK.</span><span class="sxs-lookup"><span data-stu-id="e56cb-110">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e56cb-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="e56cb-111">Requirements</span></span>  
 <span data-ttu-id="e56cb-112">Richiede alink.h</span><span class="sxs-lookup"><span data-stu-id="e56cb-112">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e56cb-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e56cb-113">See Also</span></span>  
 [<span data-ttu-id="e56cb-114">Interfaccia IALink2</span><span class="sxs-lookup"><span data-stu-id="e56cb-114">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="e56cb-115">Interfaccia IALink</span><span class="sxs-lookup"><span data-stu-id="e56cb-115">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="e56cb-116">Alink (API)</span><span class="sxs-lookup"><span data-stu-id="e56cb-116">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
