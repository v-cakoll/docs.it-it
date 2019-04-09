---
title: Metodo ImportFileEx2
ms.date: 03/30/2017
api_name:
- IALink2.ImportFileEx2
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- ImportFileEx2
helpviewer_keywords:
- ImportFileEx2 method
ms.assetid: 02c789fd-16fc-48c6-9619-56e87e2a37ca
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 784e58e0c5c2329705671580d53763f2ac30f0b2
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59201351"
---
# <a name="importfileex2-method"></a><span data-ttu-id="c284a-102">Metodo ImportFileEx2</span><span class="sxs-lookup"><span data-stu-id="c284a-102">ImportFileEx2 Method</span></span>
<span data-ttu-id="c284a-103">Importa moduli non associati e assembly.</span><span class="sxs-lookup"><span data-stu-id="c284a-103">Imports assemblies and unbound modules.</span></span> <span data-ttu-id="c284a-104">Questo metodo è simile [metodo ImportFile](../../../../docs/framework/unmanaged-api/alink/importfile-method.md), ma funziona anche se il file da importare non esiste sul disco.</span><span class="sxs-lookup"><span data-stu-id="c284a-104">This method is like [ImportFile Method](../../../../docs/framework/unmanaged-api/alink/importfile-method.md), but works even if the file being imported does not exist on disk.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c284a-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c284a-105">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="c284a-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="c284a-106">Parameters</span></span>  
 `pszFilename`  
 <span data-ttu-id="c284a-107">Nome del file da importare.</span><span class="sxs-lookup"><span data-stu-id="c284a-107">Name of file to be imported.</span></span>  
  
 `pszTargetName`  
 <span data-ttu-id="c284a-108">Nome facoltativo del file di destinazione.</span><span class="sxs-lookup"><span data-stu-id="c284a-108">Optional name of target file.</span></span>  
  
 `pAssemblyScopeIn`  
 <span data-ttu-id="c284a-109">Ambito di importazione opzionale [interfaccia IMetaDataAssemblyImport](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md) interfaccia.</span><span class="sxs-lookup"><span data-stu-id="c284a-109">Optional import scope [IMetaDataAssemblyImport Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md) interface.</span></span>  
  
 `fSmartImport`  
 <span data-ttu-id="c284a-110">Se TRUE, viene usato ImportTypes, in caso contrario, l'importazione deve essere eseguita manualmente.</span><span class="sxs-lookup"><span data-stu-id="c284a-110">If TRUE, ImportTypes is used, otherwise importing must be performed manually.</span></span>  
  
 `dwOpenFlags`  
 <span data-ttu-id="c284a-111">Flag da passare insieme alla [metodo OpenScope](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscope-method.md).</span><span class="sxs-lookup"><span data-stu-id="c284a-111">Flags to be passed along to [OpenScope Method](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscope-method.md).</span></span>  
  
 `pImportToken`  
 <span data-ttu-id="c284a-112">Riceve l'ID univoco per l'assembly o file.</span><span class="sxs-lookup"><span data-stu-id="c284a-112">Receives unique ID for the assembly or file.</span></span>  
  
 `ppAssemblyScope`  
 <span data-ttu-id="c284a-113">Ambito di importazione dell'assembly riceve [interfaccia IMetaDataAssemblyImport](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md) interfaccia.</span><span class="sxs-lookup"><span data-stu-id="c284a-113">Receives assembly import scope [IMetaDataAssemblyImport Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md) interface.</span></span> <span data-ttu-id="c284a-114">Può essere NULL se il file non è un assembly.</span><span class="sxs-lookup"><span data-stu-id="c284a-114">Can be NULL if the file is not an assembly.</span></span>  
  
 `pdwCountOfScopes`  
 <span data-ttu-id="c284a-115">Riceve il numero di file e/o ambiti importati.</span><span class="sxs-lookup"><span data-stu-id="c284a-115">Receives the number of files and/or scopes imported.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c284a-116">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="c284a-116">Return Value</span></span>  
 <span data-ttu-id="c284a-117">Restituisce S_OK se il metodo ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="c284a-117">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c284a-118">Requisiti</span><span class="sxs-lookup"><span data-stu-id="c284a-118">Requirements</span></span>  
 <span data-ttu-id="c284a-119">Richiede alink.h.</span><span class="sxs-lookup"><span data-stu-id="c284a-119">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c284a-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c284a-120">See also</span></span>

- [<span data-ttu-id="c284a-121">Interfaccia IALink2</span><span class="sxs-lookup"><span data-stu-id="c284a-121">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="c284a-122">Interfaccia IALink</span><span class="sxs-lookup"><span data-stu-id="c284a-122">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="c284a-123">API Alink</span><span class="sxs-lookup"><span data-stu-id="c284a-123">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
