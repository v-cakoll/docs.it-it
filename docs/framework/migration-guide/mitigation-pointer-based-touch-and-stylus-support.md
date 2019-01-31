---
title: 'Mitigazione: Supporto di tocco e stilo basato su puntatore'
ms.date: 04/07/2017
helpviewer_keywords:
- retargeting changes
- .NET Framework 4.7 retargeting changes
- WPF retargeting changes
- WPF pointer-based touch and stylus stack
ms.assetid: f99126b5-c396-48f9-8233-8f36b4c9e717
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d750087cc000ad31a24d91411c0885a75d59e74f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54501945"
---
# <a name="mitigation-pointer-based-touch-and-stylus-support"></a><span data-ttu-id="35868-102">Mitigazione: Supporto di tocco e stilo basato su puntatore</span><span class="sxs-lookup"><span data-stu-id="35868-102">Mitigation: Pointer-based Touch and Stylus Support</span></span>

<span data-ttu-id="35868-103">Le applicazioni WPF destinate a .NET Framework 4.7 e che sono in esecuzione nei sistemi Windows a partire da Windows 10 Creators Update possono abilitare lo stack facoltativo di tocco/stilo basato su `WM_POINTER`.</span><span class="sxs-lookup"><span data-stu-id="35868-103">WPF applications that target the .NET Framework 4.7 and are running on Windows Systems starting with Windows 10 Creators Update can enable an optional `WM_POINTER`-based WPF touch/stylus stack.</span></span>

## <a name="impact"></a><span data-ttu-id="35868-104">Impatto</span><span class="sxs-lookup"><span data-stu-id="35868-104">Impact</span></span>

<span data-ttu-id="35868-105">Gli sviluppatori che non attivano in modo esplicito il supporto tocco/stilo basato su puntatore non dovrebbero riscontrare alcuna modifica nel comportamento di tocco/stilo WPF.</span><span class="sxs-lookup"><span data-stu-id="35868-105">Developers who do not explicitly enable pointer-based touch/stylus support should see no change in WPF touch/stylus behavior.</span></span>

<span data-ttu-id="35868-106">Di seguito sono riportati problemi noti correnti con lo stack tocco/stilo basato su `WM_POINTER`:</span><span class="sxs-lookup"><span data-stu-id="35868-106">The following are current known issues with the optional `WM_POINTER`-based touch/stylus stack:</span></span>

- <span data-ttu-id="35868-107">Nessun supporto per l'input penna in tempo reale.</span><span class="sxs-lookup"><span data-stu-id="35868-107">No support for real-time inking.</span></span>

   <span data-ttu-id="35868-108">Anche se i plug-in della stilo e dell'input penna continuano a funzionare, essi vengono elaborati nel thread dell'interfaccia utente, il che può comportare un peggioramento delle prestazioni.</span><span class="sxs-lookup"><span data-stu-id="35868-108">While inking and stylus plugins still work, they are processed on the UI thread, which can lead to poor performance.</span></span>

- <span data-ttu-id="35868-109">Modifiche del comportamento dovuti alla promozione da eventi di tocco/stilo agli eventi del mouse.</span><span class="sxs-lookup"><span data-stu-id="35868-109">Behavioral changes due to changes in promotion from touch/stylus events to mouse events.</span></span>

  - <span data-ttu-id="35868-110">La modifica potrebbe avere un comportamento diverso.</span><span class="sxs-lookup"><span data-stu-id="35868-110">Manipulation may behave differently.</span></span>

  - <span data-ttu-id="35868-111">L'opzione Trascina selezione non dà la risposta appropriata per l'input tocco.</span><span class="sxs-lookup"><span data-stu-id="35868-111">Drag/Drop will not show appropriate feedback for touch input.</span></span> <span data-ttu-id="35868-112">(Questa operazione non influisce sull'input della stilo.)</span><span class="sxs-lookup"><span data-stu-id="35868-112">(This does not affect stylus input.)</span></span>

  - <span data-ttu-id="35868-113">L'opzione Trascina selezione non può essere avviata per gli eventi di tocco/stilo.</span><span class="sxs-lookup"><span data-stu-id="35868-113">Drag/Drop can no longer be initiated on touch/stylus events.</span></span>

      <span data-ttu-id="35868-114">Questo può potenzialmente bloccare l'applicazione fino a quando non viene rilevato l'input del mouse.</span><span class="sxs-lookup"><span data-stu-id="35868-114">This can potentially hang the application until mouse input is detected.</span></span> <span data-ttu-id="35868-115">Gli sviluppatori dovranno quindi avviare l'opzione di trascinamento della selezione dagli eventi del mouse.</span><span class="sxs-lookup"><span data-stu-id="35868-115">Instead, developers should initiate drag and drop from mouse events.</span></span>

## <a name="opting-in-to-wmpointer-based-touchstylus-support"></a><span data-ttu-id="35868-116">Consenso esplicito al supporto di tocco/stilo basato su WM_POINTER</span><span class="sxs-lookup"><span data-stu-id="35868-116">Opting in to WM_POINTER-based touch/stylus support</span></span>

<span data-ttu-id="35868-117">Gli sviluppatori che desiderano abilitare questo stack possono aggiungere quanto segue al file app.config dell'applicazione:</span><span class="sxs-lookup"><span data-stu-id="35868-117">Developers who wish to enable this stack can add the following to their application's app.config file:</span></span>

```xml
<configuration>
    <runtime>
        <AppContextSwitchOverrides value="Switch.System.Windows.Input.Stylus.EnablePointerSupport=true"/>
    </runtime>
</configuration>
```

<span data-ttu-id="35868-118">Rimuovendo questa voce o impostandone il valore su `false`, questo stack facoltativo viene disattivato.</span><span class="sxs-lookup"><span data-stu-id="35868-118">Removing this entry or setting its value to `false` turns this optional stack off.</span></span>

## <a name="see-also"></a><span data-ttu-id="35868-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="35868-119">See also</span></span>

- [<span data-ttu-id="35868-120">Retargeting Changes in the .NET Framework 4.7 (Reindirizzamento delle modifiche in .NET Framework 4.7)</span><span class="sxs-lookup"><span data-stu-id="35868-120">Retargeting Changes in the .NET Framework 4.7</span></span>](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-7.md)
