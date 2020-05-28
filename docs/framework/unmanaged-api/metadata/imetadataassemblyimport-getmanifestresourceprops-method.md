---
title: Metodo IMetaDataAssemblyImport::GetManifestResourceProps
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport.GetManifestResourceProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport::GetManifestResourceProps
helpviewer_keywords:
- GetManifestResourceProps method [.NET Framework metadata]
- IMetaDataAssemblyImport::GetManifestResourceProps method [.NET Framework metadata]
ms.assetid: 00be4789-ac63-4397-b2ec-1629a5c5a585
topic_type:
- apiref
ms.openlocfilehash: c0b6d53ce3be3aed6a577bf6e38a281928499848
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2020
ms.locfileid: "84009028"
---
# <a name="imetadataassemblyimportgetmanifestresourceprops-method"></a><span data-ttu-id="324d1-102">Metodo IMetaDataAssemblyImport::GetManifestResourceProps</span><span class="sxs-lookup"><span data-stu-id="324d1-102">IMetaDataAssemblyImport::GetManifestResourceProps Method</span></span>
<span data-ttu-id="324d1-103">Ottiene il set di proprietà della risorsa del manifesto con la firma dei metadati specificata.</span><span class="sxs-lookup"><span data-stu-id="324d1-103">Gets the set of properties of the manifest resource with the specified metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="324d1-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="324d1-104">Syntax</span></span>  
  
```cpp  
HRESULT GetManifestResourceProps (  
    [in]  mdManifestResource   mdmr,
    [out] LPWSTR               szName,
    [in]  ULONG                cchName,
    [out] ULONG                *pchName,
    [out] mdToken              *ptkImplementation,
    [out] DWORD                *pdwOffset,
    [out] DWORD                *pdwResourceFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="324d1-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="324d1-105">Parameters</span></span>  
 `mdmr`  
 <span data-ttu-id="324d1-106">in `mdManifestResource`Token che rappresenta la risorsa per la quale ottenere le proprietà.</span><span class="sxs-lookup"><span data-stu-id="324d1-106">[in] An `mdManifestResource` token that represents the resource for which to get the properties.</span></span>  
  
 `szName`  
 <span data-ttu-id="324d1-107">out Nome della risorsa.</span><span class="sxs-lookup"><span data-stu-id="324d1-107">[out] The name of the resource.</span></span>  
  
 `cchName`  
 <span data-ttu-id="324d1-108">in Dimensione, in caratteri wide, di `szName` .</span><span class="sxs-lookup"><span data-stu-id="324d1-108">[in] The size, in wide chars, of `szName`.</span></span>  
  
 `pchName`  
 <span data-ttu-id="324d1-109">out Puntatore al numero di caratteri wide effettivamente restituiti in `szName` .</span><span class="sxs-lookup"><span data-stu-id="324d1-109">[out] A pointer to the number of wide chars actually returned in `szName`.</span></span>  
  
 `ptkImplementation`  
 <span data-ttu-id="324d1-110">out Puntatore a un `mdFile` token o a un `mdAssemblyRef` token che rappresenta il file o l'assembly, rispettivamente, che contiene la risorsa.</span><span class="sxs-lookup"><span data-stu-id="324d1-110">[out] A pointer to an `mdFile` token or an `mdAssemblyRef` token that represents the file or assembly, respectively, that contains the resource.</span></span>  
  
 `pdwOffset`  
 <span data-ttu-id="324d1-111">out Puntatore a un valore che specifica l'offset all'inizio della risorsa all'interno del file.</span><span class="sxs-lookup"><span data-stu-id="324d1-111">[out] A pointer to a value that specifies the offset to the beginning of the resource within the file.</span></span>  
  
 `pdwResourceFlags`  
 <span data-ttu-id="324d1-112">out Puntatore ai flag che descrivono i metadati applicati a una risorsa.</span><span class="sxs-lookup"><span data-stu-id="324d1-112">[out] A pointer to flags that describe the metadata applied to a resource.</span></span> <span data-ttu-id="324d1-113">Il valore dei flag è una combinazione di uno o più valori [CorManifestResourceFlags](cormanifestresourceflags-enumeration.md) .</span><span class="sxs-lookup"><span data-stu-id="324d1-113">The flags value is a combination of one or more [CorManifestResourceFlags](cormanifestresourceflags-enumeration.md) values.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="324d1-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="324d1-114">Requirements</span></span>  
 <span data-ttu-id="324d1-115">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="324d1-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="324d1-116">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="324d1-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="324d1-117">**Libreria:** Usato come risorsa in MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="324d1-117">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="324d1-118">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="324d1-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="324d1-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="324d1-119">See also</span></span>

- [<span data-ttu-id="324d1-120">Interfaccia IMetaDataAssemblyImport</span><span class="sxs-lookup"><span data-stu-id="324d1-120">IMetaDataAssemblyImport Interface</span></span>](imetadataassemblyimport-interface.md)
