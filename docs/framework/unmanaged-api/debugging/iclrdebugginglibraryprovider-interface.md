---
title: Interfaccia ICLRDebuggingLibraryProvider
ms.date: 03/30/2017
api_name:
- ICLRDebuggingLibraryProvider
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDebuggingLibraryProvider
helpviewer_keywords:
- ICLRDebuggingLibraryProvider interface [.NET Framework debugging]
ms.assetid: 67739617-6add-41a9-9de5-a3200c3109ce
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c62079a87c09bcbe09167a137fd39530652ae3e5
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59106340"
---
# <a name="iclrdebugginglibraryprovider-interface"></a><span data-ttu-id="77ec4-102">Interfaccia ICLRDebuggingLibraryProvider</span><span class="sxs-lookup"><span data-stu-id="77ec4-102">ICLRDebuggingLibraryProvider Interface</span></span>
<span data-ttu-id="77ec4-103">Include il [metodo ProvideLibrary](../../../../docs/framework/unmanaged-api/debugging/iclrdebugginglibraryprovider-providelibrary-method.md) metodo, che ottiene un provider di librerie di interfaccia di callback che consente a common language runtime le librerie di debug specifiche della versione di individuare e caricare su richiesta.</span><span class="sxs-lookup"><span data-stu-id="77ec4-103">Includes the [ProvideLibrary Method](../../../../docs/framework/unmanaged-api/debugging/iclrdebugginglibraryprovider-providelibrary-method.md) method, which gets a library provider callback interface that allows common language runtime version-specific debugging libraries to be located and loaded on demand.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="77ec4-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="77ec4-104">Methods</span></span>  
  
|<span data-ttu-id="77ec4-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="77ec4-105">Method</span></span>|<span data-ttu-id="77ec4-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="77ec4-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="77ec4-107">Metodo ProvideLibrary</span><span class="sxs-lookup"><span data-stu-id="77ec4-107">ProvideLibrary Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdebugginglibraryprovider-providelibrary-method.md)|<span data-ttu-id="77ec4-108">Consente al debugger fornire un handle a un modulo che può essere usato per caricare una libreria di debug.</span><span class="sxs-lookup"><span data-stu-id="77ec4-108">Allows the debugger to provide a handle to a module which can be used to load a debug library.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="77ec4-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="77ec4-109">Requirements</span></span>  
 <span data-ttu-id="77ec4-110">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="77ec4-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="77ec4-111">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="77ec4-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="77ec4-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="77ec4-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="77ec4-113">**Versioni di .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="77ec4-113">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="77ec4-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="77ec4-114">See also</span></span>

- [<span data-ttu-id="77ec4-115">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="77ec4-115">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="77ec4-116">Debug</span><span class="sxs-lookup"><span data-stu-id="77ec4-116">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
