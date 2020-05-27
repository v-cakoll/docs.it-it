---
title: Metodo IMetaDataDispenser::OpenScopeOnMemory
ms.date: 03/30/2017
api_name:
- IMetaDataDispenser.OpenScopeOnMemory
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataDispenser::OpenScopeOnMemory
helpviewer_keywords:
- OpenScopeOnMemory method [.NET Framework metadata]
- IMetaDataDispenser::OpenScopeOnMemory method [.NET Framework metadata]
ms.assetid: 14218249-bdec-48ae-b5fc-9f57f7ca8501
topic_type:
- apiref
ms.openlocfilehash: 69e5e05012d2b44a76a986591ec990f66bf8ae20
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2020
ms.locfileid: "84007325"
---
# <a name="imetadatadispenseropenscopeonmemory-method"></a><span data-ttu-id="2a3b4-102">Metodo IMetaDataDispenser::OpenScopeOnMemory</span><span class="sxs-lookup"><span data-stu-id="2a3b4-102">IMetaDataDispenser::OpenScopeOnMemory Method</span></span>
<span data-ttu-id="2a3b4-103">Apre un'area di memoria contenente i metadati esistenti.</span><span class="sxs-lookup"><span data-stu-id="2a3b4-103">Opens an area of memory that contains existing metadata.</span></span> <span data-ttu-id="2a3b4-104">Questo metodo apre un'area di memoria specificata in cui i dati esistenti vengono considerati come metadati.</span><span class="sxs-lookup"><span data-stu-id="2a3b4-104">That is, this method opens a specified area of memory in which the existing data is treated as metadata.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2a3b4-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2a3b4-105">Syntax</span></span>  
  
```cpp  
HRESULT OpenScopeOnMemory (  
    [in]  LPCVOID     pData,
    [in]  ULONG       cbData,
    [in]  DWORD       dwOpenFlags,
    [in]  REFIID      riid,
    [out] IUnknown    **ppIUnk  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2a3b4-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="2a3b4-106">Parameters</span></span>  
 `pData`  
 <span data-ttu-id="2a3b4-107">in Puntatore che specifica l'indirizzo iniziale dell'area di memoria.</span><span class="sxs-lookup"><span data-stu-id="2a3b4-107">[in] A pointer that specifies the starting address of the memory area.</span></span>  
  
 `cbData`  
 <span data-ttu-id="2a3b4-108">in Dimensioni in byte dell'area di memoria.</span><span class="sxs-lookup"><span data-stu-id="2a3b4-108">[in] The size of the memory area, in bytes.</span></span>  
  
 `dwOpenFlags`  
 <span data-ttu-id="2a3b4-109">in Valore dell'enumerazione [CorOpenFlags](coropenflags-enumeration.md) per specificare la modalità (lettura, scrittura e così via) per l'apertura.</span><span class="sxs-lookup"><span data-stu-id="2a3b4-109">[in] A value of the [CorOpenFlags](coropenflags-enumeration.md) enumeration to specify the mode (read, write, and so on) for opening.</span></span>  
  
 `riid`  
 <span data-ttu-id="2a3b4-110">in IID dell'interfaccia di metadati desiderata da restituire. il chiamante utilizzerà l'interfaccia per importare (leggere) o creare (scrivere) metadati.</span><span class="sxs-lookup"><span data-stu-id="2a3b4-110">[in] The IID of the desired metadata interface to be returned; the caller will use the interface to import (read) or emit (write) metadata.</span></span>  
  
 <span data-ttu-id="2a3b4-111">Il valore di `riid` deve specificare una delle interfacce "Import" o "Emit".</span><span class="sxs-lookup"><span data-stu-id="2a3b4-111">The value of `riid` must specify one of the "import" or "emit" interfaces.</span></span> <span data-ttu-id="2a3b4-112">I valori validi sono IID_IMetaDataEmit, IID_IMetaDataImport, IID_IMetaDataAssemblyEmit, IID_IMetaDataAssemblyImport, IID_IMetaDataEmit2 o IID_IMetaDataImport2.</span><span class="sxs-lookup"><span data-stu-id="2a3b4-112">Valid values are IID_IMetaDataEmit, IID_IMetaDataImport, IID_IMetaDataAssemblyEmit, IID_IMetaDataAssemblyImport, IID_IMetaDataEmit2, or IID_IMetaDataImport2.</span></span>  
  
 `ppIUnk`  
 <span data-ttu-id="2a3b4-113">out Puntatore all'interfaccia restituita.</span><span class="sxs-lookup"><span data-stu-id="2a3b4-113">[out] The pointer to the returned interface.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2a3b4-114">Commenti</span><span class="sxs-lookup"><span data-stu-id="2a3b4-114">Remarks</span></span>  
 <span data-ttu-id="2a3b4-115">La copia in memoria dei metadati può essere sottoposta a query usando i metodi di una delle interfacce di "importazione" oppure aggiunti a usando i metodi di una delle interfacce "Emit".</span><span class="sxs-lookup"><span data-stu-id="2a3b4-115">The in-memory copy of the metadata can be queried using methods from one of the "import" interfaces, or added to using methods from the one of the "emit" interfaces.</span></span>  
  
 <span data-ttu-id="2a3b4-116">Il `OpenScopeOnMemory` metodo è simile al metodo [IMetaDataDispenser:: OpenScope](imetadatadispenser-openscope-method.md) , ad eccezione del fatto che i metadati di interesse sono già presenti in memoria, anziché in un file su disco.</span><span class="sxs-lookup"><span data-stu-id="2a3b4-116">The `OpenScopeOnMemory` method is similar to the [IMetaDataDispenser::OpenScope](imetadatadispenser-openscope-method.md) method, except that the metadata of interest already exists in memory, rather than in a file on disk.</span></span>  
  
 <span data-ttu-id="2a3b4-117">Se l'area di destinazione della memoria non contiene metadati di Common Language Runtime (CLR), il `OpenScopeOnMemory` metodo avrà esito negativo.</span><span class="sxs-lookup"><span data-stu-id="2a3b4-117">If the target area of memory does not contain common language runtime (CLR) metadata, the `OpenScopeOnMemory` method will fail.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2a3b4-118">Requisiti</span><span class="sxs-lookup"><span data-stu-id="2a3b4-118">Requirements</span></span>  
 <span data-ttu-id="2a3b4-119">**Piattaforma:** Vedere [requisiti di sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2a3b4-119">**Platform:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2a3b4-120">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="2a3b4-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="2a3b4-121">**Libreria:** Usato come risorsa in MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="2a3b4-121">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="2a3b4-122">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2a3b4-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2a3b4-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2a3b4-123">See also</span></span>

- [<span data-ttu-id="2a3b4-124">Interfaccia IMetaDataDispenser</span><span class="sxs-lookup"><span data-stu-id="2a3b4-124">IMetaDataDispenser Interface</span></span>](imetadatadispenser-interface.md)
- [<span data-ttu-id="2a3b4-125">Interfaccia IMetaDataDispenserEx</span><span class="sxs-lookup"><span data-stu-id="2a3b4-125">IMetaDataDispenserEx Interface</span></span>](imetadatadispenserex-interface.md)
- [<span data-ttu-id="2a3b4-126">Interfaccia IMetaDataAssemblyEmit</span><span class="sxs-lookup"><span data-stu-id="2a3b4-126">IMetaDataAssemblyEmit Interface</span></span>](imetadataassemblyemit-interface.md)
- [<span data-ttu-id="2a3b4-127">Interfaccia IMetaDataAssemblyImport</span><span class="sxs-lookup"><span data-stu-id="2a3b4-127">IMetaDataAssemblyImport Interface</span></span>](imetadataassemblyimport-interface.md)
- [<span data-ttu-id="2a3b4-128">Interfaccia IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="2a3b4-128">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="2a3b4-129">Interfaccia IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="2a3b4-129">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
- [<span data-ttu-id="2a3b4-130">Interfaccia IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="2a3b4-130">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="2a3b4-131">Interfaccia IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="2a3b4-131">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
