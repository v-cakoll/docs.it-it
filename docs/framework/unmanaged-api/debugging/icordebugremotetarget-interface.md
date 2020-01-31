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
ms.openlocfilehash: bab6b7f683b5563cf362366dfb007f83caeee12d
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791929"
---
# <a name="icordebugremotetarget-interface"></a><span data-ttu-id="96755-102">Interfaccia ICorDebugRemoteTarget</span><span class="sxs-lookup"><span data-stu-id="96755-102">ICorDebugRemoteTarget Interface</span></span>
<span data-ttu-id="96755-103">Fornisce i metodi che consentono agli sviluppatori di eseguire il debug delle applicazioni basate su Silverlight nell'ambiente CLR (Common Language Runtime).</span><span class="sxs-lookup"><span data-stu-id="96755-103">Provides methods that enable developers to debug Silverlight-based applications in the common language runtime (CLR) environment.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="96755-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="96755-104">Syntax</span></span>  
  
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
  
## <a name="methods"></a><span data-ttu-id="96755-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="96755-105">Methods</span></span>  
  
|<span data-ttu-id="96755-106">Metodo</span><span class="sxs-lookup"><span data-stu-id="96755-106">Method</span></span>|<span data-ttu-id="96755-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="96755-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="96755-108">Metodo ICorDebugRemoteTarget::GetHostName</span><span class="sxs-lookup"><span data-stu-id="96755-108">ICorDebugRemoteTarget::GetHostName Method</span></span>](icordebugremotetarget-gethostname-method.md)|<span data-ttu-id="96755-109">Restituisce il nome host o l'indirizzo IP di un computer remoto.</span><span class="sxs-lookup"><span data-stu-id="96755-109">Returns the host name or the IP address of a remote machine.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="96755-110">Note</span><span class="sxs-lookup"><span data-stu-id="96755-110">Remarks</span></span>  
 <span data-ttu-id="96755-111">Il debug in modalità mista (cioè codice gestito e nativo) non è supportato né da Windows 95, Windows 98 o Windows ME né dalle piattaforme diverse da x86 (ad esempio IA-64 e AMD64).</span><span class="sxs-lookup"><span data-stu-id="96755-111">Mixed-mode (that is, managed and native code) debugging is not supported on Windows 95, Windows 98, or Windows ME, or on non-x86 platforms (such as IA-64 and AMD64).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="96755-112">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="96755-112">Requirements</span></span>  
 <span data-ttu-id="96755-113">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="96755-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="96755-114">**Intestazione:** CorDebug. idl</span><span class="sxs-lookup"><span data-stu-id="96755-114">**Header:** CorDebug.idl</span></span>  
  
 <span data-ttu-id="96755-115">**Libreria:** : corguids. lib</span><span class="sxs-lookup"><span data-stu-id="96755-115">**Library:** : CorGuids.lib</span></span>  
  
 <span data-ttu-id="96755-116">**Versioni .NET Framework:** 3,5 SP1</span><span class="sxs-lookup"><span data-stu-id="96755-116">**.NET Framework Versions:** 3.5 SP1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="96755-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="96755-117">See also</span></span>

- [<span data-ttu-id="96755-118">Interfaccia ICorDebugRemote</span><span class="sxs-lookup"><span data-stu-id="96755-118">ICorDebugRemote Interface</span></span>](icordebugremote-interface.md)
- [<span data-ttu-id="96755-119">Interfaccia ICorDebug</span><span class="sxs-lookup"><span data-stu-id="96755-119">ICorDebug Interface</span></span>](icordebug-interface.md)
- [<span data-ttu-id="96755-120">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="96755-120">Debugging Interfaces</span></span>](debugging-interfaces.md)
