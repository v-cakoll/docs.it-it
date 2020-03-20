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
ms.openlocfilehash: dd1d6f1da6e49837eebd9356500f403c199b011b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177858"
---
# <a name="imetadataassemblyemitsetexportedtypeprops-method"></a><span data-ttu-id="3070e-102">Metodo IMetaDataAssemblyEmit::SetExportedTypeProps</span><span class="sxs-lookup"><span data-stu-id="3070e-102">IMetaDataAssemblyEmit::SetExportedTypeProps Method</span></span>
<span data-ttu-id="3070e-103">Modifica la struttura dei metadati `ExportedType` specificata.</span><span class="sxs-lookup"><span data-stu-id="3070e-103">Modifies the specified `ExportedType` metadata structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3070e-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3070e-104">Syntax</span></span>  
  
```cpp  
HRESULT SetExportedTypeProps (  
    [in] mdExportedType   ct,
    [in] mdToken          tkImplementation,  
    [in] mdTypeDef        tkTypeDef,  
    [in] DWORD            dwExportedTypeFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3070e-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="3070e-105">Parameters</span></span>  
 `ct`  
 <span data-ttu-id="3070e-106">[in] Token di metadati `ExportedType` che specifica la struttura dei metadati da modificare.</span><span class="sxs-lookup"><span data-stu-id="3070e-106">[in] The metadata token that specifies the `ExportedType` metadata structure to be modified.</span></span>  
  
 `tkImplementation`  
 <span data-ttu-id="3070e-107">[in] Token, di `File`tipo `AssemblyRef`, `ExportedType`, o , che specifica la modalità di implementazione di questo tipo.</span><span class="sxs-lookup"><span data-stu-id="3070e-107">[in] The token, of type `File`, `AssemblyRef`, or `ExportedType`, that specifies how this type is implemented.</span></span>  
  
 `tkTypeDef`  
 <span data-ttu-id="3070e-108">[in] Token `TypeDef` a cui viene fatto riferimento nel file di codice.</span><span class="sxs-lookup"><span data-stu-id="3070e-108">[in] The `TypeDef` token referenced in the code file.</span></span>  
  
 `dwExportedTypeFlags`  
 <span data-ttu-id="3070e-109">[in] Combinazione bit per bit di valori che specificano attributi del tipo.</span><span class="sxs-lookup"><span data-stu-id="3070e-109">[in] A bitwise combination of values that specify attributes of the type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3070e-110">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="3070e-110">Remarks</span></span>  
 <span data-ttu-id="3070e-111">Per creare `ExportedType` una struttura dei metadati, utilizzare il metodo [IMetaDataAssemblyEmit::DefineExportedType](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineexportedtype-method.md) .</span><span class="sxs-lookup"><span data-stu-id="3070e-111">To create an `ExportedType` metadata structure, use the [IMetaDataAssemblyEmit::DefineExportedType](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineexportedtype-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3070e-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="3070e-112">Requirements</span></span>  
 <span data-ttu-id="3070e-113">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3070e-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3070e-114">**Intestazione:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="3070e-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="3070e-115">**Biblioteca:** Utilizzato come risorsa in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="3070e-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="3070e-116">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3070e-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3070e-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3070e-117">See also</span></span>

- [<span data-ttu-id="3070e-118">Interfaccia IMetaDataAssemblyEmit</span><span class="sxs-lookup"><span data-stu-id="3070e-118">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
