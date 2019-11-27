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
ms.openlocfilehash: 106ffeee521f69a73628b1fb6a611abc733583f9
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74431881"
---
# <a name="imetadataassemblyemitsetfileprops-method"></a><span data-ttu-id="2514d-102">Metodo IMetaDataAssemblyEmit::SetFileProps</span><span class="sxs-lookup"><span data-stu-id="2514d-102">IMetaDataAssemblyEmit::SetFileProps Method</span></span>
<span data-ttu-id="2514d-103">Modifica la struttura dei metadati `File` specificata.</span><span class="sxs-lookup"><span data-stu-id="2514d-103">Modifies the specified `File` metadata structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2514d-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2514d-104">Syntax</span></span>  
  
```cpp  
HRESULT SetFileProps (  
    [in] mdFile        file,  
    [in] const void    *pbHashValue,   
    [in] ULONG         cbHashValue,  
    [in] DWORD         dwFileFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2514d-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="2514d-105">Parameters</span></span>  
 `file`  
 <span data-ttu-id="2514d-106">in Token di metadati che specifica la struttura dei metadati `File` da modificare.</span><span class="sxs-lookup"><span data-stu-id="2514d-106">[in] The metadata token that specifies the `File` metadata structure to be modified.</span></span>  
  
 `pbHashValue`  
 <span data-ttu-id="2514d-107">in Puntatore ai dati hash associati al file.</span><span class="sxs-lookup"><span data-stu-id="2514d-107">[in] A pointer to the hash data associated with the file.</span></span>  
  
 `cbHashValue`  
 <span data-ttu-id="2514d-108">in Dimensioni in byte del `pbHashValue`.</span><span class="sxs-lookup"><span data-stu-id="2514d-108">[in] The size in bytes of `pbHashValue`.</span></span>  
  
 `dwFileFlags`  
 <span data-ttu-id="2514d-109">in Combinazione bit per bit di valori [CorFileFlags](../../../../docs/framework/unmanaged-api/metadata/corfileflags-enumeration.md) che specificano diversi attributi del file.</span><span class="sxs-lookup"><span data-stu-id="2514d-109">[in] A bitwise combination of [CorFileFlags](../../../../docs/framework/unmanaged-api/metadata/corfileflags-enumeration.md) values that specify various attributes of the file.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2514d-110">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="2514d-110">Remarks</span></span>  
 <span data-ttu-id="2514d-111">Per creare una struttura di metadati `File`, usare il metodo [IMetaDataAssemblyEmit::D efinefile](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definefile-method.md) .</span><span class="sxs-lookup"><span data-stu-id="2514d-111">To create a `File` metadata structure, use the [IMetaDataAssemblyEmit::DefineFile](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definefile-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2514d-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="2514d-112">Requirements</span></span>  
 <span data-ttu-id="2514d-113">**Piattaforme:** vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2514d-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2514d-114">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="2514d-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="2514d-115">**Libreria:** Usato come risorsa in MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="2514d-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="2514d-116">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2514d-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2514d-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2514d-117">See also</span></span>

- [<span data-ttu-id="2514d-118">Interfaccia IMetaDataAssemblyEmit</span><span class="sxs-lookup"><span data-stu-id="2514d-118">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
