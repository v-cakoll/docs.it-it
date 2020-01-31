---
title: Interfaccia ICorDebugVariableSymbol
ms.date: 03/30/2017
ms.assetid: 0e58b85e-69bd-41ff-bedb-8cdc8be6a7a2
ms.openlocfilehash: 9d17bc92dcae9e906dfe18d7665fbf489d278234
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790866"
---
# <a name="icordebugvariablesymbol-interface"></a><span data-ttu-id="72dac-102">Interfaccia ICorDebugVariableSymbol</span><span class="sxs-lookup"><span data-stu-id="72dac-102">ICorDebugVariableSymbol Interface</span></span>
<span data-ttu-id="72dac-103">Recupera le informazioni relative al simbolo di debug per una variabile.</span><span class="sxs-lookup"><span data-stu-id="72dac-103">Retrieves the debug symbol information for a variable.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="72dac-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="72dac-104">Methods</span></span>  
  
|<span data-ttu-id="72dac-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="72dac-105">Method</span></span>|<span data-ttu-id="72dac-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="72dac-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="72dac-107">Metodo GetName</span><span class="sxs-lookup"><span data-stu-id="72dac-107">GetName Method</span></span>](icordebugvariablesymbol-getname-method.md)|<span data-ttu-id="72dac-108">Ottiene il nome di una variabile.</span><span class="sxs-lookup"><span data-stu-id="72dac-108">Gets the name of a variable.</span></span>|  
|[<span data-ttu-id="72dac-109">Metodo GetSize</span><span class="sxs-lookup"><span data-stu-id="72dac-109">GetSize Method</span></span>](icordebugvariablesymbol-getsize-method.md)|<span data-ttu-id="72dac-110">Ottiene le dimensioni di una variabile in byte.</span><span class="sxs-lookup"><span data-stu-id="72dac-110">Gets the size of a variable in bytes.</span></span>|  
|[<span data-ttu-id="72dac-111">Metodo GetSlotIndex</span><span class="sxs-lookup"><span data-stu-id="72dac-111">GetSlotIndex Method</span></span>](icordebugvariablesymbol-getslotindex-method.md)|<span data-ttu-id="72dac-112">Ottiene l'indice dello slot gestito di una variabile locale.</span><span class="sxs-lookup"><span data-stu-id="72dac-112">Gets the managed slot index of a local variable.</span></span>|  
|[<span data-ttu-id="72dac-113">Metodo GetValue</span><span class="sxs-lookup"><span data-stu-id="72dac-113">GetValue Method</span></span>](icordebugvariablesymbol-getvalue-method.md)|<span data-ttu-id="72dac-114">Ottiene il valore di una variabile come matrice di byte.</span><span class="sxs-lookup"><span data-stu-id="72dac-114">Gets the value of a variable as a byte array.</span></span>|  
|[<span data-ttu-id="72dac-115">Metodo SetValue</span><span class="sxs-lookup"><span data-stu-id="72dac-115">SetValue Method</span></span>](icordebugvariablesymbol-setvalue-method.md)|<span data-ttu-id="72dac-116">Assegna il valore di una matrice di byte a una variabile.</span><span class="sxs-lookup"><span data-stu-id="72dac-116">Assigns the value of a byte array to a variable.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="72dac-117">Note</span><span class="sxs-lookup"><span data-stu-id="72dac-117">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="72dac-118">Questa interfaccia è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="72dac-118">This interface is available with .NET Native only.</span></span> <span data-ttu-id="72dac-119">Se questa interfaccia viene implementata per scenari ICorDebug al di fuori di .NET Native, sarà ignorata da Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="72dac-119">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="72dac-120">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="72dac-120">Requirements</span></span>  
 <span data-ttu-id="72dac-121">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="72dac-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="72dac-122">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="72dac-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="72dac-123">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="72dac-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="72dac-124">**Versioni .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="72dac-124">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="72dac-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="72dac-125">See also</span></span>

- [<span data-ttu-id="72dac-126">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="72dac-126">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="72dac-127">Debug</span><span class="sxs-lookup"><span data-stu-id="72dac-127">Debugging</span></span>](index.md)
