---
title: Interfaccia ICorDebugMergedAssemblyRecord
ms.date: 03/30/2017
ms.assetid: fe280b11-9479-4e34-a07c-0d1ea8088422
ms.openlocfilehash: 721f6c1cf468b3b518d2ea213588ae2410249690
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2020
ms.locfileid: "83208720"
---
# <a name="icordebugmergedassemblyrecord-interface"></a><span data-ttu-id="c39fa-102">Interfaccia ICorDebugMergedAssemblyRecord</span><span class="sxs-lookup"><span data-stu-id="c39fa-102">ICorDebugMergedAssemblyRecord Interface</span></span>
<span data-ttu-id="c39fa-103">Fornisce informazioni su un assembly unito.</span><span class="sxs-lookup"><span data-stu-id="c39fa-103">Provides information about a merged assembly.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="c39fa-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="c39fa-104">Methods</span></span>  
  
|<span data-ttu-id="c39fa-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="c39fa-105">Method</span></span>|<span data-ttu-id="c39fa-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c39fa-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="c39fa-107">Metodo GetCulture</span><span class="sxs-lookup"><span data-stu-id="c39fa-107">GetCulture Method</span></span>](icordebugmergedassemblyrecord-getculture-method.md)|<span data-ttu-id="c39fa-108">Ottiene la stringa del nome delle impostazioni cultura dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="c39fa-108">Gets the culture name string of the assembly.</span></span>|  
|[<span data-ttu-id="c39fa-109">Metodo GetIndex</span><span class="sxs-lookup"><span data-stu-id="c39fa-109">GetIndex Method</span></span>](icordebugmergedassemblyrecord-getindex-method.md)|<span data-ttu-id="c39fa-110">Ottiene l'indice del prefisso dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="c39fa-110">Gets the assembly's prefix index.</span></span>|  
|[<span data-ttu-id="c39fa-111">Metodo GetPublicKey</span><span class="sxs-lookup"><span data-stu-id="c39fa-111">GetPublicKey Method</span></span>](icordebugmergedassemblyrecord-getpublickey-method.md)|<span data-ttu-id="c39fa-112">Ottiene la chiave pubblica dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="c39fa-112">Gets the assembly's public key.</span></span>|  
|[<span data-ttu-id="c39fa-113">Metodo GetPublicKeyToken</span><span class="sxs-lookup"><span data-stu-id="c39fa-113">GetPublicKeyToken Method</span></span>](icordebugmergedassemblyrecord-getpublickeytoken-method.md)|<span data-ttu-id="c39fa-114">Ottiene il token di chiave pubblica dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="c39fa-114">Gets the assembly's public key token.</span></span>|  
|[<span data-ttu-id="c39fa-115">Metodo GetSimpleName</span><span class="sxs-lookup"><span data-stu-id="c39fa-115">GetSimpleName Method</span></span>](icordebugmergedassemblyrecord-getsimplename-method.md)|<span data-ttu-id="c39fa-116">Ottiene il nome semplice dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="c39fa-116">Gets the simple name of the assembly.</span></span>|  
|[<span data-ttu-id="c39fa-117">Metodo GetVersion</span><span class="sxs-lookup"><span data-stu-id="c39fa-117">GetVersion Method</span></span>](icordebugmergedassemblyrecord-getversion-method.md)|<span data-ttu-id="c39fa-118">Ottiene le informazioni sulla versione dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="c39fa-118">Gets the assembly's version information.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c39fa-119">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="c39fa-119">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="c39fa-120">Questa interfaccia è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="c39fa-120">This interface is available with .NET Native only.</span></span> <span data-ttu-id="c39fa-121">Se questa interfaccia viene implementata per scenari ICorDebug al di fuori di .NET Native, sarà ignorata da Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="c39fa-121">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c39fa-122">Requisiti</span><span class="sxs-lookup"><span data-stu-id="c39fa-122">Requirements</span></span>  
 <span data-ttu-id="c39fa-123">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c39fa-123">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c39fa-124">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c39fa-124">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c39fa-125">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c39fa-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c39fa-126">**Versioni .NET Framework:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c39fa-126">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c39fa-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c39fa-127">See also</span></span>

- [<span data-ttu-id="c39fa-128">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="c39fa-128">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="c39fa-129">Debug</span><span class="sxs-lookup"><span data-stu-id="c39fa-129">Debugging</span></span>](index.md)
