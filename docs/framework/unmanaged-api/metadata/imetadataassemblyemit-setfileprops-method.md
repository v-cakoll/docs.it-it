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
ms.openlocfilehash: 25baa6ffda3d50915cc7898275d6a557c1b3e947
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176032"
---
# <a name="imetadataassemblyemitsetfileprops-method"></a><span data-ttu-id="8baa4-102">Metodo IMetaDataAssemblyEmit::SetFileProps</span><span class="sxs-lookup"><span data-stu-id="8baa4-102">IMetaDataAssemblyEmit::SetFileProps Method</span></span>
<span data-ttu-id="8baa4-103">Modifica la struttura dei metadati `File` specificata.</span><span class="sxs-lookup"><span data-stu-id="8baa4-103">Modifies the specified `File` metadata structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8baa4-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8baa4-104">Syntax</span></span>  
  
```cpp  
HRESULT SetFileProps (  
    [in] mdFile        file,  
    [in] const void    *pbHashValue,
    [in] ULONG         cbHashValue,  
    [in] DWORD         dwFileFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8baa4-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="8baa4-105">Parameters</span></span>  
 `file`  
 <span data-ttu-id="8baa4-106">[in] Token di metadati `File` che specifica la struttura dei metadati da modificare.</span><span class="sxs-lookup"><span data-stu-id="8baa4-106">[in] The metadata token that specifies the `File` metadata structure to be modified.</span></span>  
  
 `pbHashValue`  
 <span data-ttu-id="8baa4-107">[in] Puntatore ai dati hash associati al file.</span><span class="sxs-lookup"><span data-stu-id="8baa4-107">[in] A pointer to the hash data associated with the file.</span></span>  
  
 `cbHashValue`  
 <span data-ttu-id="8baa4-108">[in] Dimensione in byte `pbHashValue`di .</span><span class="sxs-lookup"><span data-stu-id="8baa4-108">[in] The size in bytes of `pbHashValue`.</span></span>  
  
 `dwFileFlags`  
 <span data-ttu-id="8baa4-109">[in] Combinazione bit per bit di [valori CorFileFlags](../../../../docs/framework/unmanaged-api/metadata/corfileflags-enumeration.md) che specificano vari attributi del file.</span><span class="sxs-lookup"><span data-stu-id="8baa4-109">[in] A bitwise combination of [CorFileFlags](../../../../docs/framework/unmanaged-api/metadata/corfileflags-enumeration.md) values that specify various attributes of the file.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8baa4-110">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="8baa4-110">Remarks</span></span>  
 <span data-ttu-id="8baa4-111">Per creare `File` una struttura dei metadati, utilizzare il [metodo IMetaDataAssemblyEmit::DefineFile.](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definefile-method.md)</span><span class="sxs-lookup"><span data-stu-id="8baa4-111">To create a `File` metadata structure, use the [IMetaDataAssemblyEmit::DefineFile](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definefile-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8baa4-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="8baa4-112">Requirements</span></span>  
 <span data-ttu-id="8baa4-113">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8baa4-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8baa4-114">**Intestazione:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="8baa4-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="8baa4-115">**Biblioteca:** Utilizzato come risorsa in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="8baa4-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="8baa4-116">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8baa4-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8baa4-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8baa4-117">See also</span></span>

- [<span data-ttu-id="8baa4-118">Interfaccia IMetaDataAssemblyEmit</span><span class="sxs-lookup"><span data-stu-id="8baa4-118">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
