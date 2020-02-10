---
title: 'Mitigazione: Supporto di tocco e stilo basato su puntatore'
ms.date: 04/07/2017
helpviewer_keywords:
- retargeting changes
- .NET Framework 4.7 retargeting changes
- WPF retargeting changes
- WPF pointer-based touch and stylus stack
ms.assetid: f99126b5-c396-48f9-8233-8f36b4c9e717
ms.openlocfilehash: 023c38f66611bd0022699d3f62d90c3923585012
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/09/2020
ms.locfileid: "77094475"
---
# <a name="mitigation-pointer-based-touch-and-stylus-support"></a><span data-ttu-id="c71c4-102">Mitigazione: Supporto di tocco e stilo basato su puntatore</span><span class="sxs-lookup"><span data-stu-id="c71c4-102">Mitigation: Pointer-based Touch and Stylus Support</span></span>

<span data-ttu-id="c71c4-103">Le applicazioni WPF destinate a .NET Framework 4,7 e sono in esecuzione in Windows a partire da Windows 10 Creators Update possono abilitare uno stack di tocco/stilo WPF basato su `WM_POINTER`facoltativo.</span><span class="sxs-lookup"><span data-stu-id="c71c4-103">WPF applications that target the .NET Framework 4.7 and are running on Windows starting with Windows 10 Creators Update can enable an optional `WM_POINTER`-based WPF touch/stylus stack.</span></span>

## <a name="impact"></a><span data-ttu-id="c71c4-104">Impatto</span><span class="sxs-lookup"><span data-stu-id="c71c4-104">Impact</span></span>

<span data-ttu-id="c71c4-105">Gli sviluppatori che non attivano in modo esplicito il supporto tocco/stilo basato su puntatore non dovrebbero riscontrare alcuna modifica nel comportamento di tocco/stilo WPF.</span><span class="sxs-lookup"><span data-stu-id="c71c4-105">Developers who do not explicitly enable pointer-based touch/stylus support should see no change in WPF touch/stylus behavior.</span></span>

<span data-ttu-id="c71c4-106">Di seguito sono riportati problemi noti correnti con lo stack tocco/stilo basato su `WM_POINTER`:</span><span class="sxs-lookup"><span data-stu-id="c71c4-106">The following are current known issues with the optional `WM_POINTER`-based touch/stylus stack:</span></span>

- <span data-ttu-id="c71c4-107">Nessun supporto per l'input penna in tempo reale.</span><span class="sxs-lookup"><span data-stu-id="c71c4-107">No support for real-time inking.</span></span>

   <span data-ttu-id="c71c4-108">Anche se i plug-in della stilo e dell'input penna continuano a funzionare, essi vengono elaborati nel thread dell'interfaccia utente, il che può comportare un peggioramento delle prestazioni.</span><span class="sxs-lookup"><span data-stu-id="c71c4-108">While inking and stylus plugins still work, they are processed on the UI thread, which can lead to poor performance.</span></span>

- <span data-ttu-id="c71c4-109">Modifiche del comportamento dovuti alla promozione da eventi di tocco/stilo agli eventi del mouse.</span><span class="sxs-lookup"><span data-stu-id="c71c4-109">Behavioral changes due to changes in promotion from touch/stylus events to mouse events.</span></span>

  - <span data-ttu-id="c71c4-110">La modifica potrebbe avere un comportamento diverso.</span><span class="sxs-lookup"><span data-stu-id="c71c4-110">Manipulation may behave differently.</span></span>

  - <span data-ttu-id="c71c4-111">L'opzione Trascina selezione non dà la risposta appropriata per l'input tocco.</span><span class="sxs-lookup"><span data-stu-id="c71c4-111">Drag/Drop will not show appropriate feedback for touch input.</span></span> <span data-ttu-id="c71c4-112">(Questa operazione non influisce sull'input della stilo.)</span><span class="sxs-lookup"><span data-stu-id="c71c4-112">(This does not affect stylus input.)</span></span>

  - <span data-ttu-id="c71c4-113">L'opzione Trascina selezione non può essere avviata per gli eventi di tocco/stilo.</span><span class="sxs-lookup"><span data-stu-id="c71c4-113">Drag/Drop can no longer be initiated on touch/stylus events.</span></span>

      <span data-ttu-id="c71c4-114">Questo può potenzialmente bloccare l'applicazione fino a quando non viene rilevato l'input del mouse.</span><span class="sxs-lookup"><span data-stu-id="c71c4-114">This can potentially cause the application to become unresponsive until mouse input is detected.</span></span> <span data-ttu-id="c71c4-115">Gli sviluppatori dovranno quindi avviare l'opzione di trascinamento della selezione dagli eventi del mouse.</span><span class="sxs-lookup"><span data-stu-id="c71c4-115">Instead, developers should initiate drag and drop from mouse events.</span></span>

## <a name="opting-in-to-wm_pointer-based-touchstylus-support"></a><span data-ttu-id="c71c4-116">Consenso esplicito al supporto di tocco/stilo basato su WM_POINTER</span><span class="sxs-lookup"><span data-stu-id="c71c4-116">Opting in to WM_POINTER-based touch/stylus support</span></span>

<span data-ttu-id="c71c4-117">Gli sviluppatori che desiderano abilitare questo stack possono aggiungere quanto segue al file *app. config* dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="c71c4-117">Developers who wish to enable this stack can add the following to their application's *app.config* file.</span></span>

```xml
<configuration>
    <runtime>
        <AppContextSwitchOverrides value="Switch.System.Windows.Input.Stylus.EnablePointerSupport=true"/>
    </runtime>
</configuration>
```

<span data-ttu-id="c71c4-118">Rimuovendo questa voce o impostandone il valore su `false`, questo stack facoltativo viene disattivato.</span><span class="sxs-lookup"><span data-stu-id="c71c4-118">Removing this entry or setting its value to `false` turns this optional stack off.</span></span>

## <a name="see-also"></a><span data-ttu-id="c71c4-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c71c4-119">See also</span></span>

- [<span data-ttu-id="c71c4-120">Compatibilità delle applicazioni</span><span class="sxs-lookup"><span data-stu-id="c71c4-120">Application compatibility</span></span>](application-compatibility.md)
