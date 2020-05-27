---
title: Metodo IMetaDataEmit::SetPinvokeMap
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetPinvokeMap
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetPinvokeMap
helpviewer_keywords:
- IMetaDataEmit::SetPinvokeMap method [.NET Framework metadata]
- SetPinvokeMap method [.NET Framework metadata]
ms.assetid: c6bfd574-1da3-4ba7-82f2-46ca5efcbaba
topic_type:
- apiref
ms.openlocfilehash: 0d34c7a2992a2779b96ec87f1a0175d8fcbce34a
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2020
ms.locfileid: "84007793"
---
# <a name="imetadataemitsetpinvokemap-method"></a><span data-ttu-id="18db1-102">Metodo IMetaDataEmit::SetPinvokeMap</span><span class="sxs-lookup"><span data-stu-id="18db1-102">IMetaDataEmit::SetPinvokeMap Method</span></span>
<span data-ttu-id="18db1-103">Imposta o modifica le funzionalità della firma PInvoke di un metodo, come definito da una chiamata precedente a [IMetaDataEmit::D efinepinvokemap](imetadataemit-definepinvokemap-method.md).</span><span class="sxs-lookup"><span data-stu-id="18db1-103">Sets or changes features of a method's PInvoke signature, as defined by a prior call to [IMetaDataEmit::DefinePinvokeMap](imetadataemit-definepinvokemap-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="18db1-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="18db1-104">Syntax</span></span>  
  
```cpp  
HRESULT SetPinvokeMap (
    [in]  mdToken      tk,
    [in]  DWORD        dwMappingFlags,  
    [in]  LPCWSTR      szImportName,
    [in]  mdModuleRef  mrImportDLL
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="18db1-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="18db1-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="18db1-106">in Oggetto `mdToken` a cui si applicano le informazioni di mapping.</span><span class="sxs-lookup"><span data-stu-id="18db1-106">[in] The `mdToken` to which mapping information applies.</span></span>  
  
 `dwMappingFlags`  
 <span data-ttu-id="18db1-107">in Flag utilizzati da PInvoke per eseguire il mapping.</span><span class="sxs-lookup"><span data-stu-id="18db1-107">[in] Flags used by PInvoke to do the mapping.</span></span> <span data-ttu-id="18db1-108">Si tratta di una maschera di maschera di `CorPinvokeMap` valori.</span><span class="sxs-lookup"><span data-stu-id="18db1-108">This is a bitmask of `CorPinvokeMap` values.</span></span>  
  
 `szImportName`  
 <span data-ttu-id="18db1-109">in Nome dell'esportazione di destinazione nella DLL nativa.</span><span class="sxs-lookup"><span data-stu-id="18db1-109">[in] The name of the target export in the native DLL.</span></span>  
  
 `mrImportDLL`  
 <span data-ttu-id="18db1-110">in `mdModuleRef`Token per la dll non gestita di destinazione.</span><span class="sxs-lookup"><span data-stu-id="18db1-110">[in] The `mdModuleRef` token for the target unmanaged DLL.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="18db1-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="18db1-111">Requirements</span></span>  
 <span data-ttu-id="18db1-112">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="18db1-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="18db1-113">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="18db1-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="18db1-114">**Libreria:** Usato come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="18db1-114">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="18db1-115">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="18db1-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="18db1-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="18db1-116">See also</span></span>

- [<span data-ttu-id="18db1-117">Interfaccia IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="18db1-117">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="18db1-118">Interfaccia IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="18db1-118">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
