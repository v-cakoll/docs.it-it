---
title: Metodo IMetaDataAssemblyImport::GetAssemblyRefProps
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport.GetAssemblyRefProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport::GetAssemblyRefProps
helpviewer_keywords:
- IMetaDataAssemblyImport::GetAssemblyRefProps method [.NET Framework metadata]
- GetAssemblyRefProps method [.NET Framework metadata]
ms.assetid: 5c6b7fb4-cbca-4479-b650-ab9a99732ea0
topic_type:
- apiref
ms.openlocfilehash: 2858e924ab6effe192955ce53dad9d333d2d244d
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2020
ms.locfileid: "84009067"
---
# <a name="imetadataassemblyimportgetassemblyrefprops-method"></a><span data-ttu-id="963b7-102">Metodo IMetaDataAssemblyImport::GetAssemblyRefProps</span><span class="sxs-lookup"><span data-stu-id="963b7-102">IMetaDataAssemblyImport::GetAssemblyRefProps Method</span></span>
<span data-ttu-id="963b7-103">Ottiene il set di proprietà per il riferimento all'assembly con la firma dei metadati specificata.</span><span class="sxs-lookup"><span data-stu-id="963b7-103">Gets the set of properties for the assembly reference with the specified metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="963b7-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="963b7-104">Syntax</span></span>  
  
```cpp  
HRESULT GetAssemblyRefProps (  
    [in]  mdAssemblyRef        mdar,
    [out] const void          **ppbPublicKeyOrToken,
    [out] ULONG                *pcbPublicKeyOrToken,
    [out] LPWSTR               szName,
    [in]  ULONG                cchName,
    [out] ULONG                *pchName,
    [out] ASSEMBLYMETADATA     *pMetaData,
    [out] const void           **ppbHashValue,
    [out] ULONG                *pcbHashValue,
    [out] DWORD                *pdwAssemblyRefFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="963b7-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="963b7-105">Parameters</span></span>  
 `mdar`  
 <span data-ttu-id="963b7-106">in `mdAssemblyRef`Token di metadati che rappresenta il riferimento all'assembly per il quale ottenere le proprietà.</span><span class="sxs-lookup"><span data-stu-id="963b7-106">[in] The `mdAssemblyRef` metadata token that represents the assembly reference for which to get the properties.</span></span>  
  
 `ppbPublicKeyOrToken`  
 <span data-ttu-id="963b7-107">out Puntatore alla chiave pubblica o al token di metadati.</span><span class="sxs-lookup"><span data-stu-id="963b7-107">[out] A pointer to the public key or the metadata token.</span></span>  
  
 `pcbPublicKeyOrToken`  
 <span data-ttu-id="963b7-108">out Numero di byte nella chiave pubblica o nel token restituito.</span><span class="sxs-lookup"><span data-stu-id="963b7-108">[out] The number of bytes in the returned public key or token.</span></span>  
  
 `szName`  
 <span data-ttu-id="963b7-109">out Nome semplice dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="963b7-109">[out] The simple name of the assembly.</span></span>  
  
 `cchName`  
 <span data-ttu-id="963b7-110">in Dimensione, in caratteri wide, di `szName` .</span><span class="sxs-lookup"><span data-stu-id="963b7-110">[in] The size, in wide chars, of `szName`.</span></span>  
  
 `pchName`  
 <span data-ttu-id="963b7-111">out Puntatore al numero di caratteri wide effettivamente restituiti in `szName` .</span><span class="sxs-lookup"><span data-stu-id="963b7-111">[out] A pointer to the number of wide chars actually returned in `szName`.</span></span>  
  
 `pMetaData`  
 <span data-ttu-id="963b7-112">out Puntatore a una struttura ASSEMBLYMETADATA che contiene i metadati dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="963b7-112">[out] A pointer to an ASSEMBLYMETADATA structure that contains the assembly metadata.</span></span>  
  
 `ppbHashValue`  
 <span data-ttu-id="963b7-113">out Puntatore al valore hash.</span><span class="sxs-lookup"><span data-stu-id="963b7-113">[out] A pointer to the hash value.</span></span> <span data-ttu-id="963b7-114">Si tratta dell'hash, che usa l'algoritmo SHA-1, della `PublicKey` proprietà dell'assembly a cui si fa riferimento, a meno che non sia impostato il flag arfFullOriginator dell'enumerazione [AssemblyRefFlags](assemblyrefflags-enumeration.md) .</span><span class="sxs-lookup"><span data-stu-id="963b7-114">This is the hash, using the SHA-1 algorithm, of the `PublicKey` property of the assembly being referenced, unless the arfFullOriginator flag of the [AssemblyRefFlags](assemblyrefflags-enumeration.md) enumeration is set.</span></span>  
  
 `pcbHashValue`  
 <span data-ttu-id="963b7-115">out Numero di caratteri wide nel valore hash restituito.</span><span class="sxs-lookup"><span data-stu-id="963b7-115">[out] The number of wide chars in the returned hash value.</span></span>  
  
 `pdwAssemblyRefFlags`  
 <span data-ttu-id="963b7-116">out Puntatore ai flag che descrivono i metadati applicati a un assembly.</span><span class="sxs-lookup"><span data-stu-id="963b7-116">[out] A pointer to flags that describe the metadata applied to an assembly.</span></span> <span data-ttu-id="963b7-117">Il valore dei flag è una combinazione di uno o più valori [CorAssemblyFlags](corassemblyflags-enumeration.md) .</span><span class="sxs-lookup"><span data-stu-id="963b7-117">The flags value is a combination of one or more [CorAssemblyFlags](corassemblyflags-enumeration.md) values.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="963b7-118">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="963b7-118">Return Value</span></span>  
 <span data-ttu-id="963b7-119">Questo metodo restituisce S_OK se ha esito positivo; in caso contrario, restituisce uno dei codici di errore definiti nel file di intestazione Winerror. h.</span><span class="sxs-lookup"><span data-stu-id="963b7-119">This method returns S_OK if it succeeds; otherwise, it returns one of the error codes defined in the Winerror.h header file.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="963b7-120">Requisiti</span><span class="sxs-lookup"><span data-stu-id="963b7-120">Requirements</span></span>  
 <span data-ttu-id="963b7-121">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="963b7-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="963b7-122">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="963b7-122">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="963b7-123">**Libreria:** Usato come risorsa in MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="963b7-123">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="963b7-124">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="963b7-124">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="963b7-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="963b7-125">See also</span></span>

- [<span data-ttu-id="963b7-126">Interfaccia IMetaDataAssemblyImport</span><span class="sxs-lookup"><span data-stu-id="963b7-126">IMetaDataAssemblyImport Interface</span></span>](imetadataassemblyimport-interface.md)
