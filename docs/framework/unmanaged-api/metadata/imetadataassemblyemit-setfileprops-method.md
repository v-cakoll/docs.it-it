---
title: Metodo IMetaDataAssemblyEmit::SetFileProps
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyEmit.SetFileProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyEmit::SetFileProps
helpviewer_keywords:
- IMetaDataAssemblyEmit::SetFileProps method [.NET Framework metadata]
- SetFileProps method [.NET Framework metadata]
ms.assetid: 85667d38-611c-45a9-938d-930ac7a7b681
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 8017f816632cffc42676761a367e980d1cafe088
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33443616"
---
# <a name="imetadataassemblyemitsetfileprops-method"></a><span data-ttu-id="4730b-102">Metodo IMetaDataAssemblyEmit::SetFileProps</span><span class="sxs-lookup"><span data-stu-id="4730b-102">IMetaDataAssemblyEmit::SetFileProps Method</span></span>
<span data-ttu-id="4730b-103">Modifica la struttura dei metadati `File` specificata.</span><span class="sxs-lookup"><span data-stu-id="4730b-103">Modifies the specified `File` metadata structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4730b-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4730b-104">Syntax</span></span>  
  
```  
HRESULT SetFileProps (  
    [in] mdFile        file,  
    [in] const void    *pbHashValue,   
    [in] ULONG         cbHashValue,  
    [in] DWORD         dwFileFlags  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4730b-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="4730b-105">Parameters</span></span>  
 `file`  
 <span data-ttu-id="4730b-106">[in] Il token di metadati che specifica il `File` struttura dei metadati da modificare.</span><span class="sxs-lookup"><span data-stu-id="4730b-106">[in] The metadata token that specifies the `File` metadata structure to be modified.</span></span>  
  
 `pbHashValue`  
 <span data-ttu-id="4730b-107">[in] Un puntatore per il valore hash dei dati associati al file.</span><span class="sxs-lookup"><span data-stu-id="4730b-107">[in] A pointer to the hash data associated with the file.</span></span>  
  
 `cbHashValue`  
 <span data-ttu-id="4730b-108">[in] Le dimensioni in byte di `pbHashValue`.</span><span class="sxs-lookup"><span data-stu-id="4730b-108">[in] The size in bytes of `pbHashValue`.</span></span>  
  
 `dwFileFlags`  
 <span data-ttu-id="4730b-109">[in] Combinazione bit per bit di [CorFileFlags](../../../../docs/framework/unmanaged-api/metadata/corfileflags-enumeration.md) valori che specificano vari attributi del file.</span><span class="sxs-lookup"><span data-stu-id="4730b-109">[in] A bitwise combination of [CorFileFlags](../../../../docs/framework/unmanaged-api/metadata/corfileflags-enumeration.md) values that specify various attributes of the file.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4730b-110">Note</span><span class="sxs-lookup"><span data-stu-id="4730b-110">Remarks</span></span>  
 <span data-ttu-id="4730b-111">Per creare un `File` struttura dei metadati, usare il [IMetaDataAssemblyEmit:: DefineFile](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definefile-method.md) metodo.</span><span class="sxs-lookup"><span data-stu-id="4730b-111">To create a `File` metadata structure, use the [IMetaDataAssemblyEmit::DefineFile](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definefile-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4730b-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="4730b-112">Requirements</span></span>  
 <span data-ttu-id="4730b-113">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4730b-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4730b-114">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="4730b-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="4730b-115">**Libreria:** usata come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="4730b-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="4730b-116">**Versioni di .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4730b-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4730b-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4730b-117">See Also</span></span>  
 [<span data-ttu-id="4730b-118">Interfaccia IMetaDataAssemblyEmit</span><span class="sxs-lookup"><span data-stu-id="4730b-118">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
