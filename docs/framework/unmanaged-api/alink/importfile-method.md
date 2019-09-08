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
ms.openlocfilehash: f7fee7a91de99e2db69609cbc7c73e22d85d045f
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70777065"
---
# <a name="importfile-method"></a><span data-ttu-id="a630c-102">Metodo ImportFile</span><span class="sxs-lookup"><span data-stu-id="a630c-102">ImportFile Method</span></span>
<span data-ttu-id="a630c-103">Importa assembly e moduli non associati.</span><span class="sxs-lookup"><span data-stu-id="a630c-103">Imports assemblies and unbound modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a630c-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a630c-104">Syntax</span></span>  
  
```cpp  
HRESULT ImportFile(  
    LPCWSTR pszFilename,  
    LPCWSTR pszTargetName,  
    BOOL fSmartImport,  
    mdToken* pImportToken,  
    IMetaDataAssemblyImport** ppAssemblyScope,  
    DWORD* pdwCountOfScopes  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="a630c-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="a630c-105">Parameters</span></span>  
 `pszFilename`  
 <span data-ttu-id="a630c-106">Nome completo del file da importare.</span><span class="sxs-lookup"><span data-stu-id="a630c-106">Fully qualified name of file to be imported.</span></span>  
  
 `pszTargetName`  
 <span data-ttu-id="a630c-107">Nome del file di output facoltativo che può essere usato per rinominare il file mentre è collegato nell'assembly.</span><span class="sxs-lookup"><span data-stu-id="a630c-107">Optional output file name that can be used to rename the file as it is linked into the assembly.</span></span>  
  
 `fSmartImport`  
 <span data-ttu-id="a630c-108">Se TRUE, viene usato ImportTypes. in caso contrario, l'importazione deve essere eseguita manualmente.</span><span class="sxs-lookup"><span data-stu-id="a630c-108">If TRUE, ImportTypes is used, otherwise importing must be performed manually.</span></span>  
  
 `pImportToken`  
 <span data-ttu-id="a630c-109">Puntatore al token in cui verrà archiviato un ID file univoco.</span><span class="sxs-lookup"><span data-stu-id="a630c-109">Pointer to token where a unique file ID will be stored.</span></span> <span data-ttu-id="a630c-110">Il file può essere un assembly o un file.</span><span class="sxs-lookup"><span data-stu-id="a630c-110">The file can be an assembly or a file.</span></span>  
  
 `ppAssemblyScope`  
 <span data-ttu-id="a630c-111">Riceve il puntatore all' [Interfaccia IMetaDataAssemblyImport](../metadata/imetadataassemblyimport-interface.md).</span><span class="sxs-lookup"><span data-stu-id="a630c-111">Receives pointer to [IMetaDataAssemblyImport Interface](../metadata/imetadataassemblyimport-interface.md).</span></span> <span data-ttu-id="a630c-112">Può essere NULL se il file non è un assembly.</span><span class="sxs-lookup"><span data-stu-id="a630c-112">Can be NULL if the file is not an assembly.</span></span>  
  
 `pdwCountOfScopes`  
 <span data-ttu-id="a630c-113">Puntatore al conteggio dei file e/o degli ambiti che sono stati importati.</span><span class="sxs-lookup"><span data-stu-id="a630c-113">Pointer to the count of files and/or scopes that have been imported.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a630c-114">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="a630c-114">Return Value</span></span>  
 <span data-ttu-id="a630c-115">Restituisce S_OK se il metodo ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="a630c-115">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a630c-116">Requisiti</span><span class="sxs-lookup"><span data-stu-id="a630c-116">Requirements</span></span>  
 <span data-ttu-id="a630c-117">Richiede ALink. h</span><span class="sxs-lookup"><span data-stu-id="a630c-117">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a630c-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a630c-118">See also</span></span>

- [<span data-ttu-id="a630c-119">Interfaccia IALink</span><span class="sxs-lookup"><span data-stu-id="a630c-119">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="a630c-120">Interfaccia IALink2</span><span class="sxs-lookup"><span data-stu-id="a630c-120">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="a630c-121">Alink (API)</span><span class="sxs-lookup"><span data-stu-id="a630c-121">ALink API</span></span>](index.md)
