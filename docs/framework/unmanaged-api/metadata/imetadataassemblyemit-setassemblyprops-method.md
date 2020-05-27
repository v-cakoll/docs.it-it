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
ms.openlocfilehash: 7c6adcbcfe64f63048078b4ccba6727a58531033
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008105"
---
# <a name="imetadataassemblyemitsetassemblyprops-method"></a><span data-ttu-id="46625-102">Metodo IMetaDataAssemblyEmit::SetAssemblyProps</span><span class="sxs-lookup"><span data-stu-id="46625-102">IMetaDataAssemblyEmit::SetAssemblyProps Method</span></span>
<span data-ttu-id="46625-103">Modifica la struttura dei metadati `Assembly` specificata.</span><span class="sxs-lookup"><span data-stu-id="46625-103">Modifies the specified `Assembly` metadata structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="46625-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="46625-104">Syntax</span></span>  
  
```cpp  
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
  
## <a name="parameters"></a><span data-ttu-id="46625-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="46625-105">Parameters</span></span>  
 `pma`  
 <span data-ttu-id="46625-106">in Token di metadati che specifica la `Assembly` struttura dei metadati da modificare.</span><span class="sxs-lookup"><span data-stu-id="46625-106">[in] The metadata token that specifies the `Assembly` metadata structure to be modified.</span></span>  
  
 `pbPublicKey`  
 <span data-ttu-id="46625-107">in Puntatore alla chiave pubblica del server di pubblicazione dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="46625-107">[in] A pointer to the public key of the publisher of the assembly.</span></span>  
  
 `cbPublicKey`  
 <span data-ttu-id="46625-108">in Dimensioni in byte di `pbPublicKey` .</span><span class="sxs-lookup"><span data-stu-id="46625-108">[in] The size in bytes of `pbPublicKey`.</span></span>  
  
 `ulHashAlgId`  
 <span data-ttu-id="46625-109">in Identificatore dell'algoritmo hash utilizzato per eseguire l'hashing dei file di assembly.</span><span class="sxs-lookup"><span data-stu-id="46625-109">[in] The identifier for the hash algorithm used to hash the assembly files.</span></span>  
  
 `szName`  
 <span data-ttu-id="46625-110">in Nome di testo leggibile dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="46625-110">[in] The human-readable text name of the assembly.</span></span>  
  
 `pMetaData`  
 <span data-ttu-id="46625-111">in Puntatore a ASSEMBLYMETADATA che contiene le informazioni sulla versione, sulla piattaforma e sulle impostazioni locali per l'assembly.</span><span class="sxs-lookup"><span data-stu-id="46625-111">[in] A pointer to the ASSEMBLYMETADATA that contains version, platform, and locale information for the assembly.</span></span>  
  
 `dwAssemblyFlags`  
 <span data-ttu-id="46625-112">in Combinazione bit per bit di valori [AssemblyFlags](assemblyflags-enumeration.md) che specificano diversi attributi dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="46625-112">[in] A bitwise combination of [AssemblyFlags](assemblyflags-enumeration.md) values that specify various attributes of the assembly.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="46625-113">Commenti</span><span class="sxs-lookup"><span data-stu-id="46625-113">Remarks</span></span>  
 <span data-ttu-id="46625-114">Per creare una `Assembly` struttura di metadati, usare il metodo [IMetaDataAssemblyEmit::D efineassembly](imetadataassemblyemit-defineassembly-method.md) .</span><span class="sxs-lookup"><span data-stu-id="46625-114">To create an `Assembly` metadata structure, use the [IMetaDataAssemblyEmit::DefineAssembly](imetadataassemblyemit-defineassembly-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="46625-115">Requisiti</span><span class="sxs-lookup"><span data-stu-id="46625-115">Requirements</span></span>  
 <span data-ttu-id="46625-116">**Piattaforma:** Vedere [requisiti di sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="46625-116">**Platform:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="46625-117">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="46625-117">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="46625-118">**Libreria:** Usato come risorsa in MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="46625-118">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="46625-119">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="46625-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="46625-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="46625-120">See also</span></span>

- [<span data-ttu-id="46625-121">Interfaccia IMetaDataAssemblyEmit</span><span class="sxs-lookup"><span data-stu-id="46625-121">IMetaDataAssemblyEmit Interface</span></span>](imetadataassemblyemit-interface.md)
