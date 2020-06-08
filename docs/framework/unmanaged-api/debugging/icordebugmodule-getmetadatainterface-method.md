---
title: Metodo ICorDebugModule::GetMetaDataInterface
ms.date: 03/30/2017
api_name:
- ICorDebugModule.GetMetaDataInterface
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule::GetMetaDataInterface
helpviewer_keywords:
- ICorDebugModule::GetMetaDatainterface method [.NET Framework debugging]
- GetMetaDatainterface method [.NET Framework debugging]
ms.assetid: 30d906f2-cf35-4fa9-9d4c-0c31b58c9f3a
topic_type:
- apiref
ms.openlocfilehash: f5d0dd7a99087b21a5f827e4dce0f6342ae7b25a
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84501768"
---
# <a name="icordebugmodulegetmetadatainterface-method"></a><span data-ttu-id="e92a3-102">Metodo ICorDebugModule::GetMetaDataInterface</span><span class="sxs-lookup"><span data-stu-id="e92a3-102">ICorDebugModule::GetMetaDataInterface Method</span></span>
<span data-ttu-id="e92a3-103">Ottiene un oggetto di interfaccia di metadati che può essere utilizzato per esaminare i metadati per il modulo.</span><span class="sxs-lookup"><span data-stu-id="e92a3-103">Gets a metadata interface object that can be used to examine the metadata for the module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e92a3-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e92a3-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMetaDataInterface (  
    [in] REFIID      riid,  
    [out] IUnknown **ppObj  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e92a3-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="e92a3-105">Parameters</span></span>  
 `riid`  
 <span data-ttu-id="e92a3-106">in ID di riferimento che specifica l'interfaccia dei metadati.</span><span class="sxs-lookup"><span data-stu-id="e92a3-106">[in] The reference ID that specifies the metadata interface.</span></span>  
  
 `ppObj`  
 <span data-ttu-id="e92a3-107">out Puntatore all'indirizzo di un `T:IUnknown` oggetto che corrisponde a una delle interfacce di [metadati](../metadata/metadata-interfaces.md).</span><span class="sxs-lookup"><span data-stu-id="e92a3-107">[out] A pointer to the address of an `T:IUnknown` object that is one of the [metadata interfaces](../metadata/metadata-interfaces.md).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e92a3-108">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="e92a3-108">Remarks</span></span>  
 <span data-ttu-id="e92a3-109">Il debugger può usare il `GetMetaDataInterface` metodo per creare una copia dei metadati originali per un modulo, che deve eseguire per modificare il modulo.</span><span class="sxs-lookup"><span data-stu-id="e92a3-109">The debugger can use the `GetMetaDataInterface` method to make a copy of the original metadata for a module, which it must do in order to edit that module.</span></span> <span data-ttu-id="e92a3-110">Il debugger chiama `GetMetaDataInterface` per ottenere un oggetto di interfaccia [IMetaDataEmit](../metadata/imetadataemit-interface.md) per il modulo, quindi chiama [IMetaDataEmit:: SaveToMemory](../metadata/imetadataemit-savetomemory-method.md) per salvare una copia dei metadati del modulo in memoria.</span><span class="sxs-lookup"><span data-stu-id="e92a3-110">The debugger calls `GetMetaDataInterface` to get an [IMetaDataEmit](../metadata/imetadataemit-interface.md) interface object for the module, then calls [IMetaDataEmit::SaveToMemory](../metadata/imetadataemit-savetomemory-method.md) to save a copy of the module's metadata to memory.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e92a3-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="e92a3-111">Requirements</span></span>  
 <span data-ttu-id="e92a3-112">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e92a3-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e92a3-113">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e92a3-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e92a3-114">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e92a3-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e92a3-115">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e92a3-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e92a3-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e92a3-116">See also</span></span>

- [<span data-ttu-id="e92a3-117">Metadati</span><span class="sxs-lookup"><span data-stu-id="e92a3-117">Metadata</span></span>](../metadata/index.md)
