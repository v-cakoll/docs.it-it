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
ms.openlocfilehash: 97c4e6d3c9de7dcb8d399a956a4a58c49ca6e3b9
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73131877"
---
# <a name="icordebugremotetarget-interface"></a><span data-ttu-id="091ee-102">Interfaccia ICorDebugRemoteTarget</span><span class="sxs-lookup"><span data-stu-id="091ee-102">ICorDebugRemoteTarget Interface</span></span>
<span data-ttu-id="091ee-103">Fornisce i metodi che consentono agli sviluppatori di eseguire il debug delle applicazioni basate su Silverlight nell'ambiente CLR (Common Language Runtime).</span><span class="sxs-lookup"><span data-stu-id="091ee-103">Provides methods that enable developers to debug Silverlight-based applications in the common language runtime (CLR) environment.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="091ee-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="091ee-104">Syntax</span></span>  
  
```cpp  
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
  
## <a name="methods"></a><span data-ttu-id="091ee-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="091ee-105">Methods</span></span>  
  
|<span data-ttu-id="091ee-106">Metodo</span><span class="sxs-lookup"><span data-stu-id="091ee-106">Method</span></span>|<span data-ttu-id="091ee-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="091ee-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="091ee-108">Metodo ICorDebugRemoteTarget::GetHostName</span><span class="sxs-lookup"><span data-stu-id="091ee-108">ICorDebugRemoteTarget::GetHostName Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugremotetarget-gethostname-method.md)|<span data-ttu-id="091ee-109">Restituisce il nome host o l'indirizzo IP di un computer remoto.</span><span class="sxs-lookup"><span data-stu-id="091ee-109">Returns the host name or the IP address of a remote machine.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="091ee-110">Note</span><span class="sxs-lookup"><span data-stu-id="091ee-110">Remarks</span></span>  
 <span data-ttu-id="091ee-111">Il debug in modalità mista (cioè codice gestito e nativo) non è supportato né da Windows 95, Windows 98 o Windows ME né dalle piattaforme diverse da x86 (ad esempio IA-64 e AMD64).</span><span class="sxs-lookup"><span data-stu-id="091ee-111">Mixed-mode (that is, managed and native code) debugging is not supported on Windows 95, Windows 98, or Windows ME, or on non-x86 platforms (such as IA-64 and AMD64).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="091ee-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="091ee-112">Requirements</span></span>  
 <span data-ttu-id="091ee-113">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="091ee-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="091ee-114">**Intestazione:** CorDebug. idl</span><span class="sxs-lookup"><span data-stu-id="091ee-114">**Header:** CorDebug.idl</span></span>  
  
 <span data-ttu-id="091ee-115">**Libreria:** : corguids. lib</span><span class="sxs-lookup"><span data-stu-id="091ee-115">**Library:** : CorGuids.lib</span></span>  
  
 <span data-ttu-id="091ee-116">**Versioni .NET Framework:** 3,5 SP1</span><span class="sxs-lookup"><span data-stu-id="091ee-116">**.NET Framework Versions:** 3.5 SP1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="091ee-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="091ee-117">See also</span></span>

- [<span data-ttu-id="091ee-118">Interfaccia ICorDebugRemote</span><span class="sxs-lookup"><span data-stu-id="091ee-118">ICorDebugRemote Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugremote-interface.md)
- [<span data-ttu-id="091ee-119">Interfaccia ICorDebug</span><span class="sxs-lookup"><span data-stu-id="091ee-119">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
- [<span data-ttu-id="091ee-120">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="091ee-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
