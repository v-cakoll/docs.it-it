---
title: Interfaccia ICorDebugType2
ms.date: 03/30/2017
api_name:
- ICorDebugType2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugType2
helpviewer_keywords:
- ICorDebugType2 interface
ms.assetid: 376fb03f-f1ef-4107-baa4-4d9d55884862
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 878941f7af71fa5e3de8e38c4a68a66cb964983d
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59223160"
---
# <a name="icordebugtype2-interface"></a><span data-ttu-id="35520-102">Interfaccia ICorDebugType2</span><span class="sxs-lookup"><span data-stu-id="35520-102">ICorDebugType2 Interface</span></span>
<span data-ttu-id="35520-103">Estende l'interfaccia ICorDebugType per recuperare l'identificatore del tipo di un tipo di base o complesso (tipo definito dall'utente).</span><span class="sxs-lookup"><span data-stu-id="35520-103">Extends the ICorDebugType interface to retrieve the type identifier  of a base type or complex (user-defined) type.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="35520-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="35520-104">Methods</span></span>  
  
|<span data-ttu-id="35520-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="35520-105">Method</span></span>||  
|------------|-|  
|[<span data-ttu-id="35520-106">Metodo GetTypeID</span><span class="sxs-lookup"><span data-stu-id="35520-106">GetTypeID Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugtype2-gettypeid-method.md)|<span data-ttu-id="35520-107">Ottiene un [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) per questo tipo.</span><span class="sxs-lookup"><span data-stu-id="35520-107">Gets a [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) for this type.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="35520-108">Note</span><span class="sxs-lookup"><span data-stu-id="35520-108">Remarks</span></span>  
 <span data-ttu-id="35520-109">Questa interfaccia è un'estensione logica dell'interfaccia ICorDebugType.</span><span class="sxs-lookup"><span data-stu-id="35520-109">This interface is a logical extension of the ICorDebugType interface.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="35520-110">Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.</span><span class="sxs-lookup"><span data-stu-id="35520-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="example"></a><span data-ttu-id="35520-111">Esempio</span><span class="sxs-lookup"><span data-stu-id="35520-111">Example</span></span>  
 <span data-ttu-id="35520-112">Il frammento di codice seguente viene illustrato l'utilizzo dei [ICorDebugType2::GetTypeID](../../../../docs/framework/unmanaged-api/debugging/icordebugtype2-gettypeid-method.md) (metodo).</span><span class="sxs-lookup"><span data-stu-id="35520-112">The following code fragment illustrates the use of the [ICorDebugType2::GetTypeID](../../../../docs/framework/unmanaged-api/debugging/icordebugtype2-gettypeid-method.md) method.</span></span>  
  
```  
// (error checking omitted for brevity)  
// given an ICorDebugType *pType  
  
ICorDebugType2 *pType2 = NULL;  
pType->QueryInterface(IID_ICorDebugType2, &pType);  
  
COR_TYPEID id;  
pType2->GetTypeID(&id);  
  
// now we can use existing APIs to get information about this COR_TYPEID  
```  
  
## <a name="requirements"></a><span data-ttu-id="35520-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="35520-113">Requirements</span></span>  
 <span data-ttu-id="35520-114">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="35520-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="35520-115">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="35520-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="35520-116">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="35520-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="35520-117">**Versioni di .NET Framework:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="35520-117">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="35520-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="35520-118">See also</span></span>

- [<span data-ttu-id="35520-119">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="35520-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
