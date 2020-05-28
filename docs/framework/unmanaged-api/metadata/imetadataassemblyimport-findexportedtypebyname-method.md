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
ms.openlocfilehash: ac6de9a16fad6ba9d14f3960ddd28c42c111f254
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2020
ms.locfileid: "84009392"
---
# <a name="imetadataassemblyimportfindexportedtypebyname-method"></a><span data-ttu-id="d3567-102">Metodo IMetaDataAssemblyImport::FindExportedTypeByName</span><span class="sxs-lookup"><span data-stu-id="d3567-102">IMetaDataAssemblyImport::FindExportedTypeByName Method</span></span>
<span data-ttu-id="d3567-103">Ottiene un puntatore a un tipo esportato, in base al nome e al tipo di inclusione.</span><span class="sxs-lookup"><span data-stu-id="d3567-103">Gets a pointer to an exported type, given its name and enclosing type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d3567-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d3567-104">Syntax</span></span>  
  
```cpp  
HRESULT FindExportedTypeByName (  
    [in]  LPCWSTR           szName,
    [in]  mdToken           mdtExportedType,
    [out] mdExportedType    *ptkExportedType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d3567-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="d3567-105">Parameters</span></span>  
 `szName`  
 <span data-ttu-id="d3567-106">in Nome del tipo esportato.</span><span class="sxs-lookup"><span data-stu-id="d3567-106">[in] The name of the exported type.</span></span>  
  
 `mdtExportedType`  
 <span data-ttu-id="d3567-107">in Token di metadati per la classe contenitore del tipo esportato.</span><span class="sxs-lookup"><span data-stu-id="d3567-107">[in] The metadata token for the enclosing class of the exported type.</span></span> <span data-ttu-id="d3567-108">Questo valore è `mdExportedTypeNil` se il tipo esportato richiesto non è un tipo annidato.</span><span class="sxs-lookup"><span data-stu-id="d3567-108">This value is `mdExportedTypeNil` if the requested exported type is not a nested type.</span></span>  
  
 `ptkExportedType`  
 <span data-ttu-id="d3567-109">out Puntatore al `mdExportedType` token che rappresenta il tipo esportato.</span><span class="sxs-lookup"><span data-stu-id="d3567-109">[out] A pointer to the `mdExportedType` token that represents the exported type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d3567-110">Commenti</span><span class="sxs-lookup"><span data-stu-id="d3567-110">Remarks</span></span>  
 <span data-ttu-id="d3567-111">Il `FindExportedTypeByName` metodo utilizza le regole standard utilizzate dal Common Language Runtime per la risoluzione dei riferimenti.</span><span class="sxs-lookup"><span data-stu-id="d3567-111">The `FindExportedTypeByName` method uses the standard rules employed by the common language runtime for resolving references.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d3567-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="d3567-112">Requirements</span></span>  
 <span data-ttu-id="d3567-113">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d3567-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d3567-114">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="d3567-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="d3567-115">**Libreria:** Usato come risorsa in MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="d3567-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="d3567-116">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d3567-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d3567-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d3567-117">See also</span></span>

- [<span data-ttu-id="d3567-118">Interfaccia IMetaDataAssemblyImport</span><span class="sxs-lookup"><span data-stu-id="d3567-118">IMetaDataAssemblyImport Interface</span></span>](imetadataassemblyimport-interface.md)
- [<span data-ttu-id="d3567-119">Modalità di individuazione degli assembly da parte del runtime</span><span class="sxs-lookup"><span data-stu-id="d3567-119">How the Runtime Locates Assemblies</span></span>](../../deployment/how-the-runtime-locates-assemblies.md)
