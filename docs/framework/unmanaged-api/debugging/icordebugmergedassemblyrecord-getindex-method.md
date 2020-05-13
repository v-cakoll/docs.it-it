---
title: Metodo ICorDebugMergedAssemblyRecord::GetIndex
ms.date: 03/30/2017
ms.assetid: 98701444-b9bc-4978-9548-89ac3394147d
ms.openlocfilehash: b13e589e32b3317b567a4a89a5b48fc1299a1a84
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2020
ms.locfileid: "83206958"
---
# <a name="icordebugmergedassemblyrecordgetindex-method"></a><span data-ttu-id="0231e-102">Metodo ICorDebugMergedAssemblyRecord::GetIndex</span><span class="sxs-lookup"><span data-stu-id="0231e-102">ICorDebugMergedAssemblyRecord::GetIndex Method</span></span>
<span data-ttu-id="0231e-103">Ottiene l'indice del prefisso dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="0231e-103">Gets the assembly's prefix index.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0231e-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0231e-104">Syntax</span></span>  
  
```cpp  
HRESULT GetIndex(  
   [out] ULONG32 *pIndex  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0231e-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="0231e-105">Parameters</span></span>  
 `pIndex`  
 <span data-ttu-id="0231e-106">[out] Puntatore all'indice del prefisso.</span><span class="sxs-lookup"><span data-stu-id="0231e-106">[out] A pointer to the prefix index.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0231e-107">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="0231e-107">Remarks</span></span>  
 <span data-ttu-id="0231e-108">L'indice del prefisso viene usato per evitare conflitti di nome nei nomi dei tipi di metadati uniti.</span><span class="sxs-lookup"><span data-stu-id="0231e-108">The prefix index is used to prevent name collisions in the merged metadata type names.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="0231e-109">Questo metodo è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="0231e-109">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0231e-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="0231e-110">Requirements</span></span>  
 <span data-ttu-id="0231e-111">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0231e-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0231e-112">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0231e-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0231e-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0231e-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0231e-114">**Versioni .NET Framework:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0231e-114">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0231e-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0231e-115">See also</span></span>

- [<span data-ttu-id="0231e-116">Interfaccia ICorDebugMergedAssemblyRecord</span><span class="sxs-lookup"><span data-stu-id="0231e-116">ICorDebugMergedAssemblyRecord Interface</span></span>](icordebugmergedassemblyrecord-interface.md)
- [<span data-ttu-id="0231e-117">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="0231e-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
