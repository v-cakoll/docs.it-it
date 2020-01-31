---
title: Metodo ICorDebugVariableSymbol::GetSize
ms.date: 03/30/2017
ms.assetid: add0cd9d-9a29-49b1-ae07-d9d3786b4ccd
ms.openlocfilehash: 6d60dbdefd09770fd5a18653c5118469323581e1
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790908"
---
# <a name="icordebugvariablesymbolgetsize-method"></a><span data-ttu-id="479f3-102">Metodo ICorDebugVariableSymbol::GetSize</span><span class="sxs-lookup"><span data-stu-id="479f3-102">ICorDebugVariableSymbol::GetSize Method</span></span>
<span data-ttu-id="479f3-103">Ottiene le dimensioni di una variabile in byte.</span><span class="sxs-lookup"><span data-stu-id="479f3-103">Gets the size of a variable in bytes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="479f3-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="479f3-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSize(  
   [out] ULONG32 *pcbValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="479f3-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="479f3-105">Parameters</span></span>  
 `pcbValue`  
 <span data-ttu-id="479f3-106">Puntatore a un intero senza segno a 32 bit che contiene le dimensioni della variabile.</span><span class="sxs-lookup"><span data-stu-id="479f3-106">A pointer to a 32-bit unsigned integer containing the size of the variable.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="479f3-107">Note</span><span class="sxs-lookup"><span data-stu-id="479f3-107">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="479f3-108">Questo metodo è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="479f3-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="479f3-109">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="479f3-109">Requirements</span></span>  
 <span data-ttu-id="479f3-110">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="479f3-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="479f3-111">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="479f3-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="479f3-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="479f3-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="479f3-113">**Versioni .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="479f3-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="479f3-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="479f3-114">See also</span></span>

- [<span data-ttu-id="479f3-115">Interfaccia ICorDebugVariableSymbol</span><span class="sxs-lookup"><span data-stu-id="479f3-115">ICorDebugVariableSymbol Interface</span></span>](icordebugvariablesymbol-interface.md)
- [<span data-ttu-id="479f3-116">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="479f3-116">Debugging Interfaces</span></span>](debugging-interfaces.md)
