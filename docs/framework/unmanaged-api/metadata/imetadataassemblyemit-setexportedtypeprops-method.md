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
ms.openlocfilehash: fa4f1f57cb8fe1ca81bbad6438a88bb43c48e7bf
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008079"
---
# <a name="imetadataassemblyemitsetexportedtypeprops-method"></a><span data-ttu-id="50696-102">Metodo IMetaDataAssemblyEmit::SetExportedTypeProps</span><span class="sxs-lookup"><span data-stu-id="50696-102">IMetaDataAssemblyEmit::SetExportedTypeProps Method</span></span>
<span data-ttu-id="50696-103">Modifica la struttura dei metadati `ExportedType` specificata.</span><span class="sxs-lookup"><span data-stu-id="50696-103">Modifies the specified `ExportedType` metadata structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="50696-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="50696-104">Syntax</span></span>  
  
```cpp  
HRESULT SetExportedTypeProps (  
    [in] mdExportedType   ct,
    [in] mdToken          tkImplementation,  
    [in] mdTypeDef        tkTypeDef,  
    [in] DWORD            dwExportedTypeFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="50696-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="50696-105">Parameters</span></span>  
 `ct`  
 <span data-ttu-id="50696-106">in Token di metadati che specifica la `ExportedType` struttura dei metadati da modificare.</span><span class="sxs-lookup"><span data-stu-id="50696-106">[in] The metadata token that specifies the `ExportedType` metadata structure to be modified.</span></span>  
  
 `tkImplementation`  
 <span data-ttu-id="50696-107">in Token, di tipo `File` , `AssemblyRef` o `ExportedType` , che specifica la modalità di implementazione di questo tipo.</span><span class="sxs-lookup"><span data-stu-id="50696-107">[in] The token, of type `File`, `AssemblyRef`, or `ExportedType`, that specifies how this type is implemented.</span></span>  
  
 `tkTypeDef`  
 <span data-ttu-id="50696-108">in `TypeDef`Token a cui si fa riferimento nel file di codice.</span><span class="sxs-lookup"><span data-stu-id="50696-108">[in] The `TypeDef` token referenced in the code file.</span></span>  
  
 `dwExportedTypeFlags`  
 <span data-ttu-id="50696-109">in Combinazione bit per bit di valori che specificano gli attributi del tipo.</span><span class="sxs-lookup"><span data-stu-id="50696-109">[in] A bitwise combination of values that specify attributes of the type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="50696-110">Commenti</span><span class="sxs-lookup"><span data-stu-id="50696-110">Remarks</span></span>  
 <span data-ttu-id="50696-111">Per creare una `ExportedType` struttura di metadati, usare il metodo [IMetaDataAssemblyEmit::D efineexportedtype](imetadataassemblyemit-defineexportedtype-method.md) .</span><span class="sxs-lookup"><span data-stu-id="50696-111">To create an `ExportedType` metadata structure, use the [IMetaDataAssemblyEmit::DefineExportedType](imetadataassemblyemit-defineexportedtype-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="50696-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="50696-112">Requirements</span></span>  
 <span data-ttu-id="50696-113">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="50696-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="50696-114">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="50696-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="50696-115">**Libreria:** Usato come risorsa in MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="50696-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="50696-116">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="50696-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="50696-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="50696-117">See also</span></span>

- [<span data-ttu-id="50696-118">Interfaccia IMetaDataAssemblyEmit</span><span class="sxs-lookup"><span data-stu-id="50696-118">IMetaDataAssemblyEmit Interface</span></span>](imetadataassemblyemit-interface.md)
