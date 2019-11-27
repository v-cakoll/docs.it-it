---
title: Metodo IMetaDataDispenser::DefineScope
ms.date: 03/30/2017
api_name:
- IMetaDataDispenser.DefineScope
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataDispenser::DefineScope
helpviewer_keywords:
- DefineScope method [.NET Framework metadata]
- IMetaDataDispenser::DefineScope method [.NET Framework metadata]
ms.assetid: af28db02-29af-45ac-aec6-8d6c6123c2ff
topic_type:
- apiref
ms.openlocfilehash: 381c38542dcde242c0a1a4e71e9b99316328159d
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74436242"
---
# <a name="imetadatadispenserdefinescope-method"></a><span data-ttu-id="05ad9-102">Metodo IMetaDataDispenser::DefineScope</span><span class="sxs-lookup"><span data-stu-id="05ad9-102">IMetaDataDispenser::DefineScope Method</span></span>
<span data-ttu-id="05ad9-103">Crea una nuova area in memoria in cui è possibile creare nuovi metadati.</span><span class="sxs-lookup"><span data-stu-id="05ad9-103">Creates a new area in memory in which you can create new metadata.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="05ad9-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="05ad9-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineScope (  
    [in]  REFCLSID    rclsid,  
    [in]  DWORD       dwCreateFlags,  
    [in]  REFIID      riid,   
    [out] IUnknown    **ppIUnk  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="05ad9-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="05ad9-105">Parameters</span></span>  
 `rclsid`  
 <span data-ttu-id="05ad9-106">in CLSID della versione delle strutture di metadati da creare.</span><span class="sxs-lookup"><span data-stu-id="05ad9-106">[in] The CLSID of the version of metadata structures to be created.</span></span> <span data-ttu-id="05ad9-107">Questo valore deve essere CLSID_CorMetaDataRuntime per la versione .NET Framework 2,0.</span><span class="sxs-lookup"><span data-stu-id="05ad9-107">This value must be CLSID_CorMetaDataRuntime for the .NET Framework version 2.0.</span></span>  
  
 `dwCreateFlags`  
 <span data-ttu-id="05ad9-108">in Flag che specificano le opzioni.</span><span class="sxs-lookup"><span data-stu-id="05ad9-108">[in] Flags that specify options.</span></span> <span data-ttu-id="05ad9-109">Questo valore deve essere zero per il .NET Framework 2,0.</span><span class="sxs-lookup"><span data-stu-id="05ad9-109">This value must be zero for the .NET Framework 2.0.</span></span>  
  
 `riid`  
 <span data-ttu-id="05ad9-110">in IID dell'interfaccia di metadati desiderata da restituire. il chiamante utilizzerà l'interfaccia per creare i nuovi metadati.</span><span class="sxs-lookup"><span data-stu-id="05ad9-110">[in] The IID of the desired metadata interface to be returned; the caller will use the interface to create the new metadata.</span></span>  
  
 <span data-ttu-id="05ad9-111">Il valore di `riid` deve specificare una delle interfacce "Emit".</span><span class="sxs-lookup"><span data-stu-id="05ad9-111">The value of `riid` must specify one of the "emit" interfaces.</span></span> <span data-ttu-id="05ad9-112">I valori validi sono IID_IMetaDataEmit, IID_IMetaDataAssemblyEmit o IID_IMetaDataEmit2.</span><span class="sxs-lookup"><span data-stu-id="05ad9-112">Valid values are IID_IMetaDataEmit, IID_IMetaDataAssemblyEmit, or IID_IMetaDataEmit2.</span></span>  
  
 `ppIUnk`  
 <span data-ttu-id="05ad9-113">out Puntatore all'interfaccia restituita.</span><span class="sxs-lookup"><span data-stu-id="05ad9-113">[out] The pointer to the returned interface.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="05ad9-114">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="05ad9-114">Remarks</span></span>  
 <span data-ttu-id="05ad9-115">`DefineScope` crea un set di tabelle di metadati in memoria, genera un GUID univoco (identificatore della versione del modulo o MVID) per i metadati e crea una voce nella tabella dei moduli per l'unità di compilazione da emettere.</span><span class="sxs-lookup"><span data-stu-id="05ad9-115">`DefineScope` creates a set of in-memory metadata tables, generates a unique GUID (module version identifier, or MVID) for the metadata, and creates an entry in the module table for the compilation unit being emitted.</span></span>  
  
 <span data-ttu-id="05ad9-116">È possibile alleghi gli attributi all'ambito dei metadati nel suo complesso usando il metodo [IMetaDataEmit:: SetModuleProps](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setmoduleprops-method.md) o [IMetaDataEmit::D efinecustomattribute](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definecustomattribute-method.md) , a seconda dei casi.</span><span class="sxs-lookup"><span data-stu-id="05ad9-116">You can attach attributes to the metadata scope as a whole by using the [IMetaDataEmit::SetModuleProps](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setmoduleprops-method.md) or [IMetaDataEmit::DefineCustomAttribute](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definecustomattribute-method.md) method, as appropriate.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="05ad9-117">Requisiti</span><span class="sxs-lookup"><span data-stu-id="05ad9-117">Requirements</span></span>  
 <span data-ttu-id="05ad9-118">**Piattaforma:** Vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="05ad9-118">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="05ad9-119">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="05ad9-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="05ad9-120">**Libreria:** Usato come risorsa in MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="05ad9-120">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="05ad9-121">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="05ad9-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="05ad9-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="05ad9-122">See also</span></span>

- [<span data-ttu-id="05ad9-123">Interfaccia IMetaDataDispenser</span><span class="sxs-lookup"><span data-stu-id="05ad9-123">IMetaDataDispenser Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md)
- [<span data-ttu-id="05ad9-124">Interfaccia IMetaDataDispenserEx</span><span class="sxs-lookup"><span data-stu-id="05ad9-124">IMetaDataDispenserEx Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md)
- [<span data-ttu-id="05ad9-125">Interfaccia IMetaDataAssemblyEmit</span><span class="sxs-lookup"><span data-stu-id="05ad9-125">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
- [<span data-ttu-id="05ad9-126">Interfaccia IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="05ad9-126">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="05ad9-127">Interfaccia IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="05ad9-127">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
