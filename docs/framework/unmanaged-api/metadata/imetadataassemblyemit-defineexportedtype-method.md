---
title: Metodo IMetaDataAssemblyEmit::DefineExportedType
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyEmit.DefineExportedType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyEmit::DefineExportedType
helpviewer_keywords:
- IMetaDataAssemblyEmit::DefineExportedType method [.NET Framework metadata]
- DefineExportedType method [.NET Framework metadata]
ms.assetid: fad01d7a-3178-4c8c-9f0a-4641e3701c9b
topic_type:
- apiref
ms.openlocfilehash: 81d6c972b53221ee53cbcf31639d65c30858b48b
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008157"
---
# <a name="imetadataassemblyemitdefineexportedtype-method"></a><span data-ttu-id="17b62-102">Metodo IMetaDataAssemblyEmit::DefineExportedType</span><span class="sxs-lookup"><span data-stu-id="17b62-102">IMetaDataAssemblyEmit::DefineExportedType Method</span></span>
<span data-ttu-id="17b62-103">Crea una struttura `ExportedType` che contiene i metadati per il tipo esportato specificato e restituisce il token di metadati associato.</span><span class="sxs-lookup"><span data-stu-id="17b62-103">Creates an `ExportedType` structure containing metadata for the specified exported type, and returns the associated metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="17b62-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="17b62-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineExportedType (  
    [in]  LPCWSTR             szName,  
    [in]  mdToken             tkImplementation,
    [in]  mdTypeDef           tkTypeDef,  
    [in]  DWORD               dwExportedTypeFlags,  
    [out] mdExportedType      *pmdct  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="17b62-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="17b62-105">Parameters</span></span>  
 `szName`  
 <span data-ttu-id="17b62-106">in Nome del tipo da esportare.</span><span class="sxs-lookup"><span data-stu-id="17b62-106">[in] The name of type to be exported.</span></span> <span data-ttu-id="17b62-107">Per la versione 1,1 della Common Language Runtime, il nome del tipo esportato deve corrispondere esattamente al nome specificato in `TypeDef` per il tipo.</span><span class="sxs-lookup"><span data-stu-id="17b62-107">For version 1.1 of the common language runtime, the name of the exported type must exactly match the name given in the `TypeDef` for the type.</span></span>  
  
 `tkImplementation`  
 <span data-ttu-id="17b62-108">in Token che specifica la posizione in cui viene implementato il tipo esportato.</span><span class="sxs-lookup"><span data-stu-id="17b62-108">[in] A token specifying where the exported type is implemented.</span></span> <span data-ttu-id="17b62-109">I valori validi e i significati associati sono:</span><span class="sxs-lookup"><span data-stu-id="17b62-109">The valid values and their associated meanings are:</span></span>  
  
- <span data-ttu-id="17b62-110">`mdFile`Il tipo viene implementato in un file diverso all'interno dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="17b62-110">`mdFile` The type is implemented in a different file within this assembly.</span></span>  
  
- <span data-ttu-id="17b62-111">`mdAssemblyRef`Il tipo viene implementato in un assembly diverso.</span><span class="sxs-lookup"><span data-stu-id="17b62-111">`mdAssemblyRef` The type is implemented in a different assembly.</span></span>  
  
- <span data-ttu-id="17b62-112">`mdExportedTYpe`Il tipo è annidato all'interno di un altro tipo.</span><span class="sxs-lookup"><span data-stu-id="17b62-112">`mdExportedTYpe` The type is nested within some other type.</span></span>  
  
- <span data-ttu-id="17b62-113">`mdFileNil`Il tipo si trova nello stesso file del manifesto e non è un tipo annidato.</span><span class="sxs-lookup"><span data-stu-id="17b62-113">`mdFileNil` The type is in the same file as the manifest and is not a nested type.</span></span>  
  
 `tkTypeDef`  
 <span data-ttu-id="17b62-114">in Token per i metadati che specifica il tipo da esportare.</span><span class="sxs-lookup"><span data-stu-id="17b62-114">[in] A token to the metadata that specifies the type to be exported.</span></span> <span data-ttu-id="17b62-115">Questo valore viene immesso nella `TypeDef` tabella del file che implementa il tipo ed è pertinente solo se tale file si trova in questo assembly.</span><span class="sxs-lookup"><span data-stu-id="17b62-115">This value is entered in the `TypeDef` table in the file that implements the type and is relevant only if that file is in this assembly.</span></span>  
  
 `dwExportedTypeFlags`  
 <span data-ttu-id="17b62-116">in Combinazione bit per bit di valori di enumerazione [CorTypeAttr](cortypeattr-enumeration.md) che definiscono le impostazioni delle proprietà per il tipo esportato.</span><span class="sxs-lookup"><span data-stu-id="17b62-116">[in] A bitwise combination of [CorTypeAttr](cortypeattr-enumeration.md) enumeration values that define the property settings for the exported type.</span></span>  
  
 `pmdct`  
 <span data-ttu-id="17b62-117">out Puntatore al token di metadati restituito che indica il tipo esportato.</span><span class="sxs-lookup"><span data-stu-id="17b62-117">[out] A pointer to the returned metadata token that indicates the exported type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="17b62-118">Commenti</span><span class="sxs-lookup"><span data-stu-id="17b62-118">Remarks</span></span>  
 <span data-ttu-id="17b62-119">È `ExportedType` necessario definire una struttura di metadati per ogni tipo esposto dall'assembly e che viene implementato in un modulo diverso da quello che contiene il manifesto.</span><span class="sxs-lookup"><span data-stu-id="17b62-119">An `ExportedType` metadata structure must be defined for each type that is exposed by this assembly and that is implemented in a module other than the one containing the manifest.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="17b62-120">Requisiti</span><span class="sxs-lookup"><span data-stu-id="17b62-120">Requirements</span></span>  
 <span data-ttu-id="17b62-121">**Piattaforma:** Vedere [requisiti di sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="17b62-121">**Platform:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="17b62-122">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="17b62-122">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="17b62-123">**Libreria:** Usato come risorsa in MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="17b62-123">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="17b62-124">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="17b62-124">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="17b62-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="17b62-125">See also</span></span>

- [<span data-ttu-id="17b62-126">Interfaccia IMetaDataAssemblyEmit</span><span class="sxs-lookup"><span data-stu-id="17b62-126">IMetaDataAssemblyEmit Interface</span></span>](imetadataassemblyemit-interface.md)
