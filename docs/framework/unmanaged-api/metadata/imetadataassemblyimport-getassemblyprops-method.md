---
title: Metodo IMetaDataAssemblyImport::GetAssemblyProps
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport.GetAssemblyProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport::GetAssemblyProps
helpviewer_keywords:
- GetAssemblyProps method [.NET Framework metadata]
- IMetaDataAssemblyImport::GetAssemblyProps method [.NET Framework metadata]
ms.assetid: 0eaa4aa9-9441-444a-920c-e4b2a2db899e
topic_type:
- apiref
ms.openlocfilehash: a90deaf3e9ddf326c6fca558cbb4681fc40e022d
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2020
ms.locfileid: "84009054"
---
# <a name="imetadataassemblyimportgetassemblyprops-method"></a><span data-ttu-id="ad30b-102">Metodo IMetaDataAssemblyImport::GetAssemblyProps</span><span class="sxs-lookup"><span data-stu-id="ad30b-102">IMetaDataAssemblyImport::GetAssemblyProps Method</span></span>
<span data-ttu-id="ad30b-103">Ottiene il set di proprietà per l'assembly con la firma dei metadati specificata.</span><span class="sxs-lookup"><span data-stu-id="ad30b-103">Gets the set of properties for the assembly with the specified metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ad30b-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ad30b-104">Syntax</span></span>  
  
```cpp  
HRESULT GetAssemblyProps (  
    [in]  mdAssembly          mda,  
    [out] const void          **ppbPublicKey,
    [out] ULONG               *pcbPublicKey,  
    [out] ULONG               *pulHashAlgId,  
    [out] LPWSTR              szName,  
    [in] ULONG                cchName,  
    [out] ULONG               *pchName,  
    [out] ASSEMBLYMETADATA    *pMetaData,  
    [out] DWORD               *pdwAssemblyFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ad30b-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="ad30b-105">Parameters</span></span>  
 `mda`  
 <span data-ttu-id="ad30b-106">[in].</span><span class="sxs-lookup"><span data-stu-id="ad30b-106">[in].</span></span> <span data-ttu-id="ad30b-107">`mdAssembly`Token di metadati che rappresenta l'assembly per il quale ottenere le proprietà.</span><span class="sxs-lookup"><span data-stu-id="ad30b-107">The `mdAssembly` metadata token that represents the assembly for which to get the properties.</span></span>  
  
 `ppbPublicKey`  
 <span data-ttu-id="ad30b-108">out Puntatore alla chiave pubblica o al token di metadati.</span><span class="sxs-lookup"><span data-stu-id="ad30b-108">[out] A pointer to the public key or the metadata token.</span></span>  
  
 `pcbPublicKey`  
 <span data-ttu-id="ad30b-109">out Numero di byte nella chiave pubblica restituita.</span><span class="sxs-lookup"><span data-stu-id="ad30b-109">[out] The number of bytes in the returned public key.</span></span>  
  
 `pulHashAlgId`  
 <span data-ttu-id="ad30b-110">out Puntatore all'algoritmo utilizzato per eseguire l'hashing dei file nell'assembly.</span><span class="sxs-lookup"><span data-stu-id="ad30b-110">[out] A pointer to the algorithm used to hash the files in the assembly.</span></span>  
  
 `szName`  
 <span data-ttu-id="ad30b-111">out Nome semplice dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="ad30b-111">[out] The simple name of the assembly.</span></span>  
  
 `cchName`  
 <span data-ttu-id="ad30b-112">in Dimensione, in caratteri wide, di `szName` .</span><span class="sxs-lookup"><span data-stu-id="ad30b-112">[in] The size, in wide chars, of `szName`.</span></span>  
  
 `pchName`  
 <span data-ttu-id="ad30b-113">out Numero di caratteri wide effettivamente restituiti in `szName` .</span><span class="sxs-lookup"><span data-stu-id="ad30b-113">[out] The number of wide chars actually returned in `szName`.</span></span>  
  
 `pMetaData`  
 <span data-ttu-id="ad30b-114">out Puntatore a una struttura ASSEMBLYMETADATA che contiene i metadati dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="ad30b-114">[out] A pointer to an ASSEMBLYMETADATA structure that contains the assembly metadata.</span></span>  
  
 `pdwAssemblyFlags`  
 <span data-ttu-id="ad30b-115">out Flag che descrivono i metadati applicati a un assembly.</span><span class="sxs-lookup"><span data-stu-id="ad30b-115">[out] Flags that describe the metadata applied to an assembly.</span></span> <span data-ttu-id="ad30b-116">Questo valore è una combinazione di uno o più valori [CorAssemblyFlags](corassemblyflags-enumeration.md) .</span><span class="sxs-lookup"><span data-stu-id="ad30b-116">This value is a combination of one or more [CorAssemblyFlags](corassemblyflags-enumeration.md) values.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ad30b-117">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ad30b-117">Requirements</span></span>  
 <span data-ttu-id="ad30b-118">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ad30b-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ad30b-119">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="ad30b-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ad30b-120">**Libreria:** Usato come risorsa in MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="ad30b-120">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="ad30b-121">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ad30b-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ad30b-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ad30b-122">See also</span></span>

- [<span data-ttu-id="ad30b-123">Interfaccia IMetaDataAssemblyImport</span><span class="sxs-lookup"><span data-stu-id="ad30b-123">IMetaDataAssemblyImport Interface</span></span>](imetadataassemblyimport-interface.md)
