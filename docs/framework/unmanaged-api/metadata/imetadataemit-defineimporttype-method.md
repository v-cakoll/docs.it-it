---
title: Metodo IMetaDataEmit::DefineImportType
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineImportType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineImportType
helpviewer_keywords:
- DefineImportType method [.NET Framework metadata]
- IMetaDataEmit::DefineImportType method [.NET Framework metadata]
ms.assetid: 37fd27af-8062-4904-ace4-51bb78ec600a
topic_type:
- apiref
ms.openlocfilehash: 5b4b0682b2bddff96cb3d720900ed3aa39f06f9d
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74431842"
---
# <a name="imetadataemitdefineimporttype-method"></a><span data-ttu-id="d7f18-102">Metodo IMetaDataEmit::DefineImportType</span><span class="sxs-lookup"><span data-stu-id="d7f18-102">IMetaDataEmit::DefineImportType Method</span></span>
<span data-ttu-id="d7f18-103">Crea un riferimento al tipo specificato definito al di fuori dell'ambito corrente e definisce un token per il riferimento.</span><span class="sxs-lookup"><span data-stu-id="d7f18-103">Creates a reference to the specified type that is defined outside the current scope, and defines a token for that reference.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d7f18-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d7f18-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineImportType (   
    [in]  IMetaDataAssemblyImport  *pAssemImport,   
    [in]  const void               *pbHashValue,   
    [in]  ULONG                    cbHashValue,    
    [in]  IMetaDataImport          *pImport,   
    [in]  mdTypeDef                tdImport,   
    [in]  IMetaDataAssemblyEmit    *pAssemEmit,   
    [out] mdTypeRef                *ptr  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d7f18-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="d7f18-105">Parameters</span></span>  
 `pAssemImport`  
 <span data-ttu-id="d7f18-106">in Interfaccia [IMetaDataAssemblyImport](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md) che rappresenta l'assembly da cui viene importato il tipo di destinazione.</span><span class="sxs-lookup"><span data-stu-id="d7f18-106">[in] An [IMetaDataAssemblyImport](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md) interface that represents the assembly from which the target type is imported.</span></span>  
  
 `pbHashValue`  
 <span data-ttu-id="d7f18-107">in Matrice contenente l'hash per l'assembly specificato da `pAssemImport`.</span><span class="sxs-lookup"><span data-stu-id="d7f18-107">[in] An array that contains the hash for the assembly specified by `pAssemImport`.</span></span>  
  
 `cbHashValue`  
 <span data-ttu-id="d7f18-108">[in] Numero di byte nella matrice di `pbHashValue`.</span><span class="sxs-lookup"><span data-stu-id="d7f18-108">[in] The number of bytes in the `pbHashValue` array.</span></span>  
  
 `pImport`  
 <span data-ttu-id="d7f18-109">in Interfaccia [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) che rappresenta l'ambito dei metadati da cui viene importato il tipo di destinazione.</span><span class="sxs-lookup"><span data-stu-id="d7f18-109">[in] An [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) interface that represents the metadata scope from which the target type is imported.</span></span>  
  
 `tdImport`  
 <span data-ttu-id="d7f18-110">in Token `mdTypeDef` che specifica il tipo di destinazione.</span><span class="sxs-lookup"><span data-stu-id="d7f18-110">[in] An `mdTypeDef` token that specifies the target type.</span></span>  
  
 `pAssemEmit`  
 <span data-ttu-id="d7f18-111">in Interfaccia [IMetaDataAssemblyEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md) che rappresenta l'assembly in cui viene importato il tipo di destinazione.</span><span class="sxs-lookup"><span data-stu-id="d7f18-111">[in] An [IMetaDataAssemblyEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md) interface that represents the assembly into which the target type is imported.</span></span>  
  
 `ptr`  
 <span data-ttu-id="d7f18-112">out Token `mdTypeRef` definito nell'ambito corrente per il riferimento al tipo.</span><span class="sxs-lookup"><span data-stu-id="d7f18-112">[out] The `mdTypeRef` token that is defined in the current scope for the type reference.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d7f18-113">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="d7f18-113">Remarks</span></span>  
 <span data-ttu-id="d7f18-114">Prima di chiamare il metodo [IMetaDataEmit::D efineimportmember](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineimportmember-method.md) , è possibile usare il metodo `DefineImportType` per creare un riferimento al tipo, nell'ambito corrente, per la classe padre o l'interfaccia padre del membro.</span><span class="sxs-lookup"><span data-stu-id="d7f18-114">Prior to calling the [IMetaDataEmit::DefineImportMember](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineimportmember-method.md) method, you can use the `DefineImportType` method to create a type reference, in the current scope, for the member's parent class or parent interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d7f18-115">Requisiti</span><span class="sxs-lookup"><span data-stu-id="d7f18-115">Requirements</span></span>  
 <span data-ttu-id="d7f18-116">**Piattaforme:** vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d7f18-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d7f18-117">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="d7f18-117">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="d7f18-118">**Libreria:** Usato come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="d7f18-118">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d7f18-119">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d7f18-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d7f18-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d7f18-120">See also</span></span>

- [<span data-ttu-id="d7f18-121">Interfaccia IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="d7f18-121">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="d7f18-122">Interfaccia IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="d7f18-122">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
