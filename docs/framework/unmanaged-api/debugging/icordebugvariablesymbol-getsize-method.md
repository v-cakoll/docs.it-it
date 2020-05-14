---
title: Metodo ICorDebugVariableSymbol::GetSize
ms.date: 03/30/2017
ms.assetid: add0cd9d-9a29-49b1-ae07-d9d3786b4ccd
ms.openlocfilehash: d924de33c8ec49501be0ee7700b2eee8c79bb950
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/14/2020
ms.locfileid: "83397120"
---
# <a name="icordebugvariablesymbolgetsize-method"></a><span data-ttu-id="e106b-102">Metodo ICorDebugVariableSymbol::GetSize</span><span class="sxs-lookup"><span data-stu-id="e106b-102">ICorDebugVariableSymbol::GetSize Method</span></span>
<span data-ttu-id="e106b-103">Ottiene le dimensioni di una variabile in byte.</span><span class="sxs-lookup"><span data-stu-id="e106b-103">Gets the size of a variable in bytes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e106b-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e106b-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSize(  
   [out] ULONG32 *pcbValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e106b-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="e106b-105">Parameters</span></span>  
 `pcbValue`  
 <span data-ttu-id="e106b-106">Puntatore a un intero senza segno a 32 bit che contiene le dimensioni della variabile.</span><span class="sxs-lookup"><span data-stu-id="e106b-106">A pointer to a 32-bit unsigned integer containing the size of the variable.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e106b-107">Commenti</span><span class="sxs-lookup"><span data-stu-id="e106b-107">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e106b-108">Questo metodo è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="e106b-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e106b-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="e106b-109">Requirements</span></span>  
 <span data-ttu-id="e106b-110">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e106b-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e106b-111">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e106b-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e106b-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e106b-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e106b-113">**Versioni .NET Framework:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e106b-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e106b-114">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="e106b-114">See also</span></span>

- [<span data-ttu-id="e106b-115">Interfaccia ICorDebugVariableSymbol</span><span class="sxs-lookup"><span data-stu-id="e106b-115">ICorDebugVariableSymbol Interface</span></span>](icordebugvariablesymbol-interface.md)
- [<span data-ttu-id="e106b-116">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="e106b-116">Debugging Interfaces</span></span>](debugging-interfaces.md)
