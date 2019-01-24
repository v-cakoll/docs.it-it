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
ms.openlocfilehash: 1b2b7559c203e5d357dd6921ea6862fbb5ec90a1
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54576187"
---
# <a name="imetadataassemblyimportfindexportedtypebyname-method"></a><span data-ttu-id="31837-102">Metodo IMetaDataAssemblyImport::FindExportedTypeByName</span><span class="sxs-lookup"><span data-stu-id="31837-102">IMetaDataAssemblyImport::FindExportedTypeByName Method</span></span>
<span data-ttu-id="31837-103">Ottiene un puntatore a un tipo esportato, dato il nome e tipo di inclusione.</span><span class="sxs-lookup"><span data-stu-id="31837-103">Gets a pointer to an exported type, given its name and enclosing type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="31837-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="31837-104">Syntax</span></span>  
  
```  
HRESULT FindExportedTypeByName (  
    [in]  LPCWSTR           szName,   
    [in]  mdToken           mdtExportedType,   
    [out] mdExportedType    *ptkExportedType  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="31837-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="31837-105">Parameters</span></span>  
 `szName`  
 <span data-ttu-id="31837-106">[in] Il nome del tipo esportato.</span><span class="sxs-lookup"><span data-stu-id="31837-106">[in] The name of the exported type.</span></span>  
  
 `mdtExportedType`  
 <span data-ttu-id="31837-107">[in] Il token di metadati per la classe contenitore del tipo esportato.</span><span class="sxs-lookup"><span data-stu-id="31837-107">[in] The metadata token for the enclosing class of the exported type.</span></span> <span data-ttu-id="31837-108">Questo valore è `mdExportedTypeNil` se l'oggetto richiesto esportato tipo non è un tipo annidato.</span><span class="sxs-lookup"><span data-stu-id="31837-108">This value is `mdExportedTypeNil` if the requested exported type is not a nested type.</span></span>  
  
 `ptkExportedType`  
 <span data-ttu-id="31837-109">[out] Un puntatore al `mdExportedType` token che rappresenta il tipo esportato.</span><span class="sxs-lookup"><span data-stu-id="31837-109">[out] A pointer to the `mdExportedType` token that represents the exported type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="31837-110">Note</span><span class="sxs-lookup"><span data-stu-id="31837-110">Remarks</span></span>  
 <span data-ttu-id="31837-111">Il `FindExportedTypeByName` metodo Usa le regole standard utilizzate da common language runtime per la risoluzione dei riferimenti.</span><span class="sxs-lookup"><span data-stu-id="31837-111">The `FindExportedTypeByName` method uses the standard rules employed by the common language runtime for resolving references.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="31837-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="31837-112">Requirements</span></span>  
 <span data-ttu-id="31837-113">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="31837-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="31837-114">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="31837-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="31837-115">**Libreria:** Usato come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="31837-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="31837-116">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="31837-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="31837-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="31837-117">See also</span></span>
- [<span data-ttu-id="31837-118">Interfaccia IMetaDataAssemblyImport</span><span class="sxs-lookup"><span data-stu-id="31837-118">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
- [<span data-ttu-id="31837-119">Come il runtime individua gli assembly</span><span class="sxs-lookup"><span data-stu-id="31837-119">How the Runtime Locates Assemblies</span></span>](../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)
