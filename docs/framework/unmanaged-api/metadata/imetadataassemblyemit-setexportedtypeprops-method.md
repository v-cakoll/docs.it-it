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
ms.openlocfilehash: 8643a4d207fb570195caa00a1ac659c78c2ff2b8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33445066"
---
# <a name="imetadataassemblyemitsetexportedtypeprops-method"></a><span data-ttu-id="75e91-102">Metodo IMetaDataAssemblyEmit::SetExportedTypeProps</span><span class="sxs-lookup"><span data-stu-id="75e91-102">IMetaDataAssemblyEmit::SetExportedTypeProps Method</span></span>
<span data-ttu-id="75e91-103">Modifica la struttura dei metadati `ExportedType` specificata.</span><span class="sxs-lookup"><span data-stu-id="75e91-103">Modifies the specified `ExportedType` metadata structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="75e91-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="75e91-104">Syntax</span></span>  
  
```  
HRESULT SetExportedTypeProps (  
    [in] mdExportedType   ct,   
    [in] mdToken          tkImplementation,  
    [in] mdTypeDef        tkTypeDef,  
    [in] DWORD            dwExportedTypeFlags  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="75e91-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="75e91-105">Parameters</span></span>  
 `ct`  
 <span data-ttu-id="75e91-106">[in] Il token di metadati che specifica il `ExportedType` struttura dei metadati da modificare.</span><span class="sxs-lookup"><span data-stu-id="75e91-106">[in] The metadata token that specifies the `ExportedType` metadata structure to be modified.</span></span>  
  
 `tkImplementation`  
 <span data-ttu-id="75e91-107">[in] Il token, di tipo `File`, `AssemblyRef`, o `ExportedType`, che specifica la modalità di implementazione di questo tipo.</span><span class="sxs-lookup"><span data-stu-id="75e91-107">[in] The token, of type `File`, `AssemblyRef`, or `ExportedType`, that specifies how this type is implemented.</span></span>  
  
 `tkTypeDef`  
 <span data-ttu-id="75e91-108">[in] Il `TypeDef` token a cui fa riferimento nel file di codice.</span><span class="sxs-lookup"><span data-stu-id="75e91-108">[in] The `TypeDef` token referenced in the code file.</span></span>  
  
 `dwExportedTypeFlags`  
 <span data-ttu-id="75e91-109">[in] Combinazione bit per bit dei valori che specificano gli attributi del tipo.</span><span class="sxs-lookup"><span data-stu-id="75e91-109">[in] A bitwise combination of values that specify attributes of the type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="75e91-110">Note</span><span class="sxs-lookup"><span data-stu-id="75e91-110">Remarks</span></span>  
 <span data-ttu-id="75e91-111">Per creare un `ExportedType` struttura dei metadati, usare il [IMetaDataAssemblyEmit:: DefineExportedType](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineexportedtype-method.md) metodo.</span><span class="sxs-lookup"><span data-stu-id="75e91-111">To create an `ExportedType` metadata structure, use the [IMetaDataAssemblyEmit::DefineExportedType](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineexportedtype-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="75e91-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="75e91-112">Requirements</span></span>  
 <span data-ttu-id="75e91-113">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="75e91-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="75e91-114">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="75e91-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="75e91-115">**Libreria:** usata come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="75e91-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="75e91-116">**Versioni di .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="75e91-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="75e91-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="75e91-117">See Also</span></span>  
 [<span data-ttu-id="75e91-118">Interfaccia IMetaDataAssemblyEmit</span><span class="sxs-lookup"><span data-stu-id="75e91-118">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
