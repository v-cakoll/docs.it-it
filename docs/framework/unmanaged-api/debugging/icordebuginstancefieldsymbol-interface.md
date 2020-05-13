---
title: Interfaccia ICorDebugInstanceFieldSymbol
ms.date: 03/30/2017
ms.assetid: a4a8f259-b83a-4425-ae8b-72b067dbc0d9
ms.openlocfilehash: 092f2a8acdffa9f91176bdf0ca10b8db9cff6d37
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2020
ms.locfileid: "83209929"
---
# <a name="icordebuginstancefieldsymbol-interface"></a><span data-ttu-id="afda8-102">Interfaccia ICorDebugInstanceFieldSymbol</span><span class="sxs-lookup"><span data-stu-id="afda8-102">ICorDebugInstanceFieldSymbol Interface</span></span>
<span data-ttu-id="afda8-103">Rappresenta le informazioni relative al simbolo di debug per un campo di istanza.</span><span class="sxs-lookup"><span data-stu-id="afda8-103">Represents the debug symbol information for an instance field.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="afda8-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="afda8-104">Methods</span></span>  
  
|<span data-ttu-id="afda8-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="afda8-105">Method</span></span>|<span data-ttu-id="afda8-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="afda8-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="afda8-107">Metodo GetName</span><span class="sxs-lookup"><span data-stu-id="afda8-107">GetName Method</span></span>](icordebuginstancefieldsymbol-getname-method.md)|<span data-ttu-id="afda8-108">Ottiene il nome del campo di istanza.</span><span class="sxs-lookup"><span data-stu-id="afda8-108">Gets the name of the instance field.</span></span>|  
|[<span data-ttu-id="afda8-109">Metodo GetOffset</span><span class="sxs-lookup"><span data-stu-id="afda8-109">GetOffset Method</span></span>](icordebuginstancefieldsymbol-getoffset-method.md)|<span data-ttu-id="afda8-110">Ottiene l'offset, in byte, di questo campo di istanza nella relativa classe padre.</span><span class="sxs-lookup"><span data-stu-id="afda8-110">Gets the offset in bytes of this instance field in its parent class.</span></span>|  
|[<span data-ttu-id="afda8-111">Metodo GetSize</span><span class="sxs-lookup"><span data-stu-id="afda8-111">GetSize Method</span></span>](icordebuginstancefieldsymbol-getsize-method.md)|<span data-ttu-id="afda8-112">Ottiene le dimensioni, in byte, del campo di istanza.</span><span class="sxs-lookup"><span data-stu-id="afda8-112">Gets the size in bytes of the instance field.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="afda8-113">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="afda8-113">Remarks</span></span>  
 <span data-ttu-id="afda8-114">L'interfaccia `ICorDebugInstanceFieldSymbol` viene usata per recuperare le informazioni sul simbolo di debug per un campo di istanza.</span><span class="sxs-lookup"><span data-stu-id="afda8-114">The `ICorDebugInstanceFieldSymbol` interface is used to retrieve the debug symbol information for an instance field.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="afda8-115">Questa interfaccia è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="afda8-115">This interface is available with .NET Native only.</span></span> <span data-ttu-id="afda8-116">Se questa interfaccia viene implementata per scenari ICorDebug al di fuori di .NET Native, sarà ignorata da Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="afda8-116">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="afda8-117">Requisiti</span><span class="sxs-lookup"><span data-stu-id="afda8-117">Requirements</span></span>  
 <span data-ttu-id="afda8-118">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="afda8-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="afda8-119">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="afda8-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="afda8-120">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="afda8-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="afda8-121">**Versioni .NET Framework:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="afda8-121">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="afda8-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="afda8-122">See also</span></span>

- [<span data-ttu-id="afda8-123">Interfaccia ICorDebugStaticFieldSymbol</span><span class="sxs-lookup"><span data-stu-id="afda8-123">ICorDebugStaticFieldSymbol Interface</span></span>](icordebugstaticfieldsymbol-interface.md)
- [<span data-ttu-id="afda8-124">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="afda8-124">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="afda8-125">Debug</span><span class="sxs-lookup"><span data-stu-id="afda8-125">Debugging</span></span>](index.md)
