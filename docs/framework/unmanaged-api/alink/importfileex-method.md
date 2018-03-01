---
title: Metodo ImportFileEx
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
- IALink2.ImportFileEx
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- ImportFileEx
helpviewer_keywords:
- ImportFileEx method
ms.assetid: ad276f3f-b303-46ac-97e0-66a377adaa4f
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: dc2af9db27c5194a1bdcef875b8db8d458d0edfe
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="importfileex-method"></a><span data-ttu-id="61c3e-102">Metodo ImportFileEx</span><span class="sxs-lookup"><span data-stu-id="61c3e-102">ImportFileEx Method</span></span>
<span data-ttu-id="61c3e-103">Importazioni indicato assembly o un modulo non associato.</span><span class="sxs-lookup"><span data-stu-id="61c3e-103">Imports indicated assembly or unbound module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="61c3e-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="61c3e-104">Syntax</span></span>  
  
```  
HRESULT ImportFileEx(  
    LPCWSTR pszFilename,  
    LPCWSTR pszTargetName,  
    BOOL fSmartImport,  
    DWORD dwOpenFlags,  
    mdToken* pImportToken,  
    IMetaDataAssemblyImport** ppAssemblyScope,  
    DWORD* pdwCountOfScopes  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="61c3e-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="61c3e-105">Parameters</span></span>  
 `pszFilename`  
 <span data-ttu-id="61c3e-106">Nome completo del file da cui importare.</span><span class="sxs-lookup"><span data-stu-id="61c3e-106">Fully qualified name of file from which to import.</span></span>  
  
 `pszTargetName`  
 <span data-ttu-id="61c3e-107">Nome facoltativo di file di destinazione.</span><span class="sxs-lookup"><span data-stu-id="61c3e-107">Optional name of target file.</span></span>  
  
 `fSmartImport`  
 <span data-ttu-id="61c3e-108">Se TRUE, viene utilizzato ImportTypes, in caso contrario l'importazione deve essere eseguita manualmente.</span><span class="sxs-lookup"><span data-stu-id="61c3e-108">If TRUE, ImportTypes is used, otherwise importing must be performed manually.</span></span>  
  
 `dwOpenFlags`  
 <span data-ttu-id="61c3e-109">Flag da passare a [OpenScope (metodo)](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscope-method.md).</span><span class="sxs-lookup"><span data-stu-id="61c3e-109">Flags to be passed along to [OpenScope Method](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscope-method.md).</span></span>  
  
 `pImportToken`  
 <span data-ttu-id="61c3e-110">Riceve l'ID del file da importare.</span><span class="sxs-lookup"><span data-stu-id="61c3e-110">Receives ID of the file being imported.</span></span>  
  
 `ppAssemblyScope`  
 <span data-ttu-id="61c3e-111">Riceve l'ambito di importazione assembly [interfaccia IMetaDataAssemblyImport](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md) interfaccia.</span><span class="sxs-lookup"><span data-stu-id="61c3e-111">Receives assembly import scope [IMetaDataAssemblyImport Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md) interface.</span></span> <span data-ttu-id="61c3e-112">È impostato su NULL se il file non è un assembly.</span><span class="sxs-lookup"><span data-stu-id="61c3e-112">Is set to NULL if file is not an assembly.</span></span>  
  
 `pdwCountOfScopes`  
 <span data-ttu-id="61c3e-113">Riceve il numero di file importati e/o gli ambiti.</span><span class="sxs-lookup"><span data-stu-id="61c3e-113">Receives count of imported files and/or scopes.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="61c3e-114">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="61c3e-114">Return Value</span></span>  
 <span data-ttu-id="61c3e-115">Se il metodo ha esito positivo, restituisce S_OK.</span><span class="sxs-lookup"><span data-stu-id="61c3e-115">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="61c3e-116">Requisiti</span><span class="sxs-lookup"><span data-stu-id="61c3e-116">Requirements</span></span>  
 <span data-ttu-id="61c3e-117">Richiede alink.h.</span><span class="sxs-lookup"><span data-stu-id="61c3e-117">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="61c3e-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="61c3e-118">See Also</span></span>  
 [<span data-ttu-id="61c3e-119">Interfaccia IALink2</span><span class="sxs-lookup"><span data-stu-id="61c3e-119">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="61c3e-120">Interfaccia IALink</span><span class="sxs-lookup"><span data-stu-id="61c3e-120">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="61c3e-121">Alink (API)</span><span class="sxs-lookup"><span data-stu-id="61c3e-121">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
