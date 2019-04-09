---
title: Metodo IMetaDataAssemblyImport::FindExportedTypeByName
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport.FindExportedTypeByName
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport::FindExportedTypeByName
helpviewer_keywords:
- FindExportedTypeByName method [.NET Framework metadata]
- IMetaDataAssemblyImport::FindExportedTypeByName method [.NET Framework metadata]
ms.assetid: 46264b2c-574d-4dde-aafc-77187a104fdd
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 32a7b7b498cc4e52b8be3f43ae52293de380d9f7
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59182260"
---
# <a name="imetadataassemblyimportfindexportedtypebyname-method"></a><span data-ttu-id="ce215-102">Metodo IMetaDataAssemblyImport::FindExportedTypeByName</span><span class="sxs-lookup"><span data-stu-id="ce215-102">IMetaDataAssemblyImport::FindExportedTypeByName Method</span></span>
<span data-ttu-id="ce215-103">Ottiene un puntatore a un tipo esportato, dato il nome e tipo di inclusione.</span><span class="sxs-lookup"><span data-stu-id="ce215-103">Gets a pointer to an exported type, given its name and enclosing type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ce215-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ce215-104">Syntax</span></span>  
  
```  
HRESULT FindExportedTypeByName (  
    [in]  LPCWSTR           szName,   
    [in]  mdToken           mdtExportedType,   
    [out] mdExportedType    *ptkExportedType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ce215-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="ce215-105">Parameters</span></span>  
 `szName`  
 <span data-ttu-id="ce215-106">[in] Il nome del tipo esportato.</span><span class="sxs-lookup"><span data-stu-id="ce215-106">[in] The name of the exported type.</span></span>  
  
 `mdtExportedType`  
 <span data-ttu-id="ce215-107">[in] Il token di metadati per la classe contenitore del tipo esportato.</span><span class="sxs-lookup"><span data-stu-id="ce215-107">[in] The metadata token for the enclosing class of the exported type.</span></span> <span data-ttu-id="ce215-108">Questo valore è `mdExportedTypeNil` se l'oggetto richiesto esportato tipo non è un tipo annidato.</span><span class="sxs-lookup"><span data-stu-id="ce215-108">This value is `mdExportedTypeNil` if the requested exported type is not a nested type.</span></span>  
  
 `ptkExportedType`  
 <span data-ttu-id="ce215-109">[out] Un puntatore al `mdExportedType` token che rappresenta il tipo esportato.</span><span class="sxs-lookup"><span data-stu-id="ce215-109">[out] A pointer to the `mdExportedType` token that represents the exported type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ce215-110">Note</span><span class="sxs-lookup"><span data-stu-id="ce215-110">Remarks</span></span>  
 <span data-ttu-id="ce215-111">Il `FindExportedTypeByName` metodo Usa le regole standard utilizzate da common language runtime per la risoluzione dei riferimenti.</span><span class="sxs-lookup"><span data-stu-id="ce215-111">The `FindExportedTypeByName` method uses the standard rules employed by the common language runtime for resolving references.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ce215-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ce215-112">Requirements</span></span>  
 <span data-ttu-id="ce215-113">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ce215-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ce215-114">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="ce215-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ce215-115">**Libreria:** Usato come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="ce215-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="ce215-116">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="ce215-116">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="ce215-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ce215-117">See also</span></span>

- [<span data-ttu-id="ce215-118">Interfaccia IMetaDataAssemblyImport</span><span class="sxs-lookup"><span data-stu-id="ce215-118">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
- [<span data-ttu-id="ce215-119">Come il runtime individua gli assembly</span><span class="sxs-lookup"><span data-stu-id="ce215-119">How the Runtime Locates Assemblies</span></span>](../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)
