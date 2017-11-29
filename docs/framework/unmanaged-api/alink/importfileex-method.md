---
title: Metodo ImportFileEx
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IALink2.ImportFileEx
api_location: alink.dll
api_type: COM
f1_keywords: ImportFileEx
helpviewer_keywords: ImportFileEx method
ms.assetid: ad276f3f-b303-46ac-97e0-66a377adaa4f
topic_type: apiref
caps.latest.revision: "7"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 71a7bc1ba9f23f1c581ca3528752e04003d9857c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="importfileex-method"></a><span data-ttu-id="06d71-102">Metodo ImportFileEx</span><span class="sxs-lookup"><span data-stu-id="06d71-102">ImportFileEx Method</span></span>
<span data-ttu-id="06d71-103">Importazioni indicato assembly o un modulo non associato.</span><span class="sxs-lookup"><span data-stu-id="06d71-103">Imports indicated assembly or unbound module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="06d71-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="06d71-104">Syntax</span></span>  
  
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
  
#### <a name="parameters"></a><span data-ttu-id="06d71-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="06d71-105">Parameters</span></span>  
 `pszFilename`  
 <span data-ttu-id="06d71-106">Nome completo del file da cui importare.</span><span class="sxs-lookup"><span data-stu-id="06d71-106">Fully qualified name of file from which to import.</span></span>  
  
 `pszTargetName`  
 <span data-ttu-id="06d71-107">Nome facoltativo di file di destinazione.</span><span class="sxs-lookup"><span data-stu-id="06d71-107">Optional name of target file.</span></span>  
  
 `fSmartImport`  
 <span data-ttu-id="06d71-108">Se TRUE, viene utilizzato ImportTypes, in caso contrario l'importazione deve essere eseguita manualmente.</span><span class="sxs-lookup"><span data-stu-id="06d71-108">If TRUE, ImportTypes is used, otherwise importing must be performed manually.</span></span>  
  
 `dwOpenFlags`  
 <span data-ttu-id="06d71-109">Flag da passare a [OpenScope (metodo)](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscope-method.md).</span><span class="sxs-lookup"><span data-stu-id="06d71-109">Flags to be passed along to [OpenScope Method](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscope-method.md).</span></span>  
  
 `pImportToken`  
 <span data-ttu-id="06d71-110">Riceve l'ID del file da importare.</span><span class="sxs-lookup"><span data-stu-id="06d71-110">Receives ID of the file being imported.</span></span>  
  
 `ppAssemblyScope`  
 <span data-ttu-id="06d71-111">Riceve l'ambito di importazione assembly [interfaccia IMetaDataAssemblyImport](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md) interfaccia.</span><span class="sxs-lookup"><span data-stu-id="06d71-111">Receives assembly import scope [IMetaDataAssemblyImport Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md) interface.</span></span> <span data-ttu-id="06d71-112">È impostato su NULL se il file non è un assembly.</span><span class="sxs-lookup"><span data-stu-id="06d71-112">Is set to NULL if file is not an assembly.</span></span>  
  
 `pdwCountOfScopes`  
 <span data-ttu-id="06d71-113">Riceve il numero di file importati e/o gli ambiti.</span><span class="sxs-lookup"><span data-stu-id="06d71-113">Receives count of imported files and/or scopes.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="06d71-114">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="06d71-114">Return Value</span></span>  
 <span data-ttu-id="06d71-115">Se il metodo ha esito positivo, restituisce S_OK.</span><span class="sxs-lookup"><span data-stu-id="06d71-115">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="06d71-116">Requisiti</span><span class="sxs-lookup"><span data-stu-id="06d71-116">Requirements</span></span>  
 <span data-ttu-id="06d71-117">Richiede alink.h.</span><span class="sxs-lookup"><span data-stu-id="06d71-117">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="06d71-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="06d71-118">See Also</span></span>  
 [<span data-ttu-id="06d71-119">Interfaccia IALink2</span><span class="sxs-lookup"><span data-stu-id="06d71-119">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="06d71-120">Interfaccia IALink</span><span class="sxs-lookup"><span data-stu-id="06d71-120">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="06d71-121">ALink (API)</span><span class="sxs-lookup"><span data-stu-id="06d71-121">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
