---
title: Funzione Activate (riferimenti alle API WPF non gestite)
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- Activate
api_location:
- PresentationHost_v0400.dll
ms.assetid: 1400329c-b598-465f-80f2-e3dabf044811
ms.openlocfilehash: ee231653815bd5ef75d58979034e3b3be9f5ba54
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57480780"
---
# <a name="activate-function-wpf-unmanaged-api-reference"></a><span data-ttu-id="82d3b-102">Funzione Activate (riferimenti alle API WPF non gestite)</span><span class="sxs-lookup"><span data-stu-id="82d3b-102">Activate Function (WPF Unmanaged API Reference)</span></span>

<span data-ttu-id="82d3b-103">Questa API supporta l'infrastruttura Windows Presentation Foundation (WPF) e non deve essere usato direttamente dal codice.</span><span class="sxs-lookup"><span data-stu-id="82d3b-103">This API supports the Windows Presentation Foundation (WPF) infrastructure and is not intended to be used directly from your code.</span></span>

<span data-ttu-id="82d3b-104">Utilizzata dall'infrastruttura Windows Presentation Foundation (WPF) per la gestione di windows.</span><span class="sxs-lookup"><span data-stu-id="82d3b-104">Used by the Windows Presentation Foundation (WPF) infrastructure for windows management.</span></span>

## <a name="syntax"></a><span data-ttu-id="82d3b-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="82d3b-105">Syntax</span></span>

```cpp
void Activate(
    const ActivateParameters* pParameters,
    __deref_out_ecount(1) LPUNKNOWN* ppInner,
    );
```

## <a name="parameters"></a><span data-ttu-id="82d3b-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="82d3b-106">Parameters</span></span>

`pParameters`\
<span data-ttu-id="82d3b-107">Puntatore a parametri di attivazione della finestra.</span><span class="sxs-lookup"><span data-stu-id="82d3b-107">A pointer to the window's activation parameters.</span></span>

`ppInner`\
<span data-ttu-id="82d3b-108">Un puntatore all'indirizzo di un buffer a elemento singolo che contiene un puntatore a un <xref:Microsoft.VisualStudio.OLE.Interop.IOleDocument> oggetto.</span><span class="sxs-lookup"><span data-stu-id="82d3b-108">A pointer to the address of a single-element buffer that contains a pointer to an <xref:Microsoft.VisualStudio.OLE.Interop.IOleDocument> object.</span></span>

## <a name="requirements"></a><span data-ttu-id="82d3b-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="82d3b-109">Requirements</span></span>

<span data-ttu-id="82d3b-110">**Piattaforme:** Visualizzare [requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="82d3b-110">**Platforms:** See [.NET Framework System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="82d3b-111">**DLL:**</span><span class="sxs-lookup"><span data-stu-id="82d3b-111">**DLL:**</span></span>

<span data-ttu-id="82d3b-112">In .NET Framework 3.0 e 3.5: PresentationHostDLL.dll</span><span class="sxs-lookup"><span data-stu-id="82d3b-112">In the .NET Framework 3.0 and 3.5: PresentationHostDLL.dll</span></span>

<span data-ttu-id="82d3b-113">In .NET Framework 4 e versioni successive: PresentationHost_v0400.dll</span><span class="sxs-lookup"><span data-stu-id="82d3b-113">In the .NET Framework 4 and later: PresentationHost_v0400.dll</span></span>

<span data-ttu-id="82d3b-114">**Versione di .NET framework:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="82d3b-114">**.NET Framework Version:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="82d3b-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="82d3b-115">See also</span></span>

- [<span data-ttu-id="82d3b-116">Riferimenti alle API non gestite di WPF</span><span class="sxs-lookup"><span data-stu-id="82d3b-116">WPF Unmanaged API Reference</span></span>](wpf-unmanaged-api-reference.md)
