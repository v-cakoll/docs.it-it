---
title: Metodo IMetaDataAssemblyEmit::DefineAssembly
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyEmit.DefineAssembly
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyEmit::DefineAssembly
helpviewer_keywords:
- IMetaDataAssemblyEmit::DefineAssembly method [.NET Framework metadata]
- DefineAssembly method [.NET Framework metadata]
ms.assetid: a0637d66-74bf-4f2d-8137-9ff838bccece
topic_type:
- apiref
ms.openlocfilehash: 17c91200730431c4c6e230b8c1561ce7c4863868
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008183"
---
# <a name="imetadataassemblyemitdefineassembly-method"></a><span data-ttu-id="034c0-102">Metodo IMetaDataAssemblyEmit::DefineAssembly</span><span class="sxs-lookup"><span data-stu-id="034c0-102">IMetaDataAssemblyEmit::DefineAssembly Method</span></span>
<span data-ttu-id="034c0-103">Crea una `Assembly` struttura contenente i metadati per l'assembly specificato e restituisce il token di metadati associato.</span><span class="sxs-lookup"><span data-stu-id="034c0-103">Creates an `Assembly` structure containing metadata for the specified assembly and returns the associated metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="034c0-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="034c0-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineAssembly (  
    [in]  void                 *pbPublicKey,  
    [in]  ULONG                cbPublicKey,  
    [in]  ULONG                uHashAlgId,  
    [in]  LPCWSTR              szName,
    [in]  ASSEMBLYMETADATA     *pMetaData,  
    [in]  DWORD                dwAssemblyFlags,  
    [out] mdAssembly           *pmda  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="034c0-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="034c0-105">Parameters</span></span>  
 `pbPublicKey`  
 <span data-ttu-id="034c0-106">in Chiave pubblica che identifica il server di pubblicazione dell'assembly o NULL se l'assembly non ha un nome sicuro.</span><span class="sxs-lookup"><span data-stu-id="034c0-106">[in] The public key that identifies the publisher of the assembly, or NULL if the assembly is not strongly named.</span></span>  
  
 `cbPublicKey`  
 <span data-ttu-id="034c0-107">in Dimensioni in byte di `pbPublicKey` .</span><span class="sxs-lookup"><span data-stu-id="034c0-107">[in] The size in bytes of `pbPublicKey`.</span></span>  
  
 `uHashAlgId`  
 <span data-ttu-id="034c0-108">in Identificatore dell'algoritmo hash da usare per crittografare i file nell'assembly o NULL per specificare l'algoritmo SHA-1.</span><span class="sxs-lookup"><span data-stu-id="034c0-108">[in] The identifier of the hashing algorithm to use to encrypt the files in the assembly, or NULL to specify the SHA-1 algorithm.</span></span>  
  
 `szName`  
 <span data-ttu-id="034c0-109">in Nome di testo leggibile dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="034c0-109">[in] The human-readable text name of the assembly.</span></span> <span data-ttu-id="034c0-110">Questo valore non deve superare i 1024 caratteri.</span><span class="sxs-lookup"><span data-stu-id="034c0-110">This value must not exceed 1024 characters.</span></span>  
  
 `pMetaData`  
 <span data-ttu-id="034c0-111">in Puntatore a un'istanza di ASSEMBLYMETADATA che contiene le informazioni relative alla versione, alla piattaforma e alle impostazioni locali per l'assembly.</span><span class="sxs-lookup"><span data-stu-id="034c0-111">[in] A pointer to an ASSEMBLYMETADATA instance that contains the version, platform, and locale information for the assembly.</span></span>  
  
 `dwAssemblyFlags`  
 <span data-ttu-id="034c0-112">in Combinazione di valori [CorAssemblyFlags](corassemblyflags-enumeration.md) che descrivono le funzionalità dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="034c0-112">[in] A combination of [CorAssemblyFlags](corassemblyflags-enumeration.md) values that describe features of the assembly.</span></span>  
  
 `pmda`  
 <span data-ttu-id="034c0-113">out Puntatore al token di metadati.</span><span class="sxs-lookup"><span data-stu-id="034c0-113">[out] A pointer to the metadata token.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="034c0-114">Commenti</span><span class="sxs-lookup"><span data-stu-id="034c0-114">Remarks</span></span>  
 <span data-ttu-id="034c0-115">`Assembly`All'interno di un manifesto è possibile definire una sola struttura di metadati.</span><span class="sxs-lookup"><span data-stu-id="034c0-115">Only one `Assembly` metadata structure can be defined within a manifest.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="034c0-116">Requisiti</span><span class="sxs-lookup"><span data-stu-id="034c0-116">Requirements</span></span>  
 <span data-ttu-id="034c0-117">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="034c0-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="034c0-118">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="034c0-118">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="034c0-119">**Libreria:** Incluso come risorsa in MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="034c0-119">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="034c0-120">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="034c0-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="034c0-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="034c0-121">See also</span></span>

- [<span data-ttu-id="034c0-122">Interfaccia IMetaDataAssemblyEmit</span><span class="sxs-lookup"><span data-stu-id="034c0-122">IMetaDataAssemblyEmit Interface</span></span>](imetadataassemblyemit-interface.md)
