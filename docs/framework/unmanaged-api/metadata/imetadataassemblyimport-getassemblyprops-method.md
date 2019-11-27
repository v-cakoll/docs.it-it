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
ms.openlocfilehash: c3c57074ae53e2e1d8d41aa04cb6eb6089db58b5
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74449436"
---
# <a name="imetadataassemblyimportgetassemblyprops-method"></a><span data-ttu-id="ed7fd-102">Metodo IMetaDataAssemblyImport::GetAssemblyProps</span><span class="sxs-lookup"><span data-stu-id="ed7fd-102">IMetaDataAssemblyImport::GetAssemblyProps Method</span></span>
<span data-ttu-id="ed7fd-103">Ottiene il set di proprietà per l'assembly con la firma dei metadati specificata.</span><span class="sxs-lookup"><span data-stu-id="ed7fd-103">Gets the set of properties for the assembly with the specified metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ed7fd-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ed7fd-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="ed7fd-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="ed7fd-105">Parameters</span></span>  
 `mda`  
 <span data-ttu-id="ed7fd-106">[in].</span><span class="sxs-lookup"><span data-stu-id="ed7fd-106">[in].</span></span> <span data-ttu-id="ed7fd-107">Il `mdAssembly` token di metadati che rappresenta l'assembly per il quale ottenere le proprietà.</span><span class="sxs-lookup"><span data-stu-id="ed7fd-107">The `mdAssembly` metadata token that represents the assembly for which to get the properties.</span></span>  
  
 `ppbPublicKey`  
 <span data-ttu-id="ed7fd-108">out Puntatore alla chiave pubblica o al token di metadati.</span><span class="sxs-lookup"><span data-stu-id="ed7fd-108">[out] A pointer to the public key or the metadata token.</span></span>  
  
 `pcbPublicKey`  
 <span data-ttu-id="ed7fd-109">out Numero di byte nella chiave pubblica restituita.</span><span class="sxs-lookup"><span data-stu-id="ed7fd-109">[out] The number of bytes in the returned public key.</span></span>  
  
 `pulHashAlgId`  
 <span data-ttu-id="ed7fd-110">out Puntatore all'algoritmo utilizzato per eseguire l'hashing dei file nell'assembly.</span><span class="sxs-lookup"><span data-stu-id="ed7fd-110">[out] A pointer to the algorithm used to hash the files in the assembly.</span></span>  
  
 `szName`  
 <span data-ttu-id="ed7fd-111">out Nome semplice dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="ed7fd-111">[out] The simple name of the assembly.</span></span>  
  
 `cchName`  
 <span data-ttu-id="ed7fd-112">in Dimensione, in caratteri wide, di `szName`.</span><span class="sxs-lookup"><span data-stu-id="ed7fd-112">[in] The size, in wide chars, of `szName`.</span></span>  
  
 `pchName`  
 <span data-ttu-id="ed7fd-113">out Numero di caratteri wide effettivamente restituiti in `szName`.</span><span class="sxs-lookup"><span data-stu-id="ed7fd-113">[out] The number of wide chars actually returned in `szName`.</span></span>  
  
 `pMetaData`  
 <span data-ttu-id="ed7fd-114">out Puntatore a una struttura ASSEMBLYMETADATA che contiene i metadati dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="ed7fd-114">[out] A pointer to an ASSEMBLYMETADATA structure that contains the assembly metadata.</span></span>  
  
 `pdwAssemblyFlags`  
 <span data-ttu-id="ed7fd-115">out Flag che descrivono i metadati applicati a un assembly.</span><span class="sxs-lookup"><span data-stu-id="ed7fd-115">[out] Flags that describe the metadata applied to an assembly.</span></span> <span data-ttu-id="ed7fd-116">Questo valore è una combinazione di uno o più valori [CorAssemblyFlags](../../../../docs/framework/unmanaged-api/metadata/corassemblyflags-enumeration.md) .</span><span class="sxs-lookup"><span data-stu-id="ed7fd-116">This value is a combination of one or more [CorAssemblyFlags](../../../../docs/framework/unmanaged-api/metadata/corassemblyflags-enumeration.md) values.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ed7fd-117">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ed7fd-117">Requirements</span></span>  
 <span data-ttu-id="ed7fd-118">**Piattaforme:** vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ed7fd-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ed7fd-119">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="ed7fd-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ed7fd-120">**Libreria:** Usato come risorsa in MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="ed7fd-120">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="ed7fd-121">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ed7fd-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ed7fd-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ed7fd-122">See also</span></span>

- [<span data-ttu-id="ed7fd-123">Interfaccia IMetaDataAssemblyImport</span><span class="sxs-lookup"><span data-stu-id="ed7fd-123">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
