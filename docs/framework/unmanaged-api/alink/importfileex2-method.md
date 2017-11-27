---
title: Metodo ImportFileEx2
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IALink2.ImportFileEx2
api_location: alink.dll
api_type: COM
f1_keywords: ImportFileEx2
helpviewer_keywords: ImportFileEx2 method
ms.assetid: 02c789fd-16fc-48c6-9619-56e87e2a37ca
topic_type: apiref
caps.latest.revision: "7"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: c2416a630f9bd763d4d4d31170cc606b160bb854
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="importfileex2-method"></a><span data-ttu-id="b82d7-102">Metodo ImportFileEx2</span><span class="sxs-lookup"><span data-stu-id="b82d7-102">ImportFileEx2 Method</span></span>
<span data-ttu-id="b82d7-103">Importa i moduli non associati e assembly.</span><span class="sxs-lookup"><span data-stu-id="b82d7-103">Imports assemblies and unbound modules.</span></span> <span data-ttu-id="b82d7-104">Questo metodo è simile [metodo ImportFile](../../../../docs/framework/unmanaged-api/alink/importfile-method.md), ma funziona anche se il file da importare non esiste sul disco.</span><span class="sxs-lookup"><span data-stu-id="b82d7-104">This method is like [ImportFile Method](../../../../docs/framework/unmanaged-api/alink/importfile-method.md), but works even if the file being imported does not exist on disk.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b82d7-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b82d7-105">Syntax</span></span>  
  
```  
HRESULT ImportFileEx2(  
    LPCWSTR pszFilename,  
    LPCWSTR pszTargetName,  
    IMetaDataAssemblyImport* pAssemblyScopeIn,  
    BOOL fSmartImport,  
    DWORD dwOpenFlags,  
    mdToken* pImportToken,  
    IMetaDataAssemblyImport** ppAssemblyScope,  
    DWORD* pdwCountOfScopes  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b82d7-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="b82d7-106">Parameters</span></span>  
 `pszFilename`  
 <span data-ttu-id="b82d7-107">Nome del file da importare.</span><span class="sxs-lookup"><span data-stu-id="b82d7-107">Name of file to be imported.</span></span>  
  
 `pszTargetName`  
 <span data-ttu-id="b82d7-108">Nome facoltativo di file di destinazione.</span><span class="sxs-lookup"><span data-stu-id="b82d7-108">Optional name of target file.</span></span>  
  
 `pAssemblyScopeIn`  
 <span data-ttu-id="b82d7-109">Ambito di importazione opzionale [interfaccia IMetaDataAssemblyImport](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md) interfaccia.</span><span class="sxs-lookup"><span data-stu-id="b82d7-109">Optional import scope [IMetaDataAssemblyImport Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md) interface.</span></span>  
  
 `fSmartImport`  
 <span data-ttu-id="b82d7-110">Se TRUE, viene utilizzato ImportTypes, in caso contrario l'importazione deve essere eseguita manualmente.</span><span class="sxs-lookup"><span data-stu-id="b82d7-110">If TRUE, ImportTypes is used, otherwise importing must be performed manually.</span></span>  
  
 `dwOpenFlags`  
 <span data-ttu-id="b82d7-111">Flag da passare a [OpenScope (metodo)](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscope-method.md).</span><span class="sxs-lookup"><span data-stu-id="b82d7-111">Flags to be passed along to [OpenScope Method](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscope-method.md).</span></span>  
  
 `pImportToken`  
 <span data-ttu-id="b82d7-112">Riceve un ID univoco per l'assembly o file.</span><span class="sxs-lookup"><span data-stu-id="b82d7-112">Receives unique ID for the assembly or file.</span></span>  
  
 `ppAssemblyScope`  
 <span data-ttu-id="b82d7-113">Riceve l'ambito di importazione assembly [interfaccia IMetaDataAssemblyImport](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md) interfaccia.</span><span class="sxs-lookup"><span data-stu-id="b82d7-113">Receives assembly import scope [IMetaDataAssemblyImport Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md) interface.</span></span> <span data-ttu-id="b82d7-114">Può essere NULL se il file non è un assembly.</span><span class="sxs-lookup"><span data-stu-id="b82d7-114">Can be NULL if the file is not an assembly.</span></span>  
  
 `pdwCountOfScopes`  
 <span data-ttu-id="b82d7-115">Riceve il numero di file e/o gli ambiti di importazione.</span><span class="sxs-lookup"><span data-stu-id="b82d7-115">Receives the number of files and/or scopes imported.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b82d7-116">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="b82d7-116">Return Value</span></span>  
 <span data-ttu-id="b82d7-117">Se il metodo ha esito positivo, restituisce S_OK.</span><span class="sxs-lookup"><span data-stu-id="b82d7-117">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b82d7-118">Requisiti</span><span class="sxs-lookup"><span data-stu-id="b82d7-118">Requirements</span></span>  
 <span data-ttu-id="b82d7-119">Richiede alink.h.</span><span class="sxs-lookup"><span data-stu-id="b82d7-119">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b82d7-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b82d7-120">See Also</span></span>  
 [<span data-ttu-id="b82d7-121">Interfaccia IALink2</span><span class="sxs-lookup"><span data-stu-id="b82d7-121">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="b82d7-122">Interfaccia IALink</span><span class="sxs-lookup"><span data-stu-id="b82d7-122">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="b82d7-123">ALink (API)</span><span class="sxs-lookup"><span data-stu-id="b82d7-123">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
