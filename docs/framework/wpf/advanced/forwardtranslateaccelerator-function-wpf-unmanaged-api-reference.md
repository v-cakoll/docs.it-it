---
title: Funzione ForwardTranslateAccelerator-informazioni di riferimento sulle API WPF non gestite
titleSuffix: ''
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ForwardTranslateAccelerator
api_location:
- PresentationHost_v0400.dll
ms.assetid: fff47a86-9d9f-4176-9530-10e1876e393f
ms.openlocfilehash: f6e8208ffe2c186234f30f31e346ca6b1d0be4c0
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76747044"
---
# <a name="forwardtranslateaccelerator-function-wpf-unmanaged-api-reference"></a><span data-ttu-id="b307c-102">Funzione ForwardTranslateAccelerator (riferimenti alle API non gestite WPF)</span><span class="sxs-lookup"><span data-stu-id="b307c-102">ForwardTranslateAccelerator Function (WPF Unmanaged API Reference)</span></span>
<span data-ttu-id="b307c-103">Questa API supporta l'infrastruttura Windows Presentation Foundation (WPF) e non può essere usata direttamente dal codice.</span><span class="sxs-lookup"><span data-stu-id="b307c-103">This API supports the Windows Presentation Foundation (WPF) infrastructure and is not intended to be used directly from your code.</span></span>  
  
 <span data-ttu-id="b307c-104">Utilizzato dall'infrastruttura Windows Presentation Foundation (WPF) per la gestione di Windows.</span><span class="sxs-lookup"><span data-stu-id="b307c-104">Used by the Windows Presentation Foundation (WPF) infrastructure for windows management.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b307c-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b307c-105">Syntax</span></span>  
  
```cpp  
HRESULT ForwardTranslateAccelerator(  
   MSG* pMsg,   
   VARIANT_BOOL appUnhandled  
)  
```  
  
## <a name="parameters"></a><span data-ttu-id="b307c-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="b307c-106">Parameters</span></span>  
 <span data-ttu-id="b307c-107">pMsg</span><span class="sxs-lookup"><span data-stu-id="b307c-107">pMsg</span></span>  
 <span data-ttu-id="b307c-108">Puntatore a un messaggio.</span><span class="sxs-lookup"><span data-stu-id="b307c-108">A pointer to a message.</span></span>  
  
 <span data-ttu-id="b307c-109">appUnhandled</span><span class="sxs-lookup"><span data-stu-id="b307c-109">appUnhandled</span></span>  
 <span data-ttu-id="b307c-110">`true` quando l'app ha già avuto la possibilità di gestire il messaggio di input, ma non lo ha gestito; in caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="b307c-110">`true` when the app has already been given a chance to handle the input message, but has not handled it; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b307c-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="b307c-111">Requirements</span></span>  
 <span data-ttu-id="b307c-112">**Piattaforme:** Vedere [.NET Framework requisiti di sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b307c-112">**Platforms:** See [.NET Framework System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b307c-113">**DLL**</span><span class="sxs-lookup"><span data-stu-id="b307c-113">**DLL:**</span></span>  
  
 <span data-ttu-id="b307c-114">Nel .NET Framework 3,0 e 3,5: PresentationHostDLL. dll</span><span class="sxs-lookup"><span data-stu-id="b307c-114">In the .NET Framework 3.0 and 3.5: PresentationHostDLL.dll</span></span>  
  
 <span data-ttu-id="b307c-115">In .NET Framework 4 e versioni successive: PresentationHost_v0400. dll</span><span class="sxs-lookup"><span data-stu-id="b307c-115">In the .NET Framework 4 and later: PresentationHost_v0400.dll</span></span>  
  
 <span data-ttu-id="b307c-116">**Versione .NET Framework:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b307c-116">**.NET Framework Version:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b307c-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b307c-117">See also</span></span>

- [<span data-ttu-id="b307c-118">Riferimenti alle API non gestite di WPF</span><span class="sxs-lookup"><span data-stu-id="b307c-118">WPF Unmanaged API Reference</span></span>](wpf-unmanaged-api-reference.md)
