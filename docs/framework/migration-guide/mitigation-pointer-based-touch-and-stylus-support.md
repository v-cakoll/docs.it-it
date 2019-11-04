---
title: 'Mitigazione: Supporto di tocco e stilo basato su puntatore'
ms.date: 04/07/2017
helpviewer_keywords:
- retargeting changes
- .NET Framework 4.7 retargeting changes
- WPF retargeting changes
- WPF pointer-based touch and stylus stack
ms.assetid: f99126b5-c396-48f9-8233-8f36b4c9e717
ms.openlocfilehash: 6b3e8068be2f5ed82c483b760fe100ea0a751588
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/03/2019
ms.locfileid: "73457867"
---
# <a name="mitigation-pointer-based-touch-and-stylus-support"></a><span data-ttu-id="c3a84-102">Mitigazione: Supporto di tocco e stilo basato su puntatore</span><span class="sxs-lookup"><span data-stu-id="c3a84-102">Mitigation: Pointer-based Touch and Stylus Support</span></span>

<span data-ttu-id="c3a84-103">Le applicazioni WPF destinate a .NET Framework 4.7 e che sono in esecuzione nei sistemi Windows a partire da Windows 10 Creators Update possono abilitare lo stack facoltativo di tocco/stilo basato su `WM_POINTER`.</span><span class="sxs-lookup"><span data-stu-id="c3a84-103">WPF applications that target the .NET Framework 4.7 and are running on Windows Systems starting with Windows 10 Creators Update can enable an optional `WM_POINTER`-based WPF touch/stylus stack.</span></span>

## <a name="impact"></a><span data-ttu-id="c3a84-104">Impatto</span><span class="sxs-lookup"><span data-stu-id="c3a84-104">Impact</span></span>

<span data-ttu-id="c3a84-105">Gli sviluppatori che non attivano in modo esplicito il supporto tocco/stilo basato su puntatore non dovrebbero riscontrare alcuna modifica nel comportamento di tocco/stilo WPF.</span><span class="sxs-lookup"><span data-stu-id="c3a84-105">Developers who do not explicitly enable pointer-based touch/stylus support should see no change in WPF touch/stylus behavior.</span></span>

<span data-ttu-id="c3a84-106">Di seguito sono riportati problemi noti correnti con lo stack tocco/stilo basato su `WM_POINTER`:</span><span class="sxs-lookup"><span data-stu-id="c3a84-106">The following are current known issues with the optional `WM_POINTER`-based touch/stylus stack:</span></span>

- <span data-ttu-id="c3a84-107">Nessun supporto per l'input penna in tempo reale.</span><span class="sxs-lookup"><span data-stu-id="c3a84-107">No support for real-time inking.</span></span>

   <span data-ttu-id="c3a84-108">Anche se i plug-in della stilo e dell'input penna continuano a funzionare, essi vengono elaborati nel thread dell'interfaccia utente, il che può comportare un peggioramento delle prestazioni.</span><span class="sxs-lookup"><span data-stu-id="c3a84-108">While inking and stylus plugins still work, they are processed on the UI thread, which can lead to poor performance.</span></span>

- <span data-ttu-id="c3a84-109">Modifiche del comportamento dovuti alla promozione da eventi di tocco/stilo agli eventi del mouse.</span><span class="sxs-lookup"><span data-stu-id="c3a84-109">Behavioral changes due to changes in promotion from touch/stylus events to mouse events.</span></span>

  - <span data-ttu-id="c3a84-110">La modifica potrebbe avere un comportamento diverso.</span><span class="sxs-lookup"><span data-stu-id="c3a84-110">Manipulation may behave differently.</span></span>

  - <span data-ttu-id="c3a84-111">L'opzione Trascina selezione non dà la risposta appropriata per l'input tocco.</span><span class="sxs-lookup"><span data-stu-id="c3a84-111">Drag/Drop will not show appropriate feedback for touch input.</span></span> <span data-ttu-id="c3a84-112">(Questa operazione non influisce sull'input della stilo.)</span><span class="sxs-lookup"><span data-stu-id="c3a84-112">(This does not affect stylus input.)</span></span>

  - <span data-ttu-id="c3a84-113">L'opzione Trascina selezione non può essere avviata per gli eventi di tocco/stilo.</span><span class="sxs-lookup"><span data-stu-id="c3a84-113">Drag/Drop can no longer be initiated on touch/stylus events.</span></span>

      <span data-ttu-id="c3a84-114">Questo può potenzialmente bloccare l'applicazione fino a quando non viene rilevato l'input del mouse.</span><span class="sxs-lookup"><span data-stu-id="c3a84-114">This can potentially cause the application to become unresponsive until mouse input is detected.</span></span> <span data-ttu-id="c3a84-115">Gli sviluppatori dovranno quindi avviare l'opzione di trascinamento della selezione dagli eventi del mouse.</span><span class="sxs-lookup"><span data-stu-id="c3a84-115">Instead, developers should initiate drag and drop from mouse events.</span></span>

## <a name="opting-in-to-wm_pointer-based-touchstylus-support"></a><span data-ttu-id="c3a84-116">Consenso esplicito al supporto di tocco/stilo basato su WM_POINTER</span><span class="sxs-lookup"><span data-stu-id="c3a84-116">Opting in to WM_POINTER-based touch/stylus support</span></span>

<span data-ttu-id="c3a84-117">Gli sviluppatori che desiderano abilitare questo stack possono aggiungere quanto segue al file app.config dell'applicazione:</span><span class="sxs-lookup"><span data-stu-id="c3a84-117">Developers who wish to enable this stack can add the following to their application's app.config file:</span></span>

```xml
<configuration>
    <runtime>
        <AppContextSwitchOverrides value="Switch.System.Windows.Input.Stylus.EnablePointerSupport=true"/>
    </runtime>
</configuration>
```

<span data-ttu-id="c3a84-118">Rimuovendo questa voce o impostandone il valore su `false`, questo stack facoltativo viene disattivato.</span><span class="sxs-lookup"><span data-stu-id="c3a84-118">Removing this entry or setting its value to `false` turns this optional stack off.</span></span>

## <a name="see-also"></a><span data-ttu-id="c3a84-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c3a84-119">See also</span></span>

- [<span data-ttu-id="c3a84-120">Compatibilità delle applicazioni</span><span class="sxs-lookup"><span data-stu-id="c3a84-120">Application compatibility</span></span>](application-compatibility.md)
