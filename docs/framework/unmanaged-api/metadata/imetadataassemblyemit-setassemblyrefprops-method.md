---
title: Metodo IMetaDataAssemblyEmit::SetAssemblyRefProps
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyEmit.SetAssemblyRefProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyEmit::SetAssemblyRefProps
helpviewer_keywords:
- SetAssemblyRefProps method [.NET Framework metadata]
- IMetaDataAssemblyEmit::SetAssemblyRefProps method [.NET Framework metadata]
ms.assetid: 70a32bf3-9051-4f96-ae87-11356d06a073
topic_type:
- apiref
ms.openlocfilehash: fb381a872cbeb787da0c6920f2cdeef434fb33ea
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008092"
---
# <a name="imetadataassemblyemitsetassemblyrefprops-method"></a><span data-ttu-id="610a8-102">Metodo IMetaDataAssemblyEmit::SetAssemblyRefProps</span><span class="sxs-lookup"><span data-stu-id="610a8-102">IMetaDataAssemblyEmit::SetAssemblyRefProps Method</span></span>
<span data-ttu-id="610a8-103">Modifica la struttura dei metadati `AssemblyRef` specificata.</span><span class="sxs-lookup"><span data-stu-id="610a8-103">Modifies the specified `AssemblyRef` metadata structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="610a8-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="610a8-104">Syntax</span></span>  
  
```cpp  
HRESULT SetAssemblyRefProps (  
    [in] mdAssemblyRef              ar,  
    [in] const void                 *pbPublicKeyOrToken,  
    [in] ULONG                      cbPublicKeyOrToken,  
    [in] LPCWSTR                    szName,
    [in] const ASSEMBLYMETADATA     *pMetaData,
    [in] const void                 *pbHashValue,  
    [in] ULONG                      cbHashValue,  
    [in] DWORD                      dwAssemblyRefFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="610a8-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="610a8-105">Parameters</span></span>  
 `ar`  
 <span data-ttu-id="610a8-106">in Token di metadati che specifica la `AssemblyRef` struttura dei metadati da modificare.</span><span class="sxs-lookup"><span data-stu-id="610a8-106">[in] The metadata token that specifies the `AssemblyRef` metadata structure to be modified.</span></span>  
  
 `pbPublicKeyOrToken`  
 <span data-ttu-id="610a8-107">in Chiave pubblica del server di pubblicazione dell'assembly a cui si fa riferimento.</span><span class="sxs-lookup"><span data-stu-id="610a8-107">[in] The public key of the publisher of the referenced assembly.</span></span>  
  
 `cbPublicKeyOrToken`  
 <span data-ttu-id="610a8-108">in Dimensioni in byte di `pbPublicKeyOrToken` .</span><span class="sxs-lookup"><span data-stu-id="610a8-108">[in] The size in bytes of `pbPublicKeyOrToken`.</span></span>  
  
 `szName`  
 <span data-ttu-id="610a8-109">in Nome di testo leggibile dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="610a8-109">[in] The human-readable text name of the assembly.</span></span>  
  
 `pMetaData`  
 <span data-ttu-id="610a8-110">in Puntatore a un'istanza di ASSEMBLYMETADATA che contiene le informazioni relative alla versione, alla piattaforma e alle impostazioni locali per l'assembly.</span><span class="sxs-lookup"><span data-stu-id="610a8-110">[in] A pointer to an ASSEMBLYMETADATA instance that contains the version, platform, and locale information for the assembly.</span></span>  
  
 `pbHashValue`  
 <span data-ttu-id="610a8-111">in Puntatore ai dati hash associati all'assembly.</span><span class="sxs-lookup"><span data-stu-id="610a8-111">[in] A pointer to the hash data associated with the assembly.</span></span>  
  
 `cbHashValue`  
 <span data-ttu-id="610a8-112">in Dimensioni in byte di `pbHashValue` .</span><span class="sxs-lookup"><span data-stu-id="610a8-112">[in] The size in bytes of `pbHashValue`.</span></span>  
  
 `dwAssemblyRefFlags`  
 <span data-ttu-id="610a8-113">in Combinazione bit per bit di valori [AssemblyRefFlags](assemblyrefflags-enumeration.md) che specificano gli attributi dell'assembly a cui si fa riferimento.</span><span class="sxs-lookup"><span data-stu-id="610a8-113">[in] A bitwise combination of [AssemblyRefFlags](assemblyrefflags-enumeration.md) values that specify attributes of the referenced assembly.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="610a8-114">Commenti</span><span class="sxs-lookup"><span data-stu-id="610a8-114">Remarks</span></span>  
 <span data-ttu-id="610a8-115">Per creare una `AssemblyRef` struttura di metadati, usare il metodo [IMetaDataAssemblyEmit::D efineassemblyref](imetadataassemblyemit-defineassemblyref-method.md) .</span><span class="sxs-lookup"><span data-stu-id="610a8-115">To create an `AssemblyRef` metadata structure, use the [IMetaDataAssemblyEmit::DefineAssemblyRef](imetadataassemblyemit-defineassemblyref-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="610a8-116">Requisiti</span><span class="sxs-lookup"><span data-stu-id="610a8-116">Requirements</span></span>  
 <span data-ttu-id="610a8-117">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="610a8-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="610a8-118">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="610a8-118">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="610a8-119">**Libreria:** Usato come risorsa in MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="610a8-119">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="610a8-120">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="610a8-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="610a8-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="610a8-121">See also</span></span>

- [<span data-ttu-id="610a8-122">Interfaccia IMetaDataAssemblyEmit</span><span class="sxs-lookup"><span data-stu-id="610a8-122">IMetaDataAssemblyEmit Interface</span></span>](imetadataassemblyemit-interface.md)
