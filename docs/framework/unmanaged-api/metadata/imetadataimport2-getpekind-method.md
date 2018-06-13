---
title: Metodo IMetaDataImport2::GetPEKind
ms.date: 03/30/2017
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c938ef8783a122dec2a5f5bd3775661d68fba62c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33449403"
---
# <a name="imetadataimport2getpekind-method"></a><span data-ttu-id="862bc-102">Metodo IMetaDataImport2::GetPEKind</span><span class="sxs-lookup"><span data-stu-id="862bc-102">IMetaDataImport2::GetPEKind Method</span></span>
<span data-ttu-id="862bc-103">Ottiene un valore che identifica il tipo di codice nel file eseguibile portabile (PE) del file, in genere un file DLL o EXE, definito nell'ambito dei metadati corrente.</span><span class="sxs-lookup"><span data-stu-id="862bc-103">Gets a value identifying the nature of the code in the portable executable (PE) file, typically a DLL or EXE file, that is defined in the current metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="862bc-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="862bc-104">Syntax</span></span>  
  
```  
HRESULT GetPEKind (  
   [out] DWORD *pdwPEKind,  
   [out] DWORD *pdwMachine  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="862bc-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="862bc-105">Parameters</span></span>  
 `pdwPEKind`  
 <span data-ttu-id="862bc-106">[out] Un puntatore a un valore di [CorPEKind](../../../../docs/framework/unmanaged-api/metadata/corpekind-enumeration.md) enumerazione che descrive il file PE.</span><span class="sxs-lookup"><span data-stu-id="862bc-106">[out] A pointer to a value of the [CorPEKind](../../../../docs/framework/unmanaged-api/metadata/corpekind-enumeration.md) enumeration that describes the PE file.</span></span>  
  
 `pdwMachine`  
 <span data-ttu-id="862bc-107">[out] Puntatore a un valore che identifica l'architettura del computer.</span><span class="sxs-lookup"><span data-stu-id="862bc-107">[out] A pointer to a value that identifies the architecture of the machine.</span></span> <span data-ttu-id="862bc-108">Vedere la sezione successiva per i valori possibili.</span><span class="sxs-lookup"><span data-stu-id="862bc-108">See the next section for possible values.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="862bc-109">Note</span><span class="sxs-lookup"><span data-stu-id="862bc-109">Remarks</span></span>  
 <span data-ttu-id="862bc-110">Il valore a cui fa riferimento il `pdwMachine` parametro può essere uno dei seguenti.</span><span class="sxs-lookup"><span data-stu-id="862bc-110">The value referenced by the `pdwMachine` parameter can be one of the following.</span></span>  
  
|<span data-ttu-id="862bc-111">Valore</span><span class="sxs-lookup"><span data-stu-id="862bc-111">Value</span></span>|<span data-ttu-id="862bc-112">Architettura del computer</span><span class="sxs-lookup"><span data-stu-id="862bc-112">Machine architecture</span></span>|  
|-----------|--------------------------|  
|<span data-ttu-id="862bc-113">IMAGE_FILE_MACHINE_I386</span><span class="sxs-lookup"><span data-stu-id="862bc-113">IMAGE_FILE_MACHINE_I386</span></span><br /><br /> <span data-ttu-id="862bc-114">0x014C</span><span class="sxs-lookup"><span data-stu-id="862bc-114">0x014C</span></span>|<span data-ttu-id="862bc-115">x86</span><span class="sxs-lookup"><span data-stu-id="862bc-115">x86</span></span>|  
|<span data-ttu-id="862bc-116">IMAGE_FILE_MACHINE_IA64</span><span class="sxs-lookup"><span data-stu-id="862bc-116">IMAGE_FILE_MACHINE_IA64</span></span><br /><br /> <span data-ttu-id="862bc-117">0x0200</span><span class="sxs-lookup"><span data-stu-id="862bc-117">0x0200</span></span>|<span data-ttu-id="862bc-118">Intel IPF</span><span class="sxs-lookup"><span data-stu-id="862bc-118">Intel IPF</span></span>|  
|<span data-ttu-id="862bc-119">IMAGE_FILE_MACHINE_AMD64</span><span class="sxs-lookup"><span data-stu-id="862bc-119">IMAGE_FILE_MACHINE_AMD64</span></span><br /><br /> <span data-ttu-id="862bc-120">0x8664</span><span class="sxs-lookup"><span data-stu-id="862bc-120">0x8664</span></span>|<span data-ttu-id="862bc-121">X64</span><span class="sxs-lookup"><span data-stu-id="862bc-121">x64</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="862bc-122">Requisiti</span><span class="sxs-lookup"><span data-stu-id="862bc-122">Requirements</span></span>  
 <span data-ttu-id="862bc-123">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="862bc-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="862bc-124">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="862bc-124">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="862bc-125">**Libreria:** usata come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="862bc-125">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="862bc-126">**Versioni di .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="862bc-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="862bc-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="862bc-127">See Also</span></span>  
 [<span data-ttu-id="862bc-128">Interfaccia IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="862bc-128">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)  
 [<span data-ttu-id="862bc-129">Interfaccia IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="862bc-129">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="862bc-130">Enumerazione CorPEKind</span><span class="sxs-lookup"><span data-stu-id="862bc-130">CorPEKind Enumeration</span></span>](../../../../docs/framework/unmanaged-api/metadata/corpekind-enumeration.md)
