---
title: Metodo IMetaDataAssemblyEmit::SetExportedTypeProps
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyEmit.SetExportedTypeProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyEmit::SetExportedTypeProps
helpviewer_keywords:
- SetExportedTypeProps method [.NET Framework metadata]
- IMetaDataAssemblyEmit::SetExportedTypeProps method [.NET Framework metadata]
ms.assetid: 1c090153-fd5f-46c7-9cff-39a78d992c8f
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 5c09140488730179616d11932faa3542f704958a
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59123747"
---
# <a name="imetadataassemblyemitsetexportedtypeprops-method"></a><span data-ttu-id="baaf1-102">Metodo IMetaDataAssemblyEmit::SetExportedTypeProps</span><span class="sxs-lookup"><span data-stu-id="baaf1-102">IMetaDataAssemblyEmit::SetExportedTypeProps Method</span></span>
<span data-ttu-id="baaf1-103">Modifica la struttura dei metadati `ExportedType` specificata.</span><span class="sxs-lookup"><span data-stu-id="baaf1-103">Modifies the specified `ExportedType` metadata structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="baaf1-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="baaf1-104">Syntax</span></span>  
  
```  
HRESULT SetExportedTypeProps (  
    [in] mdExportedType   ct,   
    [in] mdToken          tkImplementation,  
    [in] mdTypeDef        tkTypeDef,  
    [in] DWORD            dwExportedTypeFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="baaf1-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="baaf1-105">Parameters</span></span>  
 `ct`  
 <span data-ttu-id="baaf1-106">[in] Il token di metadati che specifica il `ExportedType` modifica della struttura dei metadati.</span><span class="sxs-lookup"><span data-stu-id="baaf1-106">[in] The metadata token that specifies the `ExportedType` metadata structure to be modified.</span></span>  
  
 `tkImplementation`  
 <span data-ttu-id="baaf1-107">[in] Il token, di tipo `File`, `AssemblyRef`, o `ExportedType`, che specifica la modalità di implementazione di questo tipo.</span><span class="sxs-lookup"><span data-stu-id="baaf1-107">[in] The token, of type `File`, `AssemblyRef`, or `ExportedType`, that specifies how this type is implemented.</span></span>  
  
 `tkTypeDef`  
 <span data-ttu-id="baaf1-108">[in] Il `TypeDef` token di cui viene fatto riferimento nel file di codice.</span><span class="sxs-lookup"><span data-stu-id="baaf1-108">[in] The `TypeDef` token referenced in the code file.</span></span>  
  
 `dwExportedTypeFlags`  
 <span data-ttu-id="baaf1-109">[in] Combinazione bit per bit dei valori che specificano gli attributi del tipo.</span><span class="sxs-lookup"><span data-stu-id="baaf1-109">[in] A bitwise combination of values that specify attributes of the type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="baaf1-110">Note</span><span class="sxs-lookup"><span data-stu-id="baaf1-110">Remarks</span></span>  
 <span data-ttu-id="baaf1-111">Per creare un `ExportedType` struttura dei metadati, usare il [DefineExportedType](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineexportedtype-method.md) (metodo).</span><span class="sxs-lookup"><span data-stu-id="baaf1-111">To create an `ExportedType` metadata structure, use the [IMetaDataAssemblyEmit::DefineExportedType](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineexportedtype-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="baaf1-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="baaf1-112">Requirements</span></span>  
 <span data-ttu-id="baaf1-113">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="baaf1-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="baaf1-114">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="baaf1-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="baaf1-115">**Libreria:** Usato come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="baaf1-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="baaf1-116">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="baaf1-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="baaf1-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="baaf1-117">See also</span></span>

- [<span data-ttu-id="baaf1-118">Interfaccia IMetaDataAssemblyEmit</span><span class="sxs-lookup"><span data-stu-id="baaf1-118">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
