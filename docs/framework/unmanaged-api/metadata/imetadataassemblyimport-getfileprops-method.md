---
title: Metodo IMetaDataAssemblyImport::GetFileProps
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport.GetFileProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport::GetFileProps
helpviewer_keywords:
- GetFileProps method [.NET Framework metadata]
- IMetaDataAssemblyImport::GetFileProps method [.NET Framework metadata]
ms.assetid: c5e6216f-ae3d-4697-9688-66b69c1251ec
topic_type:
- apiref
ms.openlocfilehash: 78c192f10f629a0c1316ae7af7fc774819f4de8f
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2020
ms.locfileid: "84007481"
---
# <a name="imetadataassemblyimportgetfileprops-method"></a><span data-ttu-id="433d3-102">Metodo IMetaDataAssemblyImport::GetFileProps</span><span class="sxs-lookup"><span data-stu-id="433d3-102">IMetaDataAssemblyImport::GetFileProps Method</span></span>
<span data-ttu-id="433d3-103">Ottiene le proprietà del file con la firma dei metadati specificata.</span><span class="sxs-lookup"><span data-stu-id="433d3-103">Gets the properties of the file with the specified metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="433d3-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="433d3-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFileProps (  
    [in]  mdFile      mdf,
    [out] LPWSTR      szName,
    [in]  ULONG       cchName,
    [out] ULONG       *pchName,
    [out] const void  **ppbHashValue,
    [out] ULONG       *pcbHashValue,
    [out] DWORD       *pdwFileFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="433d3-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="433d3-105">Parameters</span></span>  
 `mdf`  
 <span data-ttu-id="433d3-106">in `mdFile`Token di metadati che rappresenta il file per il quale ottenere le proprietà.</span><span class="sxs-lookup"><span data-stu-id="433d3-106">[in] The `mdFile` metadata token that represents the file for which to get the properties.</span></span>  
  
 `szName`  
 <span data-ttu-id="433d3-107">out Nome semplice del file.</span><span class="sxs-lookup"><span data-stu-id="433d3-107">[out] The simple name of the file.</span></span>  
  
 `cchName`  
 <span data-ttu-id="433d3-108">in Dimensione, in caratteri wide, di `szName` .</span><span class="sxs-lookup"><span data-stu-id="433d3-108">[in] The size, in wide chars, of `szName`.</span></span>  
  
 `pchName`  
 <span data-ttu-id="433d3-109">out Numero di caratteri wide effettivamente restituiti in `szName` .</span><span class="sxs-lookup"><span data-stu-id="433d3-109">[out] The number of wide chars actually returned in `szName`.</span></span>  
  
 `ppbHashValue`  
 <span data-ttu-id="433d3-110">out Puntatore al valore hash.</span><span class="sxs-lookup"><span data-stu-id="433d3-110">[out] A pointer to the hash value.</span></span> <span data-ttu-id="433d3-111">Si tratta dell'hash, usando l'algoritmo SHA-1, del file.</span><span class="sxs-lookup"><span data-stu-id="433d3-111">This is the hash, using the SHA-1 algorithm, of the file.</span></span>  
  
 `pcbHashValue`  
 <span data-ttu-id="433d3-112">out Numero di caratteri wide nel valore hash restituito.</span><span class="sxs-lookup"><span data-stu-id="433d3-112">[out] The number of wide chars in the returned hash value.</span></span>  
  
 `pdwFileFlags`  
 <span data-ttu-id="433d3-113">out Puntatore ai flag che descrivono i metadati applicati a un file.</span><span class="sxs-lookup"><span data-stu-id="433d3-113">[out] A pointer to the flags that describe the metadata applied to a file.</span></span> <span data-ttu-id="433d3-114">Il valore dei flag è una combinazione di uno o più valori [CorFileFlags](corfileflags-enumeration.md) .</span><span class="sxs-lookup"><span data-stu-id="433d3-114">The flags value is a combination of one or more [CorFileFlags](corfileflags-enumeration.md) values.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="433d3-115">Requisiti</span><span class="sxs-lookup"><span data-stu-id="433d3-115">Requirements</span></span>  
 <span data-ttu-id="433d3-116">**Piattaforma:** Vedere [requisiti di sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="433d3-116">**Platform:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="433d3-117">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="433d3-117">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="433d3-118">**Libreria:** Usato come risorsa in MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="433d3-118">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="433d3-119">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="433d3-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="433d3-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="433d3-120">See also</span></span>

- [<span data-ttu-id="433d3-121">Interfaccia IMetaDataAssemblyImport</span><span class="sxs-lookup"><span data-stu-id="433d3-121">IMetaDataAssemblyImport Interface</span></span>](imetadataassemblyimport-interface.md)
