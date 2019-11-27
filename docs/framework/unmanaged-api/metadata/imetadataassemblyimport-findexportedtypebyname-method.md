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
ms.openlocfilehash: 3e470250fa0e86610fcc9a6d6e2ca03569d62b54
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74449456"
---
# <a name="imetadataassemblyimportfindexportedtypebyname-method"></a><span data-ttu-id="152a0-102">Metodo IMetaDataAssemblyImport::FindExportedTypeByName</span><span class="sxs-lookup"><span data-stu-id="152a0-102">IMetaDataAssemblyImport::FindExportedTypeByName Method</span></span>
<span data-ttu-id="152a0-103">Ottiene un puntatore a un tipo esportato, in base al nome e al tipo di inclusione.</span><span class="sxs-lookup"><span data-stu-id="152a0-103">Gets a pointer to an exported type, given its name and enclosing type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="152a0-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="152a0-104">Syntax</span></span>  
  
```cpp  
HRESULT FindExportedTypeByName (  
    [in]  LPCWSTR           szName,   
    [in]  mdToken           mdtExportedType,   
    [out] mdExportedType    *ptkExportedType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="152a0-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="152a0-105">Parameters</span></span>  
 `szName`  
 <span data-ttu-id="152a0-106">in Nome del tipo esportato.</span><span class="sxs-lookup"><span data-stu-id="152a0-106">[in] The name of the exported type.</span></span>  
  
 `mdtExportedType`  
 <span data-ttu-id="152a0-107">in Token di metadati per la classe contenitore del tipo esportato.</span><span class="sxs-lookup"><span data-stu-id="152a0-107">[in] The metadata token for the enclosing class of the exported type.</span></span> <span data-ttu-id="152a0-108">Questo valore è `mdExportedTypeNil` se il tipo esportato richiesto non è un tipo annidato.</span><span class="sxs-lookup"><span data-stu-id="152a0-108">This value is `mdExportedTypeNil` if the requested exported type is not a nested type.</span></span>  
  
 `ptkExportedType`  
 <span data-ttu-id="152a0-109">out Puntatore al token `mdExportedType` che rappresenta il tipo esportato.</span><span class="sxs-lookup"><span data-stu-id="152a0-109">[out] A pointer to the `mdExportedType` token that represents the exported type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="152a0-110">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="152a0-110">Remarks</span></span>  
 <span data-ttu-id="152a0-111">Il metodo `FindExportedTypeByName` utilizza le regole standard utilizzate dall'Common Language Runtime per la risoluzione dei riferimenti.</span><span class="sxs-lookup"><span data-stu-id="152a0-111">The `FindExportedTypeByName` method uses the standard rules employed by the common language runtime for resolving references.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="152a0-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="152a0-112">Requirements</span></span>  
 <span data-ttu-id="152a0-113">**Piattaforme:** vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="152a0-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="152a0-114">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="152a0-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="152a0-115">**Libreria:** Usato come risorsa in MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="152a0-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="152a0-116">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="152a0-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="152a0-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="152a0-117">See also</span></span>

- [<span data-ttu-id="152a0-118">Interfaccia IMetaDataAssemblyImport</span><span class="sxs-lookup"><span data-stu-id="152a0-118">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
- [<span data-ttu-id="152a0-119">Come il runtime individua gli assembly</span><span class="sxs-lookup"><span data-stu-id="152a0-119">How the Runtime Locates Assemblies</span></span>](../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)
