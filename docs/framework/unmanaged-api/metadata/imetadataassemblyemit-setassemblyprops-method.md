---
title: Metodo IMetaDataAssemblyEmit::SetAssemblyProps
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyEmit.SetAssemblyProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyEmit::SetAssemblyProps
helpviewer_keywords:
- SetAssemblyProps method [.NET Framework metadata]
- IMetaDataAssemblyEmit::SetAssemblyProps method [.NET Framework metadata]
ms.assetid: 91b633d7-9e75-43c3-a8d2-2144984e5f9e
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 6f8132296035e9ddcdcad76d93ed05358beb0b81
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33448233"
---
# <a name="imetadataassemblyemitsetassemblyprops-method"></a><span data-ttu-id="a92ab-102">Metodo IMetaDataAssemblyEmit::SetAssemblyProps</span><span class="sxs-lookup"><span data-stu-id="a92ab-102">IMetaDataAssemblyEmit::SetAssemblyProps Method</span></span>
<span data-ttu-id="a92ab-103">Modifica la struttura dei metadati `Assembly` specificata.</span><span class="sxs-lookup"><span data-stu-id="a92ab-103">Modifies the specified `Assembly` metadata structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a92ab-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a92ab-104">Syntax</span></span>  
  
```  
HRESULT SetAssemblyProps (  
    [in] mdAssembly               pma,  
    [in] const void               *pbPublicKey,  
    [in] ULONG                    cbPublicKey,  
    [in] ULONG                    ulHashAlgId,  
    [in] LPCWSTR                  szName,  
    [in] const ASSEMBLYMETADATA   *pMetaData,  
    [in] DWORD                    dwAssemblyFlags  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a92ab-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="a92ab-105">Parameters</span></span>  
 `pma`  
 <span data-ttu-id="a92ab-106">[in] Il token di metadati che specifica il `Assembly` struttura dei metadati da modificare.</span><span class="sxs-lookup"><span data-stu-id="a92ab-106">[in] The metadata token that specifies the `Assembly` metadata structure to be modified.</span></span>  
  
 `pbPublicKey`  
 <span data-ttu-id="a92ab-107">[in] Puntatore alla chiave pubblica del server di pubblicazione dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="a92ab-107">[in] A pointer to the public key of the publisher of the assembly.</span></span>  
  
 `cbPublicKey`  
 <span data-ttu-id="a92ab-108">[in] Le dimensioni in byte di `pbPublicKey`.</span><span class="sxs-lookup"><span data-stu-id="a92ab-108">[in] The size in bytes of `pbPublicKey`.</span></span>  
  
 `ulHashAlgId`  
 <span data-ttu-id="a92ab-109">[in] Identificatore per l'algoritmo hash utilizzato per i file di assembly di hash.</span><span class="sxs-lookup"><span data-stu-id="a92ab-109">[in] The identifier for the hash algorithm used to hash the assembly files.</span></span>  
  
 `szName`  
 <span data-ttu-id="a92ab-110">[in] Il nome di un testo leggibile dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="a92ab-110">[in] The human-readable text name of the assembly.</span></span>  
  
 `pMetaData`  
 <span data-ttu-id="a92ab-111">[in] Puntatore a ASSEMBLYMETADATA che contiene informazioni sulla versione, piattaforma e delle impostazioni locali per l'assembly.</span><span class="sxs-lookup"><span data-stu-id="a92ab-111">[in] A pointer to the ASSEMBLYMETADATA that contains version, platform, and locale information for the assembly.</span></span>  
  
 `dwAssemblyFlags`  
 <span data-ttu-id="a92ab-112">[in] Combinazione bit per bit di [AssemblyFlags](../../../../docs/framework/unmanaged-api/metadata/assemblyflags-enumeration.md) valori che specificano vari attributi dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="a92ab-112">[in] A bitwise combination of [AssemblyFlags](../../../../docs/framework/unmanaged-api/metadata/assemblyflags-enumeration.md) values that specify various attributes of the assembly.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a92ab-113">Note</span><span class="sxs-lookup"><span data-stu-id="a92ab-113">Remarks</span></span>  
 <span data-ttu-id="a92ab-114">Per creare un `Assembly` struttura dei metadati, usare il [IMetaDataAssemblyEmit:: DefineAssembly](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineassembly-method.md) metodo.</span><span class="sxs-lookup"><span data-stu-id="a92ab-114">To create an `Assembly` metadata structure, use the [IMetaDataAssemblyEmit::DefineAssembly](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineassembly-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a92ab-115">Requisiti</span><span class="sxs-lookup"><span data-stu-id="a92ab-115">Requirements</span></span>  
 <span data-ttu-id="a92ab-116">**Piattaforma:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a92ab-116">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a92ab-117">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="a92ab-117">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="a92ab-118">**Libreria:** usata come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="a92ab-118">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="a92ab-119">**Versioni di .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a92ab-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a92ab-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a92ab-120">See Also</span></span>  
 [<span data-ttu-id="a92ab-121">Interfaccia IMetaDataAssemblyEmit</span><span class="sxs-lookup"><span data-stu-id="a92ab-121">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
