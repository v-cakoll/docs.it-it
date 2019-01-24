---
title: Funzione Activate (riferimenti alle API WPF non gestite)
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- Acrivate
api_location:
- PresentationHost_v0400.dll
ms.assetid: 1400329c-b598-465f-80f2-e3dabf044811
ms.openlocfilehash: 4e79b74dc8bb7d57125c27e17e8f52d607fffcf1
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54721989"
---
# <a name="activate-function-wpf-unmanaged-api-reference"></a><span data-ttu-id="5dae4-102">Funzione Activate (riferimenti alle API WPF non gestite)</span><span class="sxs-lookup"><span data-stu-id="5dae4-102">Activate Function (WPF Unmanaged API Reference)</span></span>
<span data-ttu-id="5dae4-103">Questa API supporta l'infrastruttura Windows Presentation Foundation (WPF) e non deve essere usato direttamente dal codice.</span><span class="sxs-lookup"><span data-stu-id="5dae4-103">This API supports the Windows Presentation Foundation (WPF) infrastructure and is not intended to be used directly from your code.</span></span>  
  
 <span data-ttu-id="5dae4-104">Utilizzata dall'infrastruttura Windows Presentation Foundation (WPF) per la gestione di windows.</span><span class="sxs-lookup"><span data-stu-id="5dae4-104">Used by the Windows Presentation Foundation (WPF) infrastructure for windows management.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5dae4-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5dae4-105">Syntax</span></span>  
  
```cpp  
void Activate(  
    const ActivateParameters* pParameters,  
    __deref_out_ecount(1) LPUNKNOWN* ppInner,  
    );  
```  
  
#### <a name="parameters"></a><span data-ttu-id="5dae4-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="5dae4-106">Parameters</span></span>  
 <span data-ttu-id="5dae4-107">pParameters</span><span class="sxs-lookup"><span data-stu-id="5dae4-107">pParameters</span></span>  
 <span data-ttu-id="5dae4-108">Puntatore a parametri di attivazione della finestra.</span><span class="sxs-lookup"><span data-stu-id="5dae4-108">A pointer to the window's activation parameters.</span></span>  
  
 <span data-ttu-id="5dae4-109">ppInner</span><span class="sxs-lookup"><span data-stu-id="5dae4-109">ppInner</span></span>  
 <span data-ttu-id="5dae4-110">Un puntatore all'indirizzo di un buffer a elemento singolo che contiene un puntatore a un <xref:Microsoft.VisualStudio.OLE.Interop.IOleDocument> oggetto.</span><span class="sxs-lookup"><span data-stu-id="5dae4-110">A pointer to the address of a single-element buffer that contains a pointer to an <xref:Microsoft.VisualStudio.OLE.Interop.IOleDocument> object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5dae4-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="5dae4-111">Requirements</span></span>  
 <span data-ttu-id="5dae4-112">**Piattaforme:** Visualizzare [requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5dae4-112">**Platforms:** See [.NET Framework System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5dae4-113">**DLL:**</span><span class="sxs-lookup"><span data-stu-id="5dae4-113">**DLL:**</span></span>  
  
 <span data-ttu-id="5dae4-114">In .NET Framework 3.0 e 3.5: PresentationHostDLL.dll</span><span class="sxs-lookup"><span data-stu-id="5dae4-114">In the .NET Framework 3.0 and 3.5: PresentationHostDLL.dll</span></span>  
  
 <span data-ttu-id="5dae4-115">In .NET Framework 4 e versioni successive: PresentationHost_v0400.dll</span><span class="sxs-lookup"><span data-stu-id="5dae4-115">In the .NET Framework 4 and later: PresentationHost_v0400.dll</span></span>  
  
 <span data-ttu-id="5dae4-116">**Versione di .NET framework:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5dae4-116">**.NET Framework Version:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5dae4-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5dae4-117">See also</span></span>
- [<span data-ttu-id="5dae4-118">Riferimenti alle API non gestite di WPF</span><span class="sxs-lookup"><span data-stu-id="5dae4-118">WPF Unmanaged API Reference</span></span>](../../../../docs/framework/wpf/advanced/wpf-unmanaged-api-reference.md)
