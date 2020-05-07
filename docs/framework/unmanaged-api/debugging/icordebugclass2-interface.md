---
title: Interfaccia ICorDebugClass2
ms.date: 03/30/2017
api_name:
- ICorDebugClass2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugClass2
helpviewer_keywords:
- ICorDebugClass2 interface [.NET Framework debugging]
ms.assetid: 5416de70-43f2-4cdf-a11f-d570759c9c0c
topic_type:
- apiref
ms.openlocfilehash: ff15297eb479f7474c9f07123a29263fb4da3205
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/07/2020
ms.locfileid: "82893982"
---
# <a name="icordebugclass2-interface"></a><span data-ttu-id="c2152-102">Interfaccia ICorDebugClass2</span><span class="sxs-lookup"><span data-stu-id="c2152-102">ICorDebugClass2 Interface</span></span>

<span data-ttu-id="c2152-103">Rappresenta una classe generica oppure una classe con un parametro di metodo di tipo <xref:System.Type>.</span><span class="sxs-lookup"><span data-stu-id="c2152-103">Represents a generic class or a class with a method parameter of type <xref:System.Type>.</span></span> <span data-ttu-id="c2152-104">Questa interfaccia estende [ICorDebugClass](icordebugclass-interface.md).</span><span class="sxs-lookup"><span data-stu-id="c2152-104">This interface extends [ICorDebugClass](icordebugclass-interface.md).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="c2152-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="c2152-105">Methods</span></span>  
  
|<span data-ttu-id="c2152-106">Metodo</span><span class="sxs-lookup"><span data-stu-id="c2152-106">Method</span></span>|<span data-ttu-id="c2152-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c2152-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="c2152-108">Metodo GetParameterizedType</span><span class="sxs-lookup"><span data-stu-id="c2152-108">GetParameterizedType Method</span></span>](icordebugclass2-getparameterizedtype-method.md)|<span data-ttu-id="c2152-109">Ottiene la dichiarazione del tipo per questa classe.</span><span class="sxs-lookup"><span data-stu-id="c2152-109">Gets the type declaration for this class.</span></span>|  
|[<span data-ttu-id="c2152-110">Metodo SetJMCStatus</span><span class="sxs-lookup"><span data-stu-id="c2152-110">SetJMCStatus Method</span></span>](icordebugclass2-setjmcstatus-method.md)|<span data-ttu-id="c2152-111">Per ogni metodo di questa classe, imposta un valore che indica se il metodo è codice definito dall'utente.</span><span class="sxs-lookup"><span data-stu-id="c2152-111">For each method of this class, sets a value that indicates whether the method is user-defined code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c2152-112">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="c2152-112">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="c2152-113">Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.</span><span class="sxs-lookup"><span data-stu-id="c2152-113">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c2152-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="c2152-114">Requirements</span></span>  
 <span data-ttu-id="c2152-115">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c2152-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c2152-116">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c2152-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c2152-117">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c2152-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c2152-118">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c2152-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c2152-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c2152-119">See also</span></span>

- [<span data-ttu-id="c2152-120">Interfaccia ICorDebugClass</span><span class="sxs-lookup"><span data-stu-id="c2152-120">ICorDebugClass Interface</span></span>](icordebugclass-interface.md)
- [<span data-ttu-id="c2152-121">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="c2152-121">Debugging Interfaces</span></span>](debugging-interfaces.md)
