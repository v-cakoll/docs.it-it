---
title: Metodo ImportFileEx
ms.date: 03/30/2017
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3b3cf91ad4e048ddfccb4086f36923f33d754ac0
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59131040"
---
# <a name="importfileex-method"></a><span data-ttu-id="5b65a-102">Metodo ImportFileEx</span><span class="sxs-lookup"><span data-stu-id="5b65a-102">ImportFileEx Method</span></span>
<span data-ttu-id="5b65a-103">Importazioni indicato assembly o un modulo non associato.</span><span class="sxs-lookup"><span data-stu-id="5b65a-103">Imports indicated assembly or unbound module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5b65a-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5b65a-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="5b65a-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="5b65a-105">Parameters</span></span>  
 `pszFilename`  
 <span data-ttu-id="5b65a-106">Nome completo del file da cui importare.</span><span class="sxs-lookup"><span data-stu-id="5b65a-106">Fully qualified name of file from which to import.</span></span>  
  
 `pszTargetName`  
 <span data-ttu-id="5b65a-107">Nome facoltativo del file di destinazione.</span><span class="sxs-lookup"><span data-stu-id="5b65a-107">Optional name of target file.</span></span>  
  
 `fSmartImport`  
 <span data-ttu-id="5b65a-108">Se TRUE, viene usato ImportTypes, in caso contrario, l'importazione deve essere eseguita manualmente.</span><span class="sxs-lookup"><span data-stu-id="5b65a-108">If TRUE, ImportTypes is used, otherwise importing must be performed manually.</span></span>  
  
 `dwOpenFlags`  
 <span data-ttu-id="5b65a-109">Flag da passare insieme alla [metodo OpenScope](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscope-method.md).</span><span class="sxs-lookup"><span data-stu-id="5b65a-109">Flags to be passed along to [OpenScope Method](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscope-method.md).</span></span>  
  
 `pImportToken`  
 <span data-ttu-id="5b65a-110">Riceve l'ID del file da importare.</span><span class="sxs-lookup"><span data-stu-id="5b65a-110">Receives ID of the file being imported.</span></span>  
  
 `ppAssemblyScope`  
 <span data-ttu-id="5b65a-111">Ambito di importazione dell'assembly riceve [interfaccia IMetaDataAssemblyImport](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md) interfaccia.</span><span class="sxs-lookup"><span data-stu-id="5b65a-111">Receives assembly import scope [IMetaDataAssemblyImport Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md) interface.</span></span> <span data-ttu-id="5b65a-112">È impostato su NULL se il file non è un assembly.</span><span class="sxs-lookup"><span data-stu-id="5b65a-112">Is set to NULL if file is not an assembly.</span></span>  
  
 `pdwCountOfScopes`  
 <span data-ttu-id="5b65a-113">Riceve il numero di file importati e/o gli ambiti.</span><span class="sxs-lookup"><span data-stu-id="5b65a-113">Receives count of imported files and/or scopes.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5b65a-114">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="5b65a-114">Return Value</span></span>  
 <span data-ttu-id="5b65a-115">Restituisce S_OK se il metodo ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="5b65a-115">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5b65a-116">Requisiti</span><span class="sxs-lookup"><span data-stu-id="5b65a-116">Requirements</span></span>  
 <span data-ttu-id="5b65a-117">Richiede alink.h.</span><span class="sxs-lookup"><span data-stu-id="5b65a-117">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5b65a-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5b65a-118">See also</span></span>

- [<span data-ttu-id="5b65a-119">Interfaccia IALink2</span><span class="sxs-lookup"><span data-stu-id="5b65a-119">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="5b65a-120">Interfaccia IALink</span><span class="sxs-lookup"><span data-stu-id="5b65a-120">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="5b65a-121">Alink (API)</span><span class="sxs-lookup"><span data-stu-id="5b65a-121">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
