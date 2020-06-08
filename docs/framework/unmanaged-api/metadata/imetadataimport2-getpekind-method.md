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
ms.openlocfilehash: 3626998c456e23fb922ae45a68bedb0e45a7ccba
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84490432"
---
# <a name="imetadataimport2getpekind-method"></a><span data-ttu-id="fe2b5-102">Metodo IMetaDataImport2::GetPEKind</span><span class="sxs-lookup"><span data-stu-id="fe2b5-102">IMetaDataImport2::GetPEKind Method</span></span>
<span data-ttu-id="fe2b5-103">Ottiene un valore che identifica la natura del codice nel file eseguibile portabile (PE, Portable Executable), in genere un file DLL o EXE, definito nell'ambito dei metadati corrente.</span><span class="sxs-lookup"><span data-stu-id="fe2b5-103">Gets a value identifying the nature of the code in the portable executable (PE) file, typically a DLL or EXE file, that is defined in the current metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fe2b5-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="fe2b5-104">Syntax</span></span>  
  
```cpp  
HRESULT GetPEKind (  
   [out] DWORD *pdwPEKind,  
   [out] DWORD *pdwMachine  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fe2b5-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="fe2b5-105">Parameters</span></span>  
 `pdwPEKind`  
 <span data-ttu-id="fe2b5-106">out Puntatore a un valore dell'enumerazione [CorPEKind](corpekind-enumeration.md) che descrive il file PE.</span><span class="sxs-lookup"><span data-stu-id="fe2b5-106">[out] A pointer to a value of the [CorPEKind](corpekind-enumeration.md) enumeration that describes the PE file.</span></span>  
  
 `pdwMachine`  
 <span data-ttu-id="fe2b5-107">out Puntatore a un valore che identifica l'architettura del computer.</span><span class="sxs-lookup"><span data-stu-id="fe2b5-107">[out] A pointer to a value that identifies the architecture of the machine.</span></span> <span data-ttu-id="fe2b5-108">Per i valori possibili, vedere la sezione successiva.</span><span class="sxs-lookup"><span data-stu-id="fe2b5-108">See the next section for possible values.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fe2b5-109">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="fe2b5-109">Remarks</span></span>  
 <span data-ttu-id="fe2b5-110">Il valore a cui fa riferimento il `pdwMachine` parametro può essere uno dei seguenti.</span><span class="sxs-lookup"><span data-stu-id="fe2b5-110">The value referenced by the `pdwMachine` parameter can be one of the following.</span></span>  
  
|<span data-ttu-id="fe2b5-111">Valore</span><span class="sxs-lookup"><span data-stu-id="fe2b5-111">Value</span></span>|<span data-ttu-id="fe2b5-112">Architettura del computer</span><span class="sxs-lookup"><span data-stu-id="fe2b5-112">Machine architecture</span></span>|  
|-----------|--------------------------|  
|<span data-ttu-id="fe2b5-113">IMAGE_FILE_MACHINE_I386</span><span class="sxs-lookup"><span data-stu-id="fe2b5-113">IMAGE_FILE_MACHINE_I386</span></span><br /><br /> <span data-ttu-id="fe2b5-114">0x014C</span><span class="sxs-lookup"><span data-stu-id="fe2b5-114">0x014C</span></span>|<span data-ttu-id="fe2b5-115">x86</span><span class="sxs-lookup"><span data-stu-id="fe2b5-115">x86</span></span>|  
|<span data-ttu-id="fe2b5-116">IMAGE_FILE_MACHINE_IA64</span><span class="sxs-lookup"><span data-stu-id="fe2b5-116">IMAGE_FILE_MACHINE_IA64</span></span><br /><br /> <span data-ttu-id="fe2b5-117">0x0200</span><span class="sxs-lookup"><span data-stu-id="fe2b5-117">0x0200</span></span>|<span data-ttu-id="fe2b5-118">Intel IPF</span><span class="sxs-lookup"><span data-stu-id="fe2b5-118">Intel IPF</span></span>|  
|<span data-ttu-id="fe2b5-119">IMAGE_FILE_MACHINE_AMD64</span><span class="sxs-lookup"><span data-stu-id="fe2b5-119">IMAGE_FILE_MACHINE_AMD64</span></span><br /><br /> <span data-ttu-id="fe2b5-120">0x8664</span><span class="sxs-lookup"><span data-stu-id="fe2b5-120">0x8664</span></span>|<span data-ttu-id="fe2b5-121">x64</span><span class="sxs-lookup"><span data-stu-id="fe2b5-121">x64</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="fe2b5-122">Requisiti</span><span class="sxs-lookup"><span data-stu-id="fe2b5-122">Requirements</span></span>  
 <span data-ttu-id="fe2b5-123">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fe2b5-123">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fe2b5-124">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="fe2b5-124">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="fe2b5-125">**Libreria:** Usato come risorsa in MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="fe2b5-125">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="fe2b5-126">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fe2b5-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fe2b5-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fe2b5-127">See also</span></span>

- [<span data-ttu-id="fe2b5-128">Interfaccia IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="fe2b5-128">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
- [<span data-ttu-id="fe2b5-129">Interfaccia IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="fe2b5-129">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="fe2b5-130">Enumerazione CorPEKind</span><span class="sxs-lookup"><span data-stu-id="fe2b5-130">CorPEKind Enumeration</span></span>](corpekind-enumeration.md)
