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
ms.openlocfilehash: a8d9348572ec0cf67c5facebb2053a7091661724
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793592"
---
# <a name="iclrdebugginglibraryprovider-interface"></a><span data-ttu-id="5f79f-102">Interfaccia ICLRDebuggingLibraryProvider</span><span class="sxs-lookup"><span data-stu-id="5f79f-102">ICLRDebuggingLibraryProvider Interface</span></span>
<span data-ttu-id="5f79f-103">Include il metodo del [Metodo ProvideLibrary](iclrdebugginglibraryprovider-providelibrary-method.md) , che ottiene un'interfaccia di callback del provider di librerie che consente di trovare e caricare su richiesta Common Language Runtime librerie di debug specifiche della versione.</span><span class="sxs-lookup"><span data-stu-id="5f79f-103">Includes the [ProvideLibrary Method](iclrdebugginglibraryprovider-providelibrary-method.md) method, which gets a library provider callback interface that allows common language runtime version-specific debugging libraries to be located and loaded on demand.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="5f79f-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="5f79f-104">Methods</span></span>  
  
|<span data-ttu-id="5f79f-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="5f79f-105">Method</span></span>|<span data-ttu-id="5f79f-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5f79f-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="5f79f-107">Metodo ProvideLibrary</span><span class="sxs-lookup"><span data-stu-id="5f79f-107">ProvideLibrary Method</span></span>](iclrdebugginglibraryprovider-providelibrary-method.md)|<span data-ttu-id="5f79f-108">Consente al debugger di fornire un handle a un modulo che può essere utilizzato per caricare una libreria di debug.</span><span class="sxs-lookup"><span data-stu-id="5f79f-108">Allows the debugger to provide a handle to a module which can be used to load a debug library.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="5f79f-109">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="5f79f-109">Requirements</span></span>  
 <span data-ttu-id="5f79f-110">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5f79f-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5f79f-111">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5f79f-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5f79f-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5f79f-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5f79f-113">**Versioni .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5f79f-113">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5f79f-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5f79f-114">See also</span></span>

- [<span data-ttu-id="5f79f-115">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="5f79f-115">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="5f79f-116">Debug</span><span class="sxs-lookup"><span data-stu-id="5f79f-116">Debugging</span></span>](index.md)
