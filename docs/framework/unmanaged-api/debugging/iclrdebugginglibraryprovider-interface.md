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
ms.openlocfilehash: 77c2011ce677d1bd2823d47740782f48151b408a
ms.sourcegitcommit: d9c7ac5d06735a01c1fafe34efe9486734841a72
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/06/2020
ms.locfileid: "82860286"
---
# <a name="iclrdebugginglibraryprovider-interface"></a><span data-ttu-id="24aa9-102">Interfaccia ICLRDebuggingLibraryProvider</span><span class="sxs-lookup"><span data-stu-id="24aa9-102">ICLRDebuggingLibraryProvider Interface</span></span>
<span data-ttu-id="24aa9-103">Include il metodo del [Metodo ProvideLibrary](iclrdebugginglibraryprovider-providelibrary-method.md) , che ottiene un'interfaccia di callback del provider di librerie che consente di trovare e caricare su richiesta Common Language Runtime librerie di debug specifiche della versione.</span><span class="sxs-lookup"><span data-stu-id="24aa9-103">Includes the [ProvideLibrary Method](iclrdebugginglibraryprovider-providelibrary-method.md) method, which gets a library provider callback interface that allows common language runtime version-specific debugging libraries to be located and loaded on demand.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="24aa9-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="24aa9-104">Methods</span></span>  
  
|<span data-ttu-id="24aa9-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="24aa9-105">Method</span></span>|<span data-ttu-id="24aa9-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="24aa9-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="24aa9-107">Metodo ProvideLibrary</span><span class="sxs-lookup"><span data-stu-id="24aa9-107">ProvideLibrary Method</span></span>](iclrdebugginglibraryprovider-providelibrary-method.md)|<span data-ttu-id="24aa9-108">Consente al debugger di fornire un handle a un modulo che può essere utilizzato per caricare una libreria di debug.</span><span class="sxs-lookup"><span data-stu-id="24aa9-108">Allows the debugger to provide a handle to a module which can be used to load a debug library.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="24aa9-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="24aa9-109">Requirements</span></span>  
 <span data-ttu-id="24aa9-110">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="24aa9-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="24aa9-111">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="24aa9-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="24aa9-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="24aa9-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="24aa9-113">**Versioni .NET Framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="24aa9-113">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="24aa9-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="24aa9-114">See also</span></span>

- [<span data-ttu-id="24aa9-115">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="24aa9-115">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="24aa9-116">Debug</span><span class="sxs-lookup"><span data-stu-id="24aa9-116">Debugging</span></span>](index.md)
