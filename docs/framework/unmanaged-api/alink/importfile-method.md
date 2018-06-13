---
title: Metodo ImportFile
ms.date: 03/30/2017
api_name:
- IALink.ImportFile
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- ImportFile
helpviewer_keywords:
- ImportFile method
ms.assetid: bcbe321f-b83a-4e9a-9f10-8d913e244dc9
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 54b0a02af7f22e775e3f9567de79664c9805b4e2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33400650"
---
# <a name="importfile-method"></a><span data-ttu-id="82517-102">Metodo ImportFile</span><span class="sxs-lookup"><span data-stu-id="82517-102">ImportFile Method</span></span>
<span data-ttu-id="82517-103">Importa i moduli non associati e assembly.</span><span class="sxs-lookup"><span data-stu-id="82517-103">Imports assemblies and unbound modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="82517-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="82517-104">Syntax</span></span>  
  
```  
HRESULT ImportFile(  
    LPCWSTR pszFilename,  
    LPCWSTR pszTargetName,  
    BOOL fSmartImport,  
    mdToken* pImportToken,  
    IMetaDataAssemblyImport** ppAssemblyScope,  
    DWORD* pdwCountOfScopes  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="82517-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="82517-105">Parameters</span></span>  
 `pszFilename`  
 <span data-ttu-id="82517-106">Nome completo del file da importare.</span><span class="sxs-lookup"><span data-stu-id="82517-106">Fully qualified name of file to be imported.</span></span>  
  
 `pszTargetName`  
 <span data-ttu-id="82517-107">Nome di file di output facoltativo che può essere utilizzato per rinominare il file collegato nell'assembly.</span><span class="sxs-lookup"><span data-stu-id="82517-107">Optional output file name that can be used to rename the file as it is linked into the assembly.</span></span>  
  
 `fSmartImport`  
 <span data-ttu-id="82517-108">Se TRUE, viene utilizzato ImportTypes, in caso contrario l'importazione deve essere eseguita manualmente.</span><span class="sxs-lookup"><span data-stu-id="82517-108">If TRUE, ImportTypes is used, otherwise importing must be performed manually.</span></span>  
  
 `pImportToken`  
 <span data-ttu-id="82517-109">Puntatore al token in cui verrà archiviato un ID di file univoco.</span><span class="sxs-lookup"><span data-stu-id="82517-109">Pointer to token where a unique file ID will be stored.</span></span> <span data-ttu-id="82517-110">Il file può essere un assembly o un file.</span><span class="sxs-lookup"><span data-stu-id="82517-110">The file can be an assembly or a file.</span></span>  
  
 `ppAssemblyScope`  
 <span data-ttu-id="82517-111">Riceve il puntatore a [interfaccia IMetaDataAssemblyImport](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md).</span><span class="sxs-lookup"><span data-stu-id="82517-111">Receives pointer to [IMetaDataAssemblyImport Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md).</span></span> <span data-ttu-id="82517-112">Può essere NULL se il file non è un assembly.</span><span class="sxs-lookup"><span data-stu-id="82517-112">Can be NULL if the file is not an assembly.</span></span>  
  
 `pdwCountOfScopes`  
 <span data-ttu-id="82517-113">Puntatore al numero di file e/o gli ambiti che sono stati importati.</span><span class="sxs-lookup"><span data-stu-id="82517-113">Pointer to the count of files and/or scopes that have been imported.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="82517-114">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="82517-114">Return Value</span></span>  
 <span data-ttu-id="82517-115">Se il metodo ha esito positivo, restituisce S_OK.</span><span class="sxs-lookup"><span data-stu-id="82517-115">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="82517-116">Requisiti</span><span class="sxs-lookup"><span data-stu-id="82517-116">Requirements</span></span>  
 <span data-ttu-id="82517-117">Richiede alink.h</span><span class="sxs-lookup"><span data-stu-id="82517-117">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="82517-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="82517-118">See Also</span></span>  
 [<span data-ttu-id="82517-119">Interfaccia IALink</span><span class="sxs-lookup"><span data-stu-id="82517-119">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="82517-120">Interfaccia IALink2</span><span class="sxs-lookup"><span data-stu-id="82517-120">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="82517-121">Alink (API)</span><span class="sxs-lookup"><span data-stu-id="82517-121">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
