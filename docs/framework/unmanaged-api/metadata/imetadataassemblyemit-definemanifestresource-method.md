---
title: Metodo IMetaDataAssemblyEmit::DefineManifestResource
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyEmit.DefineManifestResource
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyEmit::DefineManifestResource
helpviewer_keywords:
- DefineManifestResource method [.NET Framework metadata]
- IMetaDataAssemblyEmit::DefineManifestResource method [.NET Framework metadata]
ms.assetid: 27f6d295-0fe9-4cda-b77e-6e7d5c53df09
topic_type:
- apiref
ms.openlocfilehash: 026f5efe195cdb34999b65c5f47de6f68d30e11a
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008131"
---
# <a name="imetadataassemblyemitdefinemanifestresource-method"></a><span data-ttu-id="cacd4-102">Metodo IMetaDataAssemblyEmit::DefineManifestResource</span><span class="sxs-lookup"><span data-stu-id="cacd4-102">IMetaDataAssemblyEmit::DefineManifestResource Method</span></span>
<span data-ttu-id="cacd4-103">Crea una struttura `ManifestResource` che contiene i metadati per la risorsa di manifesto specificata e restituisce il token di metadati associato.</span><span class="sxs-lookup"><span data-stu-id="cacd4-103">Creates a `ManifestResource` structure containing metadata for the specified manifest resource, and returns the associated metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cacd4-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="cacd4-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineManifestResource (  
    [in] LPCWSTR                szName,
    [in] mdToken                tkImplementation,
    [in] DWORD                  dwOffset,
    [in] DWORD                  dwResourceFlags,  
    [out] mdManifestResource    *pmdmr  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cacd4-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="cacd4-105">Parameters</span></span>  
 `szName`  
 <span data-ttu-id="cacd4-106">[in] Nome della risorsa.</span><span class="sxs-lookup"><span data-stu-id="cacd4-106">[in] The name of the resource.</span></span>  
  
 `tkImplementation`  
 <span data-ttu-id="cacd4-107">in Token di metadati di tipo `mdtFile` o `mdtAssemblyRef` che esegue il mapping al provider di risorse.</span><span class="sxs-lookup"><span data-stu-id="cacd4-107">[in] A metadata token of type `mdtFile` or `mdtAssemblyRef` that maps to the resource provider.</span></span> <span data-ttu-id="cacd4-108">Un valore NULL indica che il file in cui sono incorporati i metadati è il provider di risorse.</span><span class="sxs-lookup"><span data-stu-id="cacd4-108">A NULL value indicates that the file in which the metadata is embedded is the resource provider.</span></span>  
  
 `dwOffset`  
 <span data-ttu-id="cacd4-109">in Offset all'inizio della risorsa all'interno del file.</span><span class="sxs-lookup"><span data-stu-id="cacd4-109">[in] The offset to the beginning of the resource within the file.</span></span> <span data-ttu-id="cacd4-110">Per le risorse in file autonomi, questo valore sarà sempre zero.</span><span class="sxs-lookup"><span data-stu-id="cacd4-110">For resources in standalone files, this will always be zero.</span></span> <span data-ttu-id="cacd4-111">Se la risorsa è incorporata in un file PE (Portable Executable), si tratta di un offset del BLOB di risorse, che inizia in corrispondenza della posizione specificata nel file di intestazione cor. h.</span><span class="sxs-lookup"><span data-stu-id="cacd4-111">If the resource is embedded in a PE (portable executable) file, this is an offset of the resource BLOB, which starts at the location specified in the cor.h header file.</span></span>  
  
 `dwResourceFlags`  
 <span data-ttu-id="cacd4-112">in Combinazione bit per bit di valori di flag che specificano le impostazioni delle proprietà per la definizione di risorsa.</span><span class="sxs-lookup"><span data-stu-id="cacd4-112">[in] A bitwise combination of flag values that specify property settings for the resource definition.</span></span>  
  
 `pmdmr`  
 <span data-ttu-id="cacd4-113">out Puntatore al token di metadati restituito.</span><span class="sxs-lookup"><span data-stu-id="cacd4-113">[out] A pointer to the returned metadata token.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cacd4-114">Commenti</span><span class="sxs-lookup"><span data-stu-id="cacd4-114">Remarks</span></span>  
 <span data-ttu-id="cacd4-115">`ManifestResource`È necessario definire una struttura di metadati per ogni risorsa implementata in ognuno dei file dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="cacd4-115">One `ManifestResource` metadata structure must be defined for each resource that is implemented in each of the assembly's files.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cacd4-116">Requisiti</span><span class="sxs-lookup"><span data-stu-id="cacd4-116">Requirements</span></span>  
 <span data-ttu-id="cacd4-117">**Piattaforma:** Vedere [requisiti di sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cacd4-117">**Platform:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cacd4-118">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="cacd4-118">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="cacd4-119">**Libreria:** Usato come risorsa in MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="cacd4-119">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="cacd4-120">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cacd4-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cacd4-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cacd4-121">See also</span></span>

- [<span data-ttu-id="cacd4-122">Interfaccia IMetaDataAssemblyEmit</span><span class="sxs-lookup"><span data-stu-id="cacd4-122">IMetaDataAssemblyEmit Interface</span></span>](imetadataassemblyemit-interface.md)
