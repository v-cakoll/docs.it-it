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
ms.openlocfilehash: 6410b05a1b858a7b75c9bff3220d47505beabd7c
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/05/2019
ms.locfileid: "57357274"
---
# <a name="activate-function-wpf-unmanaged-api-reference"></a><span data-ttu-id="64537-102">Funzione Activate (riferimenti alle API WPF non gestite)</span><span class="sxs-lookup"><span data-stu-id="64537-102">Activate Function (WPF Unmanaged API Reference)</span></span>
<span data-ttu-id="64537-103">Questa API supporta l'infrastruttura Windows Presentation Foundation (WPF) e non deve essere usato direttamente dal codice.</span><span class="sxs-lookup"><span data-stu-id="64537-103">This API supports the Windows Presentation Foundation (WPF) infrastructure and is not intended to be used directly from your code.</span></span>  
  
 <span data-ttu-id="64537-104">Utilizzata dall'infrastruttura Windows Presentation Foundation (WPF) per la gestione di windows.</span><span class="sxs-lookup"><span data-stu-id="64537-104">Used by the Windows Presentation Foundation (WPF) infrastructure for windows management.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="64537-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="64537-105">Syntax</span></span>  
  
```cpp  
void Activate(  
    const ActivateParameters* pParameters,  
    __deref_out_ecount(1) LPUNKNOWN* ppInner,  
    );  
```  
  
#### <a name="parameters"></a><span data-ttu-id="64537-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="64537-106">Parameters</span></span>  
 <span data-ttu-id="64537-107">pParameters</span><span class="sxs-lookup"><span data-stu-id="64537-107">pParameters</span></span>  
 <span data-ttu-id="64537-108">Puntatore a parametri di attivazione della finestra.</span><span class="sxs-lookup"><span data-stu-id="64537-108">A pointer to the window's activation parameters.</span></span>  
  
 <span data-ttu-id="64537-109">ppInner</span><span class="sxs-lookup"><span data-stu-id="64537-109">ppInner</span></span>  
 <span data-ttu-id="64537-110">Un puntatore all'indirizzo di un buffer a elemento singolo che contiene un puntatore a un <xref:Microsoft.VisualStudio.OLE.Interop.IOleDocument> oggetto.</span><span class="sxs-lookup"><span data-stu-id="64537-110">A pointer to the address of a single-element buffer that contains a pointer to an <xref:Microsoft.VisualStudio.OLE.Interop.IOleDocument> object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="64537-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="64537-111">Requirements</span></span>  
 <span data-ttu-id="64537-112">**Piattaforme:** Visualizzare [requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="64537-112">**Platforms:** See [.NET Framework System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="64537-113">**DLL:**</span><span class="sxs-lookup"><span data-stu-id="64537-113">**DLL:**</span></span>  
  
 <span data-ttu-id="64537-114">In .NET Framework 3.0 e 3.5: PresentationHostDLL.dll</span><span class="sxs-lookup"><span data-stu-id="64537-114">In the .NET Framework 3.0 and 3.5: PresentationHostDLL.dll</span></span>  
  
 <span data-ttu-id="64537-115">In .NET Framework 4 e versioni successive: PresentationHost_v0400.dll</span><span class="sxs-lookup"><span data-stu-id="64537-115">In the .NET Framework 4 and later: PresentationHost_v0400.dll</span></span>  
  
 <span data-ttu-id="64537-116">**Versione di .NET framework:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="64537-116">**.NET Framework Version:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="64537-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="64537-117">See also</span></span>
- [<span data-ttu-id="64537-118">Riferimenti alle API non gestite di WPF</span><span class="sxs-lookup"><span data-stu-id="64537-118">WPF Unmanaged API Reference</span></span>](wpf-unmanaged-api-reference.md)
