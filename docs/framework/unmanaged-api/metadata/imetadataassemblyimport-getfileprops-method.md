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
ms.openlocfilehash: beb697d80417b937876a0887e4376341185a47d9
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74447220"
---
# <a name="imetadataassemblyimportgetfileprops-method"></a><span data-ttu-id="466e0-102">Metodo IMetaDataAssemblyImport::GetFileProps</span><span class="sxs-lookup"><span data-stu-id="466e0-102">IMetaDataAssemblyImport::GetFileProps Method</span></span>
<span data-ttu-id="466e0-103">Ottiene le proprietà del file con la firma dei metadati specificata.</span><span class="sxs-lookup"><span data-stu-id="466e0-103">Gets the properties of the file with the specified metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="466e0-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="466e0-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="466e0-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="466e0-105">Parameters</span></span>  
 `mdf`  
 <span data-ttu-id="466e0-106">in Il `mdFile` token di metadati che rappresenta il file per il quale ottenere le proprietà.</span><span class="sxs-lookup"><span data-stu-id="466e0-106">[in] The `mdFile` metadata token that represents the file for which to get the properties.</span></span>  
  
 `szName`  
 <span data-ttu-id="466e0-107">out Nome semplice del file.</span><span class="sxs-lookup"><span data-stu-id="466e0-107">[out] The simple name of the file.</span></span>  
  
 `cchName`  
 <span data-ttu-id="466e0-108">in Dimensione, in caratteri wide, di `szName`.</span><span class="sxs-lookup"><span data-stu-id="466e0-108">[in] The size, in wide chars, of `szName`.</span></span>  
  
 `pchName`  
 <span data-ttu-id="466e0-109">out Numero di caratteri wide effettivamente restituiti in `szName`.</span><span class="sxs-lookup"><span data-stu-id="466e0-109">[out] The number of wide chars actually returned in `szName`.</span></span>  
  
 `ppbHashValue`  
 <span data-ttu-id="466e0-110">out Puntatore al valore hash.</span><span class="sxs-lookup"><span data-stu-id="466e0-110">[out] A pointer to the hash value.</span></span> <span data-ttu-id="466e0-111">Si tratta dell'hash, usando l'algoritmo SHA-1, del file.</span><span class="sxs-lookup"><span data-stu-id="466e0-111">This is the hash, using the SHA-1 algorithm, of the file.</span></span>  
  
 `pcbHashValue`  
 <span data-ttu-id="466e0-112">out Numero di caratteri wide nel valore hash restituito.</span><span class="sxs-lookup"><span data-stu-id="466e0-112">[out] The number of wide chars in the returned hash value.</span></span>  
  
 `pdwFileFlags`  
 <span data-ttu-id="466e0-113">out Puntatore ai flag che descrivono i metadati applicati a un file.</span><span class="sxs-lookup"><span data-stu-id="466e0-113">[out] A pointer to the flags that describe the metadata applied to a file.</span></span> <span data-ttu-id="466e0-114">Il valore dei flag è una combinazione di uno o più valori [CorFileFlags](../../../../docs/framework/unmanaged-api/metadata/corfileflags-enumeration.md) .</span><span class="sxs-lookup"><span data-stu-id="466e0-114">The flags value is a combination of one or more [CorFileFlags](../../../../docs/framework/unmanaged-api/metadata/corfileflags-enumeration.md) values.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="466e0-115">Requisiti</span><span class="sxs-lookup"><span data-stu-id="466e0-115">Requirements</span></span>  
 <span data-ttu-id="466e0-116">**Piattaforma:** Vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="466e0-116">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="466e0-117">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="466e0-117">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="466e0-118">**Libreria:** Usato come risorsa in MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="466e0-118">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="466e0-119">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="466e0-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="466e0-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="466e0-120">See also</span></span>

- [<span data-ttu-id="466e0-121">Interfaccia IMetaDataAssemblyImport</span><span class="sxs-lookup"><span data-stu-id="466e0-121">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
