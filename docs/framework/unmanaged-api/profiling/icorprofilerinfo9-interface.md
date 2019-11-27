---
title: Interfaccia ICorProfilerInfo9
ms.date: 08/06/2019
author: davmason
ms.author: davmason
ms.openlocfilehash: 74031fd822550f8a0752d02ce0c2d89b2f5ae546
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74444955"
---
# <a name="icorprofilerinfo9-interface"></a><span data-ttu-id="68efb-102">Interfaccia ICorProfilerInfo9</span><span class="sxs-lookup"><span data-stu-id="68efb-102">ICorProfilerInfo9 Interface</span></span>

<span data-ttu-id="68efb-103">Sottoclasse di [ICorProfilerInfo8](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo8-interface.md) che fornisce metodi per eseguire query sulle informazioni sulle funzioni con più versioni di codice nativo.</span><span class="sxs-lookup"><span data-stu-id="68efb-103">A subclass of [ICorProfilerInfo8](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo8-interface.md) that provides methods to query information about functions with multiple native code versions.</span></span>  

## <a name="methods"></a><span data-ttu-id="68efb-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="68efb-104">Methods</span></span>  

| <span data-ttu-id="68efb-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="68efb-105">Method</span></span>|<span data-ttu-id="68efb-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="68efb-106">Description</span></span>|  
| ------------|-----------------|  
|[<span data-ttu-id="68efb-107">Metodo GetNativeCodeStartAddresses</span><span class="sxs-lookup"><span data-stu-id="68efb-107">GetNativeCodeStartAddresses Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo9-getnativecodestartaddresses-method.md)| <span data-ttu-id="68efb-108">Dato un functionId e rejitId, enumera l'indirizzo iniziale del codice nativo di tutte le versioni compilato JIT del codice attualmente esistente.</span><span class="sxs-lookup"><span data-stu-id="68efb-108">Given a functionId and rejitId, enumerates the native code start address of all jitted versions of this code that currently exist.</span></span> |
|[<span data-ttu-id="68efb-109">Metodo GetILToNativeMapping3</span><span class="sxs-lookup"><span data-stu-id="68efb-109">GetILToNativeMapping3 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo9-getiltonativemapping3-method.md)| <span data-ttu-id="68efb-110">Dato l'indirizzo iniziale del codice nativo, restituisce le informazioni di mapping native a per la versione compilato JIT del codice.</span><span class="sxs-lookup"><span data-stu-id="68efb-110">Given the native code start address, returns the native to IL mapping information for this jitted version of the code.</span></span> |
|[<span data-ttu-id="68efb-111">Metodo GetCodeInfo4</span><span class="sxs-lookup"><span data-stu-id="68efb-111">GetCodeInfo4 Method</span></span>](icorprofilerinfo9-getcodeinfo4-method.md)| <span data-ttu-id="68efb-112">Dato l'indirizzo iniziale del codice nativo, restituisce i blocchi di memoria virtuale che archiviano il codice.</span><span class="sxs-lookup"><span data-stu-id="68efb-112">Given the native code start address, returns the blocks of virtual memory that store this code.</span></span> |

## <a name="requirements"></a><span data-ttu-id="68efb-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="68efb-113">Requirements</span></span>  
<span data-ttu-id="68efb-114">**Piattaforme:** Vedere [sistemi operativi supportati da .NET Core](../../../core/install/dependencies.md?tabs=netcore30&pivots=os-windows).</span><span class="sxs-lookup"><span data-stu-id="68efb-114">**Platforms:** See [.NET Core supported operating systems](../../../core/install/dependencies.md?tabs=netcore30&pivots=os-windows).</span></span>  
<span data-ttu-id="68efb-115">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="68efb-115">**Header:** CorProf.idl, CorProf.h</span></span>  
<span data-ttu-id="68efb-116">**Versioni di .NET:** [!INCLUDE[net_core](../../../../includes/net-core-22-md.md)]</span><span class="sxs-lookup"><span data-stu-id="68efb-116">**.NET Versions:** [!INCLUDE[net_core](../../../../includes/net-core-22-md.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="68efb-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="68efb-117">See also</span></span>

- [<span data-ttu-id="68efb-118">Interfacce di profilatura</span><span class="sxs-lookup"><span data-stu-id="68efb-118">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
