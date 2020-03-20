---
title: Funzione ForwardTranslateAccelerator - riferimento all'API non gestita WPF
titleSuffix: ''
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ForwardTranslateAccelerator
api_location:
- PresentationHost_v0400.dll
ms.assetid: fff47a86-9d9f-4176-9530-10e1876e393f
ms.openlocfilehash: a0a01be3000dc53df7855cb74015ba1164206838
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186626"
---
# <a name="forwardtranslateaccelerator-function-wpf-unmanaged-api-reference"></a><span data-ttu-id="5fb01-102">ForwardTranslateAccelerator Function (WPF Unmanaged API Reference)</span><span class="sxs-lookup"><span data-stu-id="5fb01-102">ForwardTranslateAccelerator Function (WPF Unmanaged API Reference)</span></span>
<span data-ttu-id="5fb01-103">Questa API supporta l'infrastruttura Windows Presentation Foundation (WPF) e non può essere utilizzata direttamente dal codice.</span><span class="sxs-lookup"><span data-stu-id="5fb01-103">This API supports the Windows Presentation Foundation (WPF) infrastructure and is not intended to be used directly from your code.</span></span>  
  
 <span data-ttu-id="5fb01-104">Utilizzato dall'infrastruttura di Windows Presentation Foundation (WPF) per la gestione delle finestre.</span><span class="sxs-lookup"><span data-stu-id="5fb01-104">Used by the Windows Presentation Foundation (WPF) infrastructure for windows management.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5fb01-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5fb01-105">Syntax</span></span>  
  
```cpp  
HRESULT ForwardTranslateAccelerator(  
   MSG* pMsg,
   VARIANT_BOOL appUnhandled  
)  
```  
  
## <a name="parameters"></a><span data-ttu-id="5fb01-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="5fb01-106">Parameters</span></span>  
 <span data-ttu-id="5fb01-107">pMsg</span><span class="sxs-lookup"><span data-stu-id="5fb01-107">pMsg</span></span>  
 <span data-ttu-id="5fb01-108">Puntatore a un messaggio.</span><span class="sxs-lookup"><span data-stu-id="5fb01-108">A pointer to a message.</span></span>  
  
 <span data-ttu-id="5fb01-109">appNon gestito</span><span class="sxs-lookup"><span data-stu-id="5fb01-109">appUnhandled</span></span>  
 <span data-ttu-id="5fb01-110">`true`quando all'app è già stata data la possibilità di gestire il messaggio di input, ma non l'ha gestito; in `false`caso contrario, .</span><span class="sxs-lookup"><span data-stu-id="5fb01-110">`true` when the app has already been given a chance to handle the input message, but has not handled it; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5fb01-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="5fb01-111">Requirements</span></span>  
 <span data-ttu-id="5fb01-112">**Piattaforme:** Vedere Requisiti di sistema [di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5fb01-112">**Platforms:** See [.NET Framework System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5fb01-113">**DLL:**</span><span class="sxs-lookup"><span data-stu-id="5fb01-113">**DLL:**</span></span>  
  
 <span data-ttu-id="5fb01-114">In .NET Framework 3.0 e 3.5: PresentationHostDLL.dll</span><span class="sxs-lookup"><span data-stu-id="5fb01-114">In the .NET Framework 3.0 and 3.5: PresentationHostDLL.dll</span></span>  
  
 <span data-ttu-id="5fb01-115">In .NET Framework 4 e versioni successive: PresentationHost_v0400.dll</span><span class="sxs-lookup"><span data-stu-id="5fb01-115">In the .NET Framework 4 and later: PresentationHost_v0400.dll</span></span>  
  
 <span data-ttu-id="5fb01-116">**Versione di .NET Framework:**[!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5fb01-116">**.NET Framework Version:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5fb01-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5fb01-117">See also</span></span>

- [<span data-ttu-id="5fb01-118">Riferimenti alle API non gestite WPF</span><span class="sxs-lookup"><span data-stu-id="5fb01-118">WPF Unmanaged API Reference</span></span>](wpf-unmanaged-api-reference.md)
