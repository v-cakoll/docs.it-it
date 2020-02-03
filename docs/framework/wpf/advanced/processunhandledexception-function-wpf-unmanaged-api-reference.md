---
title: Funzione ProcessUnhandledException-informazioni di riferimento sulle API WPF non gestite
titleSuffix: ''
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ProcessUnhandledException
api_location:
- PresentationHost_v0400.dll
ms.assetid: 495ce5f6-bb4d-4b30-807a-c3c35f1ca95c
ms.openlocfilehash: 757e5ac3aa2dc4c87b210b026998523bd82045c1
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743915"
---
# <a name="processunhandledexception-function-wpf-unmanaged-api-reference"></a><span data-ttu-id="e47d0-102">Funzione ProcessUnhandledException (riferimenti alle API non gestite WPF)</span><span class="sxs-lookup"><span data-stu-id="e47d0-102">ProcessUnhandledException Function (WPF Unmanaged API Reference)</span></span>
<span data-ttu-id="e47d0-103">Questa API supporta l'infrastruttura Windows Presentation Foundation (WPF) e non può essere usata direttamente dal codice.</span><span class="sxs-lookup"><span data-stu-id="e47d0-103">This API supports the Windows Presentation Foundation (WPF) infrastructure and is not intended to be used directly from your code.</span></span>  
  
 <span data-ttu-id="e47d0-104">Utilizzato dall'infrastruttura Windows Presentation Foundation (WPF) per la gestione delle eccezioni.</span><span class="sxs-lookup"><span data-stu-id="e47d0-104">Used by the Windows Presentation Foundation (WPF) infrastructure for exception handling.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e47d0-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e47d0-105">Syntax</span></span>  
  
```cpp  
void __stdcall ProcessUnhandledException(  
   __in_ecount(1) BSTR errorMsg  
)  
```  
  
## <a name="parameters"></a><span data-ttu-id="e47d0-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="e47d0-106">Parameters</span></span>  
 <span data-ttu-id="e47d0-107">errorMsg</span><span class="sxs-lookup"><span data-stu-id="e47d0-107">errorMsg</span></span>  
 <span data-ttu-id="e47d0-108">Messaggio di errore.</span><span class="sxs-lookup"><span data-stu-id="e47d0-108">The error message.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e47d0-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="e47d0-109">Requirements</span></span>  
 <span data-ttu-id="e47d0-110">**Piattaforme:** Vedere [.NET Framework requisiti di sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e47d0-110">**Platforms:** See [.NET Framework System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e47d0-111">**DLL**</span><span class="sxs-lookup"><span data-stu-id="e47d0-111">**DLL:**</span></span>  
  
 <span data-ttu-id="e47d0-112">Nel .NET Framework 3,0 e 3,5: PresentationHostDLL. dll</span><span class="sxs-lookup"><span data-stu-id="e47d0-112">In the .NET Framework 3.0 and 3.5: PresentationHostDLL.dll</span></span>  
  
 <span data-ttu-id="e47d0-113">In .NET Framework 4 e versioni successive: PresentationHost_v0400. dll</span><span class="sxs-lookup"><span data-stu-id="e47d0-113">In the .NET Framework 4 and later: PresentationHost_v0400.dll</span></span>  
  
 <span data-ttu-id="e47d0-114">**Versione .NET Framework:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e47d0-114">**.NET Framework Version:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e47d0-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e47d0-115">See also</span></span>

- [<span data-ttu-id="e47d0-116">Riferimenti alle API non gestite di WPF</span><span class="sxs-lookup"><span data-stu-id="e47d0-116">WPF Unmanaged API Reference</span></span>](wpf-unmanaged-api-reference.md)
