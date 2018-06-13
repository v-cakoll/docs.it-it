---
title: Metodo ImportFile2
ms.date: 03/30/2017
api_name:
- IALink.ImportFile2
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- ImportFile2
helpviewer_keywords:
- ImportFile2 method
ms.assetid: 9a6be861-c260-4a35-acea-3372ea515a0f
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 61bc7783823408164ae2b073e097a0e85e193be6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33401242"
---
# <a name="importfile2-method"></a><span data-ttu-id="4aba5-102">Metodo ImportFile2</span><span class="sxs-lookup"><span data-stu-id="4aba5-102">ImportFile2 Method</span></span>
<span data-ttu-id="4aba5-103">Importa i moduli non associati e assembly.</span><span class="sxs-lookup"><span data-stu-id="4aba5-103">Imports assemblies and unbound modules.</span></span> <span data-ttu-id="4aba5-104">Questo metodo è simile [metodo ImportFile](../../../../docs/framework/unmanaged-api/alink/importfile-method.md), ma funziona anche se il file da importare non esiste sul disco.</span><span class="sxs-lookup"><span data-stu-id="4aba5-104">This method is like [ImportFile Method](../../../../docs/framework/unmanaged-api/alink/importfile-method.md), but works even if the file being imported does not exist on disk.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4aba5-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4aba5-105">Syntax</span></span>  
  
```  
HRESULT ImportFile2(  
    LPCWSTR         pszFilename,  
    LPCWSTR         pszTargetName,  
    IMetaDataAssemblyImport* pAssemblyScopeIn,  
    BOOL            fSmartImport,  
    mdToken*        pImportToken,  
    IMetaDataAssemblyImport** ppAssemblyScope,  
    DWORD*          pdwCountOfScopes  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4aba5-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="4aba5-106">Parameters</span></span>  
 `pszFilename`  
 <span data-ttu-id="4aba5-107">Nome del file da importare.</span><span class="sxs-lookup"><span data-stu-id="4aba5-107">Name of file to be imported.</span></span>  
  
 `pszTargetName`  
 <span data-ttu-id="4aba5-108">Nome di file di output facoltativo che può essere utilizzato per rinominare il file collegato nell'assembly.</span><span class="sxs-lookup"><span data-stu-id="4aba5-108">Optional output file name that can be used to rename the file as it is linked into the assembly.</span></span>  
  
 `pAssemblyScopeIn`  
 <span data-ttu-id="4aba5-109">Ambito facoltativo [interfaccia IMetaDataAssemblyImport](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md) interfaccia.</span><span class="sxs-lookup"><span data-stu-id="4aba5-109">Optional scope [IMetaDataAssemblyImport Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md) interface.</span></span>  
  
 `fSmartImport`  
 <span data-ttu-id="4aba5-110">Se TRUE, viene utilizzato ImportTypes, in caso contrario l'importazione deve essere eseguita manualmente.</span><span class="sxs-lookup"><span data-stu-id="4aba5-110">If TRUE, ImportTypes is used, otherwise importing must be performed manually.</span></span>  
  
 `pImportToken`  
 <span data-ttu-id="4aba5-111">Riceve l'ID per i file di assembly.</span><span class="sxs-lookup"><span data-stu-id="4aba5-111">Receives the ID for the file or assembly.</span></span>  
  
 `ppAssemblyScope`  
 <span data-ttu-id="4aba5-112">Riceve il [interfaccia IMetaDataAssemblyImport](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md) interfaccia.</span><span class="sxs-lookup"><span data-stu-id="4aba5-112">Receives the [IMetaDataAssemblyImport Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md) interface.</span></span> <span data-ttu-id="4aba5-113">NULL se il file non è un assembly.</span><span class="sxs-lookup"><span data-stu-id="4aba5-113">NULL if the file is not an assembly.</span></span>  
  
 `pdwCountOfScopes`  
 <span data-ttu-id="4aba5-114">Riceve il conteggio dei file e/o gli ambiti di importazione.</span><span class="sxs-lookup"><span data-stu-id="4aba5-114">Receives the found of files and/or scopes imported.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4aba5-115">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="4aba5-115">Return Value</span></span>  
 <span data-ttu-id="4aba5-116">Se il metodo ha esito positivo, restituisce S_OK.</span><span class="sxs-lookup"><span data-stu-id="4aba5-116">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4aba5-117">Requisiti</span><span class="sxs-lookup"><span data-stu-id="4aba5-117">Requirements</span></span>  
 <span data-ttu-id="4aba5-118">Richiede alink.h.</span><span class="sxs-lookup"><span data-stu-id="4aba5-118">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4aba5-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4aba5-119">See Also</span></span>  
 [<span data-ttu-id="4aba5-120">Interfaccia IALink</span><span class="sxs-lookup"><span data-stu-id="4aba5-120">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="4aba5-121">Interfaccia IALink2</span><span class="sxs-lookup"><span data-stu-id="4aba5-121">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="4aba5-122">Alink (API)</span><span class="sxs-lookup"><span data-stu-id="4aba5-122">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
