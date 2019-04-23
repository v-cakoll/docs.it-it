---
title: Interfaccia ICorDebugRemoteTarget
ms.date: 03/30/2017
api_name:
- ICorDebugRemoteTarget
api_location:
- CorDebug.dll
api_type:
- COM
f1_keywords:
- ICorDebugRemoteTarget
helpviewer_keywords:
- ICorDebugRemoteTarget interface [.NET Framework debugging]
ms.assetid: bd9936a6-cc24-4869-8761-0988664464e6
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ae31506d4ba34bf262f49bc2321c6cfcd30f1b60
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59197321"
---
# <a name="icordebugremotetarget-interface"></a><span data-ttu-id="de998-102">Interfaccia ICorDebugRemoteTarget</span><span class="sxs-lookup"><span data-stu-id="de998-102">ICorDebugRemoteTarget Interface</span></span>
<span data-ttu-id="de998-103">Fornisce i metodi che consentono agli sviluppatori di eseguire il debug delle applicazioni basate su Silverlight nell'ambiente CLR (Common Language Runtime).</span><span class="sxs-lookup"><span data-stu-id="de998-103">Provides methods that enable developers to debug Silverlight-based applications in the common language runtime (CLR) environment.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="de998-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="de998-104">Syntax</span></span>  
  
```  
interface ICorDebugRemoteTarget  : IUnknown  
{  
    HRESULT GetHostName (  
        [in]  ULONG32                    cchHostName,  
        [out] ULONG32*                   pcchHostName,  
        [out, size_is(cchHostName),  
              length_is(*pcchHostName)]  
                  WCHAR szHostName[]  
        );  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="de998-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="de998-105">Methods</span></span>  
  
|<span data-ttu-id="de998-106">Metodo</span><span class="sxs-lookup"><span data-stu-id="de998-106">Method</span></span>|<span data-ttu-id="de998-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="de998-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="de998-108">Metodo ICorDebugRemoteTarget::GetHostName</span><span class="sxs-lookup"><span data-stu-id="de998-108">ICorDebugRemoteTarget::GetHostName Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugremotetarget-gethostname-method.md)|<span data-ttu-id="de998-109">Restituisce il nome host o l'indirizzo IP di un computer remoto.</span><span class="sxs-lookup"><span data-stu-id="de998-109">Returns the host name or the IP address of a remote machine.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="de998-110">Note</span><span class="sxs-lookup"><span data-stu-id="de998-110">Remarks</span></span>  
 <span data-ttu-id="de998-111">Il debug in modalità mista (cioè codice gestito e nativo) non è supportato né da Windows 95, Windows 98 o Windows ME né dalle piattaforme diverse da x86 (ad esempio IA-64 e AMD64).</span><span class="sxs-lookup"><span data-stu-id="de998-111">Mixed-mode (that is, managed and native code) debugging is not supported on Windows 95, Windows 98, or Windows ME, or on non-x86 platforms (such as IA-64 and AMD64).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="de998-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="de998-112">Requirements</span></span>  
 <span data-ttu-id="de998-113">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="de998-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="de998-114">**Intestazione:** CorDebug.idl</span><span class="sxs-lookup"><span data-stu-id="de998-114">**Header:** CorDebug.idl</span></span>  
  
 <span data-ttu-id="de998-115">**Libreria:** : CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="de998-115">**Library:** : CorGuids.lib</span></span>  
  
 <span data-ttu-id="de998-116">**Versioni di .NET framework:** 3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="de998-116">**.NET Framework Versions:** 3.5 SP1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="de998-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="de998-117">See also</span></span>

- [<span data-ttu-id="de998-118">Interfaccia ICorDebugRemote</span><span class="sxs-lookup"><span data-stu-id="de998-118">ICorDebugRemote Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugremote-interface.md)
- [<span data-ttu-id="de998-119">Interfaccia ICorDebug</span><span class="sxs-lookup"><span data-stu-id="de998-119">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
- [<span data-ttu-id="de998-120">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="de998-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
