---
title: Metodo IMetaDataDispenser::OpenScope
ms.date: 03/30/2017
api_name:
- IMetaDataDispenser.OpenScope
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataDispenser::OpenScope
helpviewer_keywords:
- IMetaDataDispenser::OpenScope method [.NET Framework metadata]
- OpenScope method, IMetaDataDispenser interface [.NET Framework metadata]
ms.assetid: 65063ad5-e0d9-4c01-8f8b-9a5950109fa6
topic_type:
- apiref
ms.openlocfilehash: 8d9de753f1c44338a96e990def80643d591f2a8b
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2020
ms.locfileid: "84007468"
---
# <a name="imetadatadispenseropenscope-method"></a><span data-ttu-id="5c83e-102">Metodo IMetaDataDispenser::OpenScope</span><span class="sxs-lookup"><span data-stu-id="5c83e-102">IMetaDataDispenser::OpenScope Method</span></span>
<span data-ttu-id="5c83e-103">Apre un file su disco esistente ed esegue il mapping dei relativi metadati in memoria.</span><span class="sxs-lookup"><span data-stu-id="5c83e-103">Opens an existing, on-disk file and maps its metadata into memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5c83e-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5c83e-104">Syntax</span></span>  
  
```cpp  
HRESULT OpenScope (  
    [in]  LPCWSTR     szScope,
    [in]  DWORD       dwOpenFlags,
    [in]  REFIID      riid,
    [out] IUnknown    **ppIUnk  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5c83e-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="5c83e-105">Parameters</span></span>  
 `szScope`  
 <span data-ttu-id="5c83e-106">in Nome del file da aprire.</span><span class="sxs-lookup"><span data-stu-id="5c83e-106">[in] The name of the file to be opened.</span></span> <span data-ttu-id="5c83e-107">Il file deve contenere Common Language Runtime metadati (CLR).</span><span class="sxs-lookup"><span data-stu-id="5c83e-107">The file must contain common language runtime (CLR) metadata.</span></span>  
  
 `dwOpenFlags`  
 <span data-ttu-id="5c83e-108">in Valore dell'enumerazione [CorOpenFlags](coropenflags-enumeration.md) per specificare la modalità (lettura, scrittura e così via) per l'apertura.</span><span class="sxs-lookup"><span data-stu-id="5c83e-108">[in] A value of the [CorOpenFlags](coropenflags-enumeration.md) enumeration to specify the mode (read, write, and so on) for opening.</span></span>  
  
 `riid`  
 <span data-ttu-id="5c83e-109">in IID dell'interfaccia di metadati desiderata da restituire. il chiamante utilizzerà l'interfaccia per importare (leggere) o creare (scrivere) metadati.</span><span class="sxs-lookup"><span data-stu-id="5c83e-109">[in] The IID of the desired metadata interface to be returned; the caller will use the interface to import (read) or emit (write) metadata.</span></span>  
  
 <span data-ttu-id="5c83e-110">Il valore di `riid` deve specificare una delle interfacce "Import" o "Emit".</span><span class="sxs-lookup"><span data-stu-id="5c83e-110">The value of `riid` must specify one of the "import" or "emit" interfaces.</span></span> <span data-ttu-id="5c83e-111">I valori validi sono IID_IMetaDataEmit, IID_IMetaDataImport, IID_IMetaDataAssemblyEmit, IID_IMetaDataAssemblyImport, IID_IMetaDataEmit2 o IID_IMetaDataImport2.</span><span class="sxs-lookup"><span data-stu-id="5c83e-111">Valid values are IID_IMetaDataEmit, IID_IMetaDataImport, IID_IMetaDataAssemblyEmit, IID_IMetaDataAssemblyImport, IID_IMetaDataEmit2, or IID_IMetaDataImport2.</span></span>  
  
 `ppIUnk`  
 <span data-ttu-id="5c83e-112">out Puntatore all'interfaccia restituita.</span><span class="sxs-lookup"><span data-stu-id="5c83e-112">[out] The pointer to the returned interface.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5c83e-113">Commenti</span><span class="sxs-lookup"><span data-stu-id="5c83e-113">Remarks</span></span>  
 <span data-ttu-id="5c83e-114">La copia in memoria dei metadati può essere sottoposta a query usando i metodi di una delle interfacce di "importazione" oppure aggiunti a usando i metodi di una delle interfacce "Emit".</span><span class="sxs-lookup"><span data-stu-id="5c83e-114">The in-memory copy of the metadata can be queried using methods from one of the "import" interfaces, or added to using methods from the one of the "emit" interfaces.</span></span>  
  
 <span data-ttu-id="5c83e-115">Se il file di destinazione non contiene metadati CLR, il `OpenScope` metodo avrà esito negativo.</span><span class="sxs-lookup"><span data-stu-id="5c83e-115">If the target file does not contain CLR metadata, the `OpenScope` method will fail.</span></span>  
  
 <span data-ttu-id="5c83e-116">Nel .NET Framework versione 1,0 e la versione 1,1, se viene aperto un ambito con `dwOpenFlags` impostato su ofRead, è idoneo per la condivisione.</span><span class="sxs-lookup"><span data-stu-id="5c83e-116">In the .NET Framework version 1.0 and version 1.1, if a scope is opened with `dwOpenFlags` set to ofRead, it is eligible for sharing.</span></span> <span data-ttu-id="5c83e-117">Ovvero, se le chiamate successive `OpenScope` passano il nome di un file che è stato precedentemente aperto, l'ambito esistente viene riutilizzato e non viene creato un nuovo set di strutture di dati.</span><span class="sxs-lookup"><span data-stu-id="5c83e-117">That is, if subsequent calls to `OpenScope` pass in the name of a file that was previously opened, the existing scope is reused and a new set of data structures is not created.</span></span> <span data-ttu-id="5c83e-118">Tuttavia, i problemi possono verificarsi a causa di questa condivisione.</span><span class="sxs-lookup"><span data-stu-id="5c83e-118">However, problems can arise due to this sharing.</span></span>  
  
 <span data-ttu-id="5c83e-119">Nella versione .NET Framework 2,0 gli ambiti aperti con `dwOpenFlags` impostato su ofRead non sono più condivisi.</span><span class="sxs-lookup"><span data-stu-id="5c83e-119">In the .NET Framework version 2.0, scopes opened with `dwOpenFlags` set to ofRead are no longer shared.</span></span> <span data-ttu-id="5c83e-120">Usare il valore ofReadOnly per consentire la condivisione dell'ambito.</span><span class="sxs-lookup"><span data-stu-id="5c83e-120">Use the ofReadOnly value to allow the scope to be shared.</span></span> <span data-ttu-id="5c83e-121">Quando viene condiviso un ambito, le query che utilizzano le interfacce di metadati di "lettura/scrittura" avranno esito negativo.</span><span class="sxs-lookup"><span data-stu-id="5c83e-121">When a scope is shared, queries that use "read/write" metadata interfaces will fail.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5c83e-122">Requisiti</span><span class="sxs-lookup"><span data-stu-id="5c83e-122">Requirements</span></span>  
 <span data-ttu-id="5c83e-123">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5c83e-123">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5c83e-124">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="5c83e-124">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="5c83e-125">**Libreria:** Usato come risorsa in MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="5c83e-125">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="5c83e-126">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5c83e-126">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5c83e-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5c83e-127">See also</span></span>

- [<span data-ttu-id="5c83e-128">Interfaccia IMetaDataDispenser</span><span class="sxs-lookup"><span data-stu-id="5c83e-128">IMetaDataDispenser Interface</span></span>](imetadatadispenser-interface.md)
- [<span data-ttu-id="5c83e-129">Interfaccia IMetaDataDispenserEx</span><span class="sxs-lookup"><span data-stu-id="5c83e-129">IMetaDataDispenserEx Interface</span></span>](imetadatadispenserex-interface.md)
- [<span data-ttu-id="5c83e-130">Interfaccia IMetaDataAssemblyEmit</span><span class="sxs-lookup"><span data-stu-id="5c83e-130">IMetaDataAssemblyEmit Interface</span></span>](imetadataassemblyemit-interface.md)
- [<span data-ttu-id="5c83e-131">Interfaccia IMetaDataAssemblyImport</span><span class="sxs-lookup"><span data-stu-id="5c83e-131">IMetaDataAssemblyImport Interface</span></span>](imetadataassemblyimport-interface.md)
- [<span data-ttu-id="5c83e-132">Interfaccia IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="5c83e-132">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="5c83e-133">Interfaccia IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="5c83e-133">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
- [<span data-ttu-id="5c83e-134">Interfaccia IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="5c83e-134">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="5c83e-135">Interfaccia IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="5c83e-135">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
