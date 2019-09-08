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
ms.openlocfilehash: a03fc24e5ef932d13c0d195f53c703cdd3ff45ff
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70776934"
---
# <a name="importfile2-method"></a><span data-ttu-id="af137-102">Metodo ImportFile2</span><span class="sxs-lookup"><span data-stu-id="af137-102">ImportFile2 Method</span></span>
<span data-ttu-id="af137-103">Importa assembly e moduli non associati.</span><span class="sxs-lookup"><span data-stu-id="af137-103">Imports assemblies and unbound modules.</span></span> <span data-ttu-id="af137-104">Questo metodo è simile al [metodo ImportFile](importfile-method.md), ma funziona anche se il file importato non esiste sul disco.</span><span class="sxs-lookup"><span data-stu-id="af137-104">This method is like [ImportFile Method](importfile-method.md), but works even if the file being imported does not exist on disk.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="af137-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="af137-105">Syntax</span></span>  
  
```cpp  
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
  
## <a name="parameters"></a><span data-ttu-id="af137-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="af137-106">Parameters</span></span>  
 `pszFilename`  
 <span data-ttu-id="af137-107">Nome del file da importare.</span><span class="sxs-lookup"><span data-stu-id="af137-107">Name of file to be imported.</span></span>  
  
 `pszTargetName`  
 <span data-ttu-id="af137-108">Nome del file di output facoltativo che può essere usato per rinominare il file mentre è collegato nell'assembly.</span><span class="sxs-lookup"><span data-stu-id="af137-108">Optional output file name that can be used to rename the file as it is linked into the assembly.</span></span>  
  
 `pAssemblyScopeIn`  
 <span data-ttu-id="af137-109">Interfaccia facoltativa dell' [Interfaccia IMetaDataAssemblyImport](../metadata/imetadataassemblyimport-interface.md) dell'ambito.</span><span class="sxs-lookup"><span data-stu-id="af137-109">Optional scope [IMetaDataAssemblyImport Interface](../metadata/imetadataassemblyimport-interface.md) interface.</span></span>  
  
 `fSmartImport`  
 <span data-ttu-id="af137-110">Se TRUE, viene usato ImportTypes. in caso contrario, l'importazione deve essere eseguita manualmente.</span><span class="sxs-lookup"><span data-stu-id="af137-110">If TRUE, ImportTypes is used, otherwise importing must be performed manually.</span></span>  
  
 `pImportToken`  
 <span data-ttu-id="af137-111">Riceve l'ID per il file o l'assembly.</span><span class="sxs-lookup"><span data-stu-id="af137-111">Receives the ID for the file or assembly.</span></span>  
  
 `ppAssemblyScope`  
 <span data-ttu-id="af137-112">Riceve l'interfaccia dell' [Interfaccia IMetaDataAssemblyImport](../metadata/imetadataassemblyimport-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="af137-112">Receives the [IMetaDataAssemblyImport Interface](../metadata/imetadataassemblyimport-interface.md) interface.</span></span> <span data-ttu-id="af137-113">NULL se il file non è un assembly.</span><span class="sxs-lookup"><span data-stu-id="af137-113">NULL if the file is not an assembly.</span></span>  
  
 `pdwCountOfScopes`  
 <span data-ttu-id="af137-114">Riceve l'oggetto trovato dei file e/o degli ambiti importati.</span><span class="sxs-lookup"><span data-stu-id="af137-114">Receives the found of files and/or scopes imported.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="af137-115">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="af137-115">Return Value</span></span>  
 <span data-ttu-id="af137-116">Restituisce S_OK se il metodo ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="af137-116">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="af137-117">Requisiti</span><span class="sxs-lookup"><span data-stu-id="af137-117">Requirements</span></span>  
 <span data-ttu-id="af137-118">Richiede ALink. h.</span><span class="sxs-lookup"><span data-stu-id="af137-118">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="af137-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="af137-119">See also</span></span>

- [<span data-ttu-id="af137-120">Interfaccia IALink</span><span class="sxs-lookup"><span data-stu-id="af137-120">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="af137-121">Interfaccia IALink2</span><span class="sxs-lookup"><span data-stu-id="af137-121">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="af137-122">Alink (API)</span><span class="sxs-lookup"><span data-stu-id="af137-122">ALink API</span></span>](index.md)
