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
ms.openlocfilehash: a1c950e9a6e53e04cc0f2e52a140612562b32ff1
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70776975"
---
# <a name="importfileex2-method"></a><span data-ttu-id="834c6-102">Metodo ImportFileEx2</span><span class="sxs-lookup"><span data-stu-id="834c6-102">ImportFileEx2 Method</span></span>
<span data-ttu-id="834c6-103">Importa assembly e moduli non associati.</span><span class="sxs-lookup"><span data-stu-id="834c6-103">Imports assemblies and unbound modules.</span></span> <span data-ttu-id="834c6-104">Questo metodo è simile al [metodo ImportFile](importfile-method.md), ma funziona anche se il file importato non esiste sul disco.</span><span class="sxs-lookup"><span data-stu-id="834c6-104">This method is like [ImportFile Method](importfile-method.md), but works even if the file being imported does not exist on disk.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="834c6-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="834c6-105">Syntax</span></span>  
  
```cpp  
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
  
## <a name="parameters"></a><span data-ttu-id="834c6-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="834c6-106">Parameters</span></span>  
 `pszFilename`  
 <span data-ttu-id="834c6-107">Nome del file da importare.</span><span class="sxs-lookup"><span data-stu-id="834c6-107">Name of file to be imported.</span></span>  
  
 `pszTargetName`  
 <span data-ttu-id="834c6-108">Nome facoltativo del file di destinazione.</span><span class="sxs-lookup"><span data-stu-id="834c6-108">Optional name of target file.</span></span>  
  
 `pAssemblyScopeIn`  
 <span data-ttu-id="834c6-109">Interfaccia dell' [Interfaccia IMetaDataAssemblyImport](../metadata/imetadataassemblyimport-interface.md) dell'ambito di importazione facoltativa.</span><span class="sxs-lookup"><span data-stu-id="834c6-109">Optional import scope [IMetaDataAssemblyImport Interface](../metadata/imetadataassemblyimport-interface.md) interface.</span></span>  
  
 `fSmartImport`  
 <span data-ttu-id="834c6-110">Se TRUE, viene usato ImportTypes. in caso contrario, l'importazione deve essere eseguita manualmente.</span><span class="sxs-lookup"><span data-stu-id="834c6-110">If TRUE, ImportTypes is used, otherwise importing must be performed manually.</span></span>  
  
 `dwOpenFlags`  
 <span data-ttu-id="834c6-111">Flag da passare al [Metodo OpenScope](../metadata/imetadatadispenser-openscope-method.md).</span><span class="sxs-lookup"><span data-stu-id="834c6-111">Flags to be passed along to [OpenScope Method](../metadata/imetadatadispenser-openscope-method.md).</span></span>  
  
 `pImportToken`  
 <span data-ttu-id="834c6-112">Riceve l'ID univoco per l'assembly o il file.</span><span class="sxs-lookup"><span data-stu-id="834c6-112">Receives unique ID for the assembly or file.</span></span>  
  
 `ppAssemblyScope`  
 <span data-ttu-id="834c6-113">Riceve l'interfaccia dell' [Interfaccia IMetaDataAssemblyImport](../metadata/imetadataassemblyimport-interface.md) dell'ambito di importazione assembly.</span><span class="sxs-lookup"><span data-stu-id="834c6-113">Receives assembly import scope [IMetaDataAssemblyImport Interface](../metadata/imetadataassemblyimport-interface.md) interface.</span></span> <span data-ttu-id="834c6-114">Può essere NULL se il file non è un assembly.</span><span class="sxs-lookup"><span data-stu-id="834c6-114">Can be NULL if the file is not an assembly.</span></span>  
  
 `pdwCountOfScopes`  
 <span data-ttu-id="834c6-115">Riceve il numero di file e/o ambiti importati.</span><span class="sxs-lookup"><span data-stu-id="834c6-115">Receives the number of files and/or scopes imported.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="834c6-116">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="834c6-116">Return Value</span></span>  
 <span data-ttu-id="834c6-117">Restituisce S_OK se il metodo ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="834c6-117">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="834c6-118">Requisiti</span><span class="sxs-lookup"><span data-stu-id="834c6-118">Requirements</span></span>  
 <span data-ttu-id="834c6-119">Richiede ALink. h.</span><span class="sxs-lookup"><span data-stu-id="834c6-119">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="834c6-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="834c6-120">See also</span></span>

- [<span data-ttu-id="834c6-121">Interfaccia IALink2</span><span class="sxs-lookup"><span data-stu-id="834c6-121">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="834c6-122">Interfaccia IALink</span><span class="sxs-lookup"><span data-stu-id="834c6-122">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="834c6-123">Alink (API)</span><span class="sxs-lookup"><span data-stu-id="834c6-123">ALink API</span></span>](index.md)
