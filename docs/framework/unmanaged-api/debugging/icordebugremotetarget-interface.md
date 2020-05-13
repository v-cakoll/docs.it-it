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
ms.openlocfilehash: 4883c208468db0096bed3ff8cf4a8ed50a5d7cc6
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/13/2020
ms.locfileid: "83379236"
---
# <a name="icordebugremotetarget-interface"></a><span data-ttu-id="5887a-102">Interfaccia ICorDebugRemoteTarget</span><span class="sxs-lookup"><span data-stu-id="5887a-102">ICorDebugRemoteTarget Interface</span></span>
<span data-ttu-id="5887a-103">Fornisce i metodi che consentono agli sviluppatori di eseguire il debug delle applicazioni basate su Silverlight nell'ambiente CLR (Common Language Runtime).</span><span class="sxs-lookup"><span data-stu-id="5887a-103">Provides methods that enable developers to debug Silverlight-based applications in the common language runtime (CLR) environment.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5887a-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5887a-104">Syntax</span></span>  
  
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
  
## <a name="methods"></a><span data-ttu-id="5887a-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="5887a-105">Methods</span></span>  
  
|<span data-ttu-id="5887a-106">Metodo</span><span class="sxs-lookup"><span data-stu-id="5887a-106">Method</span></span>|<span data-ttu-id="5887a-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5887a-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="5887a-108">Metodo ICorDebugRemoteTarget::GetHostName</span><span class="sxs-lookup"><span data-stu-id="5887a-108">ICorDebugRemoteTarget::GetHostName Method</span></span>](icordebugremotetarget-gethostname-method.md)|<span data-ttu-id="5887a-109">Restituisce il nome host o l'indirizzo IP di un computer remoto.</span><span class="sxs-lookup"><span data-stu-id="5887a-109">Returns the host name or the IP address of a remote machine.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5887a-110">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="5887a-110">Remarks</span></span>  
 <span data-ttu-id="5887a-111">Il debug in modalità mista (cioè codice gestito e nativo) non è supportato né da Windows 95, Windows 98 o Windows ME né dalle piattaforme diverse da x86 (ad esempio IA-64 e AMD64).</span><span class="sxs-lookup"><span data-stu-id="5887a-111">Mixed-mode (that is, managed and native code) debugging is not supported on Windows 95, Windows 98, or Windows ME, or on non-x86 platforms (such as IA-64 and AMD64).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5887a-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="5887a-112">Requirements</span></span>  
 <span data-ttu-id="5887a-113">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5887a-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5887a-114">**Intestazione:** CorDebug. idl</span><span class="sxs-lookup"><span data-stu-id="5887a-114">**Header:** CorDebug.idl</span></span>  
  
 <span data-ttu-id="5887a-115">**Libreria:** : corguids. lib</span><span class="sxs-lookup"><span data-stu-id="5887a-115">**Library:** : CorGuids.lib</span></span>  
  
 <span data-ttu-id="5887a-116">**Versioni .NET Framework:** 3,5 SP1</span><span class="sxs-lookup"><span data-stu-id="5887a-116">**.NET Framework Versions:** 3.5 SP1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5887a-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5887a-117">See also</span></span>

- [<span data-ttu-id="5887a-118">Interfaccia ICorDebugRemote</span><span class="sxs-lookup"><span data-stu-id="5887a-118">ICorDebugRemote Interface</span></span>](icordebugremote-interface.md)
- [<span data-ttu-id="5887a-119">Interfaccia ICorDebug</span><span class="sxs-lookup"><span data-stu-id="5887a-119">ICorDebug Interface</span></span>](icordebug-interface.md)
- [<span data-ttu-id="5887a-120">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="5887a-120">Debugging Interfaces</span></span>](debugging-interfaces.md)
