---
title: Metodo IMetaDataImport2::GetPEKind
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- IMetaDataImport2.GetPEKind
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport2::GetPEKind
helpviewer_keywords:
- GetPEKind method [.NET Framework metadata]
- IMetaDataImport2::GetPEKind method [.NET Framework metadata]
ms.assetid: d91c3d89-8022-4a4c-a2a2-a8af2c387507
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: e8dc31877ba3550fa8faf610b831dfd2e7b313ff
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataimport2getpekind-method"></a><span data-ttu-id="b530d-102">Metodo IMetaDataImport2::GetPEKind</span><span class="sxs-lookup"><span data-stu-id="b530d-102">IMetaDataImport2::GetPEKind Method</span></span>
<span data-ttu-id="b530d-103">Ottiene un valore che identifica il tipo di codice nel file eseguibile portabile (PE) del file, in genere un file DLL o EXE, definito nell'ambito dei metadati corrente.</span><span class="sxs-lookup"><span data-stu-id="b530d-103">Gets a value identifying the nature of the code in the portable executable (PE) file, typically a DLL or EXE file, that is defined in the current metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b530d-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b530d-104">Syntax</span></span>  
  
```  
HRESULT GetPEKind (  
   [out] DWORD *pdwPEKind,  
   [out] DWORD *pdwMachine  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b530d-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="b530d-105">Parameters</span></span>  
 `pdwPEKind`  
 <span data-ttu-id="b530d-106">[out] Un puntatore a un valore di [CorPEKind](../../../../docs/framework/unmanaged-api/metadata/corpekind-enumeration.md) enumerazione che descrive il file PE.</span><span class="sxs-lookup"><span data-stu-id="b530d-106">[out] A pointer to a value of the [CorPEKind](../../../../docs/framework/unmanaged-api/metadata/corpekind-enumeration.md) enumeration that describes the PE file.</span></span>  
  
 `pdwMachine`  
 <span data-ttu-id="b530d-107">[out] Puntatore a un valore che identifica l'architettura del computer.</span><span class="sxs-lookup"><span data-stu-id="b530d-107">[out] A pointer to a value that identifies the architecture of the machine.</span></span> <span data-ttu-id="b530d-108">Vedere la sezione successiva per i valori possibili.</span><span class="sxs-lookup"><span data-stu-id="b530d-108">See the next section for possible values.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b530d-109">Note</span><span class="sxs-lookup"><span data-stu-id="b530d-109">Remarks</span></span>  
 <span data-ttu-id="b530d-110">Il valore a cui fa riferimento il `pdwMachine` parametro può essere uno dei seguenti.</span><span class="sxs-lookup"><span data-stu-id="b530d-110">The value referenced by the `pdwMachine` parameter can be one of the following.</span></span>  
  
|<span data-ttu-id="b530d-111">Valore</span><span class="sxs-lookup"><span data-stu-id="b530d-111">Value</span></span>|<span data-ttu-id="b530d-112">Architettura del computer</span><span class="sxs-lookup"><span data-stu-id="b530d-112">Machine architecture</span></span>|  
|-----------|--------------------------|  
|<span data-ttu-id="b530d-113">IMAGE_FILE_MACHINE_I386</span><span class="sxs-lookup"><span data-stu-id="b530d-113">IMAGE_FILE_MACHINE_I386</span></span><br /><br /> <span data-ttu-id="b530d-114">0x014C</span><span class="sxs-lookup"><span data-stu-id="b530d-114">0x014C</span></span>|<span data-ttu-id="b530d-115">x86</span><span class="sxs-lookup"><span data-stu-id="b530d-115">x86</span></span>|  
|<span data-ttu-id="b530d-116">IMAGE_FILE_MACHINE_IA64</span><span class="sxs-lookup"><span data-stu-id="b530d-116">IMAGE_FILE_MACHINE_IA64</span></span><br /><br /> <span data-ttu-id="b530d-117">0x0200</span><span class="sxs-lookup"><span data-stu-id="b530d-117">0x0200</span></span>|<span data-ttu-id="b530d-118">Intel IPF</span><span class="sxs-lookup"><span data-stu-id="b530d-118">Intel IPF</span></span>|  
|<span data-ttu-id="b530d-119">IMAGE_FILE_MACHINE_AMD64</span><span class="sxs-lookup"><span data-stu-id="b530d-119">IMAGE_FILE_MACHINE_AMD64</span></span><br /><br /> <span data-ttu-id="b530d-120">0x8664</span><span class="sxs-lookup"><span data-stu-id="b530d-120">0x8664</span></span>|<span data-ttu-id="b530d-121">X64</span><span class="sxs-lookup"><span data-stu-id="b530d-121">x64</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b530d-122">Requisiti</span><span class="sxs-lookup"><span data-stu-id="b530d-122">Requirements</span></span>  
 <span data-ttu-id="b530d-123">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b530d-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b530d-124">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="b530d-124">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="b530d-125">**Libreria:** usata come risorsa in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="b530d-125">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="b530d-126">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b530d-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b530d-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b530d-127">See Also</span></span>  
 [<span data-ttu-id="b530d-128">Interfaccia IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="b530d-128">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)  
 [<span data-ttu-id="b530d-129">Interfaccia IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="b530d-129">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="b530d-130">Enumerazione CorPEKind</span><span class="sxs-lookup"><span data-stu-id="b530d-130">CorPEKind Enumeration</span></span>](../../../../docs/framework/unmanaged-api/metadata/corpekind-enumeration.md)
