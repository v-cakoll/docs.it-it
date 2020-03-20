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
ms.openlocfilehash: edfe5de9c9d7ef9607a2eea5146194bbd4393a92
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175993"
---
# <a name="imetadataassemblyimportfindexportedtypebyname-method"></a><span data-ttu-id="92aca-102">Metodo IMetaDataAssemblyImport::FindExportedTypeByName</span><span class="sxs-lookup"><span data-stu-id="92aca-102">IMetaDataAssemblyImport::FindExportedTypeByName Method</span></span>
<span data-ttu-id="92aca-103">Ottiene un puntatore a un tipo esportato, dati il nome e il tipo di inclusione.</span><span class="sxs-lookup"><span data-stu-id="92aca-103">Gets a pointer to an exported type, given its name and enclosing type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="92aca-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="92aca-104">Syntax</span></span>  
  
```cpp  
HRESULT FindExportedTypeByName (  
    [in]  LPCWSTR           szName,
    [in]  mdToken           mdtExportedType,
    [out] mdExportedType    *ptkExportedType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="92aca-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="92aca-105">Parameters</span></span>  
 `szName`  
 <span data-ttu-id="92aca-106">[in] Nome del tipo esportato.</span><span class="sxs-lookup"><span data-stu-id="92aca-106">[in] The name of the exported type.</span></span>  
  
 `mdtExportedType`  
 <span data-ttu-id="92aca-107">[in] Token di metadati per la classe contenitore del tipo esportato.</span><span class="sxs-lookup"><span data-stu-id="92aca-107">[in] The metadata token for the enclosing class of the exported type.</span></span> <span data-ttu-id="92aca-108">Questo valore `mdExportedTypeNil` è se il tipo esportato richiesto non è un tipo annidato.</span><span class="sxs-lookup"><span data-stu-id="92aca-108">This value is `mdExportedTypeNil` if the requested exported type is not a nested type.</span></span>  
  
 `ptkExportedType`  
 <span data-ttu-id="92aca-109">[fuori] Puntatore al `mdExportedType` token che rappresenta il tipo esportato.</span><span class="sxs-lookup"><span data-stu-id="92aca-109">[out] A pointer to the `mdExportedType` token that represents the exported type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="92aca-110">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="92aca-110">Remarks</span></span>  
 <span data-ttu-id="92aca-111">Il `FindExportedTypeByName` metodo utilizza le regole standard utilizzate da Common Language Runtime per la risoluzione dei riferimenti.</span><span class="sxs-lookup"><span data-stu-id="92aca-111">The `FindExportedTypeByName` method uses the standard rules employed by the common language runtime for resolving references.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="92aca-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="92aca-112">Requirements</span></span>  
 <span data-ttu-id="92aca-113">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="92aca-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="92aca-114">**Intestazione:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="92aca-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="92aca-115">**Biblioteca:** Utilizzato come risorsa in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="92aca-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="92aca-116">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="92aca-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="92aca-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="92aca-117">See also</span></span>

- [<span data-ttu-id="92aca-118">Interfaccia IMetaDataAssemblyImport</span><span class="sxs-lookup"><span data-stu-id="92aca-118">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
- [<span data-ttu-id="92aca-119">Come il runtime individua gli assembly</span><span class="sxs-lookup"><span data-stu-id="92aca-119">How the Runtime Locates Assemblies</span></span>](../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)
