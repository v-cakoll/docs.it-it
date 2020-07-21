---
title: 'Mitigazione: Supporto di tocco e stilo basato su puntatore'
description: Informazioni sugli effetti dell'abilitazione di uno stack di tocco/stilo WPF facoltativo per le app WPF destinate a .NET Framework 4,7.
ms.date: 04/07/2017
helpviewer_keywords:
- retargeting changes
- .NET Framework 4.7 retargeting changes
- WPF retargeting changes
- WPF pointer-based touch and stylus stack
ms.assetid: f99126b5-c396-48f9-8233-8f36b4c9e717
ms.openlocfilehash: d0c0effeaa727c615dddc3b92cdd34aafde65705
ms.sourcegitcommit: cf5a800a33de64d0aad6d115ffcc935f32375164
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/20/2020
ms.locfileid: "86475424"
---
# <a name="mitigation-pointer-based-touch-and-stylus-support"></a><span data-ttu-id="3f6cc-103">Mitigazione: Supporto di tocco e stilo basato su puntatore</span><span class="sxs-lookup"><span data-stu-id="3f6cc-103">Mitigation: Pointer-based Touch and Stylus Support</span></span>

<span data-ttu-id="3f6cc-104">Le applicazioni WPF destinate a .NET Framework 4,7 e sono in esecuzione in Windows a partire da Windows 10 Creators Update possono abilitare uno `WM_POINTER` stack di tocco/stilo WPF basato su facoltativo.</span><span class="sxs-lookup"><span data-stu-id="3f6cc-104">WPF applications that target the .NET Framework 4.7 and are running on Windows starting with Windows 10 Creators Update can enable an optional `WM_POINTER`-based WPF touch/stylus stack.</span></span>

## <a name="impact"></a><span data-ttu-id="3f6cc-105">Impatto</span><span class="sxs-lookup"><span data-stu-id="3f6cc-105">Impact</span></span>

<span data-ttu-id="3f6cc-106">Gli sviluppatori che non attivano in modo esplicito il supporto tocco/stilo basato su puntatore non dovrebbero riscontrare alcuna modifica nel comportamento di tocco/stilo WPF.</span><span class="sxs-lookup"><span data-stu-id="3f6cc-106">Developers who do not explicitly enable pointer-based touch/stylus support should see no change in WPF touch/stylus behavior.</span></span>

<span data-ttu-id="3f6cc-107">Di seguito sono riportati problemi noti correnti con lo stack tocco/stilo basato su `WM_POINTER`:</span><span class="sxs-lookup"><span data-stu-id="3f6cc-107">The following are current known issues with the optional `WM_POINTER`-based touch/stylus stack:</span></span>

- <span data-ttu-id="3f6cc-108">Nessun supporto per l'input penna in tempo reale.</span><span class="sxs-lookup"><span data-stu-id="3f6cc-108">No support for real-time inking.</span></span>

   <span data-ttu-id="3f6cc-109">Anche se i plug-in della stilo e dell'input penna continuano a funzionare, essi vengono elaborati nel thread dell'interfaccia utente, il che può comportare un peggioramento delle prestazioni.</span><span class="sxs-lookup"><span data-stu-id="3f6cc-109">While inking and stylus plugins still work, they are processed on the UI thread, which can lead to poor performance.</span></span>

- <span data-ttu-id="3f6cc-110">Modifiche del comportamento dovuti alla promozione da eventi di tocco/stilo agli eventi del mouse.</span><span class="sxs-lookup"><span data-stu-id="3f6cc-110">Behavioral changes due to changes in promotion from touch/stylus events to mouse events.</span></span>

  - <span data-ttu-id="3f6cc-111">La modifica potrebbe avere un comportamento diverso.</span><span class="sxs-lookup"><span data-stu-id="3f6cc-111">Manipulation may behave differently.</span></span>

  - <span data-ttu-id="3f6cc-112">L'opzione Trascina selezione non dà la risposta appropriata per l'input tocco.</span><span class="sxs-lookup"><span data-stu-id="3f6cc-112">Drag/Drop will not show appropriate feedback for touch input.</span></span> <span data-ttu-id="3f6cc-113">(Questa operazione non influisce sull'input della stilo.)</span><span class="sxs-lookup"><span data-stu-id="3f6cc-113">(This does not affect stylus input.)</span></span>

  - <span data-ttu-id="3f6cc-114">L'opzione Trascina selezione non può essere avviata per gli eventi di tocco/stilo.</span><span class="sxs-lookup"><span data-stu-id="3f6cc-114">Drag/Drop can no longer be initiated on touch/stylus events.</span></span>

      <span data-ttu-id="3f6cc-115">Questo può potenzialmente bloccare l'applicazione fino a quando non viene rilevato l'input del mouse.</span><span class="sxs-lookup"><span data-stu-id="3f6cc-115">This can potentially cause the application to become unresponsive until mouse input is detected.</span></span> <span data-ttu-id="3f6cc-116">Gli sviluppatori dovranno quindi avviare l'opzione di trascinamento della selezione dagli eventi del mouse.</span><span class="sxs-lookup"><span data-stu-id="3f6cc-116">Instead, developers should initiate drag and drop from mouse events.</span></span>

## <a name="opting-in-to-wm_pointer-based-touchstylus-support"></a><span data-ttu-id="3f6cc-117">Consenso esplicito al supporto di tocco/stilo basato su WM_POINTER</span><span class="sxs-lookup"><span data-stu-id="3f6cc-117">Opting in to WM_POINTER-based touch/stylus support</span></span>

<span data-ttu-id="3f6cc-118">Gli sviluppatori che desiderano abilitare questo stack possono aggiungere quanto segue al file di *app.config* dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="3f6cc-118">Developers who wish to enable this stack can add the following to their application's *app.config* file.</span></span>

```xml
<configuration>
    <runtime>
        <AppContextSwitchOverrides value="Switch.System.Windows.Input.Stylus.EnablePointerSupport=true"/>
    </runtime>
</configuration>
```

<span data-ttu-id="3f6cc-119">Rimuovendo questa voce o impostandone il valore su `false`, questo stack facoltativo viene disattivato.</span><span class="sxs-lookup"><span data-stu-id="3f6cc-119">Removing this entry or setting its value to `false` turns this optional stack off.</span></span>

## <a name="see-also"></a><span data-ttu-id="3f6cc-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3f6cc-120">See also</span></span>

- [<span data-ttu-id="3f6cc-121">Compatibilità tra le versioni</span><span class="sxs-lookup"><span data-stu-id="3f6cc-121">Application compatibility</span></span>](application-compatibility.md)
