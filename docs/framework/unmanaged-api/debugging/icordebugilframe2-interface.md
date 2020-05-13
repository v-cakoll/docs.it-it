---
title: Interfaccia ICorDebugILFrame2
ms.date: 03/30/2017
api_name:
- ICorDebugILFrame2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugILFrame2
helpviewer_keywords:
- ICorDebugILFrame2 interface [.NET Framework debugging]
ms.assetid: f94b9d53-d8f8-4424-a95e-53a1bfd26e4a
topic_type:
- apiref
ms.openlocfilehash: 2e0f284625e99215900c6aaab94e4eae611787ed
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2020
ms.locfileid: "83212100"
---
# <a name="icordebugilframe2-interface"></a><span data-ttu-id="a9e3f-102">Interfaccia ICorDebugILFrame2</span><span class="sxs-lookup"><span data-stu-id="a9e3f-102">ICorDebugILFrame2 Interface</span></span>

<span data-ttu-id="a9e3f-103">Estensione logica dell'interfaccia ICorDebugILFrame.</span><span class="sxs-lookup"><span data-stu-id="a9e3f-103">A logical extension of the ICorDebugILFrame interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a9e3f-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="a9e3f-104">Methods</span></span>  
  
|<span data-ttu-id="a9e3f-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="a9e3f-105">Method</span></span>|<span data-ttu-id="a9e3f-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a9e3f-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a9e3f-107">Metodo EnumerateTypeParameters</span><span class="sxs-lookup"><span data-stu-id="a9e3f-107">EnumerateTypeParameters Method</span></span>](icordebugilframe2-enumeratetypeparameters-method.md)|<span data-ttu-id="a9e3f-108">Ottiene un oggetto ICorDebugTypeEnum che contiene i <xref:System.Type> parametri in questo frame.</span><span class="sxs-lookup"><span data-stu-id="a9e3f-108">Gets an ICorDebugTypeEnum object that contains the <xref:System.Type> parameters in this frame.</span></span>|  
|[<span data-ttu-id="a9e3f-109">Metodo RemapFunction</span><span class="sxs-lookup"><span data-stu-id="a9e3f-109">RemapFunction Method</span></span>](icordebugilframe2-remapfunction-method.md)|<span data-ttu-id="a9e3f-110">Consente di rimappare una funzione modificata specificando il nuovo offset MSIL.</span><span class="sxs-lookup"><span data-stu-id="a9e3f-110">Remaps an edited function by specifying the new MSIL offset.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a9e3f-111">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="a9e3f-111">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a9e3f-112">Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.</span><span class="sxs-lookup"><span data-stu-id="a9e3f-112">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a9e3f-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="a9e3f-113">Requirements</span></span>  
 <span data-ttu-id="a9e3f-114">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a9e3f-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a9e3f-115">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a9e3f-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a9e3f-116">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a9e3f-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a9e3f-117">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a9e3f-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a9e3f-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a9e3f-118">See also</span></span>

- [<span data-ttu-id="a9e3f-119">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="a9e3f-119">Debugging Interfaces</span></span>](debugging-interfaces.md)
