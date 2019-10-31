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
ms.openlocfilehash: fb96949e22b4edfc0e64780a54bb38da44eb8369
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73129553"
---
# <a name="icordebugmodulegetmetadatainterface-method"></a><span data-ttu-id="e766c-102">Metodo ICorDebugModule::GetMetaDataInterface</span><span class="sxs-lookup"><span data-stu-id="e766c-102">ICorDebugModule::GetMetaDataInterface Method</span></span>
<span data-ttu-id="e766c-103">Ottiene un oggetto di interfaccia di metadati che può essere utilizzato per esaminare i metadati per il modulo.</span><span class="sxs-lookup"><span data-stu-id="e766c-103">Gets a metadata interface object that can be used to examine the metadata for the module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e766c-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e766c-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMetaDataInterface (  
    [in] REFIID      riid,  
    [out] IUnknown **ppObj  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e766c-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="e766c-105">Parameters</span></span>  
 `riid`  
 <span data-ttu-id="e766c-106">in ID di riferimento che specifica l'interfaccia dei metadati.</span><span class="sxs-lookup"><span data-stu-id="e766c-106">[in] The reference ID that specifies the metadata interface.</span></span>  
  
 `ppObj`  
 <span data-ttu-id="e766c-107">out Puntatore all'indirizzo di un `T:IUnknown` oggetto che corrisponde a una delle interfacce di [metadati](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md).</span><span class="sxs-lookup"><span data-stu-id="e766c-107">[out] A pointer to the address of an `T:IUnknown` object that is one of the [metadata interfaces](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e766c-108">Note</span><span class="sxs-lookup"><span data-stu-id="e766c-108">Remarks</span></span>  
 <span data-ttu-id="e766c-109">Il debugger può utilizzare il metodo `GetMetaDataInterface` per creare una copia dei metadati originali per un modulo, operazione che deve essere eseguita per modificare il modulo.</span><span class="sxs-lookup"><span data-stu-id="e766c-109">The debugger can use the `GetMetaDataInterface` method to make a copy of the original metadata for a module, which it must do in order to edit that module.</span></span> <span data-ttu-id="e766c-110">Il debugger chiama `GetMetaDataInterface` per ottenere un oggetto interfaccia [IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md) per il modulo, quindi chiama [IMetaDataEmit:: SaveToMemory](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-savetomemory-method.md) per salvare una copia dei metadati del modulo in memoria.</span><span class="sxs-lookup"><span data-stu-id="e766c-110">The debugger calls `GetMetaDataInterface` to get an [IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md) interface object for the module, then calls [IMetaDataEmit::SaveToMemory](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-savetomemory-method.md) to save a copy of the module's metadata to memory.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e766c-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="e766c-111">Requirements</span></span>  
 <span data-ttu-id="e766c-112">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e766c-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e766c-113">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e766c-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e766c-114">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e766c-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e766c-115">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e766c-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e766c-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e766c-116">See also</span></span>

- [<span data-ttu-id="e766c-117">Metadati</span><span class="sxs-lookup"><span data-stu-id="e766c-117">Metadata</span></span>](../../../../docs/framework/unmanaged-api/metadata/index.md)
