---
title: Metodo IMetaDataAssemblyEmit::DefineFile
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyEmit.DefineFile
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyEmit::DefineFile
helpviewer_keywords:
- IMetaDataAssemblyEmit::DefineFile method [.NET Framework metadata]
- DefineFile method [.NET Framework metadata]
ms.assetid: c065aadf-c1ca-4981-bde6-597042cb29c4
topic_type:
- apiref
ms.openlocfilehash: 0b7ca6f9878ed2fa2d90ea93e5101f0a66ec2d5e
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74440213"
---
# <a name="imetadataassemblyemitdefinefile-method"></a><span data-ttu-id="c2bb6-102">Metodo IMetaDataAssemblyEmit::DefineFile</span><span class="sxs-lookup"><span data-stu-id="c2bb6-102">IMetaDataAssemblyEmit::DefineFile Method</span></span>
<span data-ttu-id="c2bb6-103">Crea una struttura dei metadati `File` che contiene i metadati per l'assembly a cui fa riferimento questo assembly e restituisce il token di metadati associato.</span><span class="sxs-lookup"><span data-stu-id="c2bb6-103">Creates a `File` metadata structure containing metadata for assembly referenced by this assembly, and returns the associated metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c2bb6-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c2bb6-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineFile (  
    [in]  LPCWSTR        szName,   
    [in]  const void     *pbHashValue,   
    [in]  ULONG          cbHashValue,  
    [in]  DWORD          dwFileFlags,  
    [out] mdFile         *pmdf  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c2bb6-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="c2bb6-105">Parameters</span></span>  
 `szName`  
 <span data-ttu-id="c2bb6-106">in Nome del file da utilizzare.</span><span class="sxs-lookup"><span data-stu-id="c2bb6-106">[in] The name of the file to be consumed.</span></span>  
  
 `pbHashValue`  
 <span data-ttu-id="c2bb6-107">in Puntatore ai dati hash associati all'assembly.</span><span class="sxs-lookup"><span data-stu-id="c2bb6-107">[in] A pointer to the hash data associated with the assembly.</span></span>  
  
 `cbHashValue`  
 <span data-ttu-id="c2bb6-108">in Dimensioni in byte del `pbHashValue`.</span><span class="sxs-lookup"><span data-stu-id="c2bb6-108">[in] The size in bytes of `pbHashValue`.</span></span>  
  
 `dwFileFlags`  
 <span data-ttu-id="c2bb6-109">in Combinazione bit per bit di valori di `FileFlags` che specificano le impostazioni delle proprietà.</span><span class="sxs-lookup"><span data-stu-id="c2bb6-109">[in] A bitwise combination of `FileFlags` values that specify property settings.</span></span>  
  
 `pmdf`  
 <span data-ttu-id="c2bb6-110">out Puntatore al token di `File` restituito.</span><span class="sxs-lookup"><span data-stu-id="c2bb6-110">[out] A pointer to the returned `File` token.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c2bb6-111">Note</span><span class="sxs-lookup"><span data-stu-id="c2bb6-111">Remarks</span></span>  
 <span data-ttu-id="c2bb6-112">È necessario definire una `File` struttura dei metadati per ogni file che faceva parte di questo assembly nel momento in cui è stato compilato l'assembly, escluso il file contenente i metadati.</span><span class="sxs-lookup"><span data-stu-id="c2bb6-112">One `File` metadata structure must be defined for each file that was part of this assembly at the time that this assembly was built, excluding the file that contains the metadata.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c2bb6-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="c2bb6-113">Requirements</span></span>  
 <span data-ttu-id="c2bb6-114">**Piattaforma:** Vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c2bb6-114">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c2bb6-115">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="c2bb6-115">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="c2bb6-116">**Libreria:** Usato come risorsa in MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="c2bb6-116">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="c2bb6-117">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c2bb6-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c2bb6-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c2bb6-118">See also</span></span>

- [<span data-ttu-id="c2bb6-119">Interfaccia IMetaDataAssemblyEmit</span><span class="sxs-lookup"><span data-stu-id="c2bb6-119">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
