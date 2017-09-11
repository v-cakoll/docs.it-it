---
title: 'Mitigazione: Allocazione dello spazio di controllo della griglia alle colonne a stella'
ms.custom: 
ms.date: 04/07/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- retargeting changes
- .NET Framework 4.7 retargeting changes
- WPF retargeting changes
- Grid control retargeting changes
ms.assetid: 707c064d-85e9-4ea1-aefb-e42b60b88679
caps.latest.revision: 4
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 54391538ac0b2daf307cba2f7ceff1984d26b0ce
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="mitigation-grid-control39s-space-allocation-to-star-columns"></a><span data-ttu-id="8ec07-102">Mitigazione: Allocazione dello spazio di controllo della griglia alle colonne a stella</span><span class="sxs-lookup"><span data-stu-id="8ec07-102">Mitigation: Grid Control&#39;s Space Allocation to Star-columns</span></span>

<span data-ttu-id="8ec07-103">A partire dalle applicazioni destinate a .NET Framework 4.7, WPF sostituisce l'algoritmo usato dal controllo <xref:System.Windows.Controls.Grid> per allocare spazio alle colonne \*.</span><span class="sxs-lookup"><span data-stu-id="8ec07-103">Starting with applications that the .NET Framework 4.7, WPF replaces the algorithm that the <xref:System.Windows.Controls.Grid> control uses to allocate space to \*-columns.</span></span> 

## <a name="whats-changed"></a><span data-ttu-id="8ec07-104">Novità</span><span class="sxs-lookup"><span data-stu-id="8ec07-104">What's changed</span></span>

<span data-ttu-id="8ec07-105">Il nuovo algoritmo consente di risolvere diversi bug presenti nell'algoritmo precedente:</span><span class="sxs-lookup"><span data-stu-id="8ec07-105">The new algorithm fixes several bugs present in the old algorithm:</span></span>

1. <span data-ttu-id="8ec07-106">L'allocazione totale alle colonne può superare la larghezza della griglia.</span><span class="sxs-lookup"><span data-stu-id="8ec07-106">Total allocation to columns can exceed the Grid's width.</span></span> <span data-ttu-id="8ec07-107">Ciò può verificarsi quando si alloca spazio a una colonna la cui quota proporzionale è minore rispetto alle dimensioni minime.</span><span class="sxs-lookup"><span data-stu-id="8ec07-107">This can occur when allocating space to a column whose proportional share is less than its minimum size.</span></span> <span data-ttu-id="8ec07-108">L'algoritmo alloca le dimensioni minime, riducendo lo spazio disponibile per le altre colonne.</span><span class="sxs-lookup"><span data-stu-id="8ec07-108">The algorithm allocates the minimum size, which decreases the space available to other columns.</span></span> <span data-ttu-id="8ec07-109">Se non sono presenti colonne \* da allocare, l'allocazione totale potrebbe essere troppo grande.</span><span class="sxs-lookup"><span data-stu-id="8ec07-109">If there are no \*-columns left to allocate, the total allocation will be too large.</span></span>

1. <span data-ttu-id="8ec07-110">L'allocazione totale può non raggiungere la larghezza della griglia.</span><span class="sxs-lookup"><span data-stu-id="8ec07-110">Total allocation can fall short of the Grid's width.</span></span> <span data-ttu-id="8ec07-111">Questo è il doppio problema di # 1, che si verifica quando si effettua l'allocazione a una colonna la cui quota proporzionale è maggiore rispetto alle sue dimensioni massime, senza alcuna colonna \* per sfruttare la flessibilità.</span><span class="sxs-lookup"><span data-stu-id="8ec07-111">This is the dual problem to #1, arising when allocating to a column whose proportional share is greater than its maximum size, with no \*-columns left to take up the slack.</span></span>

1. <span data-ttu-id="8ec07-112">Due colonne \* possono ricevere le allocazioni in modo non proporzionale ai loro pesi.</span><span class="sxs-lookup"><span data-stu-id="8ec07-112">Two \*-columns can receive allocations not proportional to their -weights.</span></span> <span data-ttu-id="8ec07-113">Questa è una versione più lieve di #1/#2, che si verifica durante l'allocazione alle colonne * A, B e C (in questo ordine), dove la quota proporzionale di B viola il suo vincolo min o max.</span><span class="sxs-lookup"><span data-stu-id="8ec07-113">This is a milder version of #1/#2, arising when allocating to *-columns A, B, and C (in that order), where B's proportional share violates its min (or max) constraint.</span></span> <span data-ttu-id="8ec07-114">Come in precedenza, lo spazio disponibile alla colonna C si riduce e questa ottiene un'allocazione proporzionale inferiore o superiore rispetto ad A,</span><span class="sxs-lookup"><span data-stu-id="8ec07-114">As above, this changes the space available to column C, who gets less (or more) proportional allocation than A did,</span></span>

1. <span data-ttu-id="8ec07-115">Le colonne con pesi estremamente alti (> 10^298) vengono considerate tutte come se avessero un peso di 10^298.</span><span class="sxs-lookup"><span data-stu-id="8ec07-115">Columns with extremely large weights (> 10^298) are all treated as if they had weight 10^298.</span></span> <span data-ttu-id="8ec07-116">Le differenze proporzionali tra di esse (e tra le colonne con pesi leggermente inferiori) non vengono rispettate.</span><span class="sxs-lookup"><span data-stu-id="8ec07-116">Proportional differences between them (and between columns with slightly smaller weights) are not honored.</span></span>

1. <span data-ttu-id="8ec07-117">Le colonne con pesi infiniti non vengono gestite correttamente.</span><span class="sxs-lookup"><span data-stu-id="8ec07-117">Columns with infinite weights are not handled correctly.</span></span> <span data-ttu-id="8ec07-118">[In realtà non è possibile impostare un peso su infinito, ma si tratta di una limitazione artificiale.</span><span class="sxs-lookup"><span data-stu-id="8ec07-118">[Actually you can't set a weight to Infinity, but this is an artificial restriction.</span></span> <span data-ttu-id="8ec07-119">Il codice di allocazione stava tentando di gestirlo, ma in un processo non valido.]</span><span class="sxs-lookup"><span data-stu-id="8ec07-119">The allocation code was trying to handle it, but doing a bad job.]</span></span>

1. <span data-ttu-id="8ec07-120">Diversi problemi minori mentre si evita l'overflow, l'underflow, la perdita di precisione e altri problemi analoghi della virgola mobile.</span><span class="sxs-lookup"><span data-stu-id="8ec07-120">Several minor problems while avoiding overflow, underflow, loss of precision and similar floating-point issues.</span></span>

1. <span data-ttu-id="8ec07-121">Le modifiche per l'arrotondamento del layout con un DPI sufficientemente elevato non sono corrette.</span><span class="sxs-lookup"><span data-stu-id="8ec07-121">Adjustments for layout rounding are incorrect at sufficiently high DPI.</span></span>

<span data-ttu-id="8ec07-122">Il nuovo algoritmo produce risultati che soddisfano i criteri seguenti:</span><span class="sxs-lookup"><span data-stu-id="8ec07-122">The new algorithm produces results that meet the following criteria:</span></span>

<span data-ttu-id="8ec07-123">Un </span><span class="sxs-lookup"><span data-stu-id="8ec07-123">A.</span></span> <span data-ttu-id="8ec07-124">La larghezza effettiva assegnata a una colonna * non è mai minore della larghezza minima né maggiore della larghezza massima.</span><span class="sxs-lookup"><span data-stu-id="8ec07-124">The actual width assigned to a *-column is never less than its minimum width nor greater than its maximum width.</span></span>

<span data-ttu-id="8ec07-125">B.</span><span class="sxs-lookup"><span data-stu-id="8ec07-125">B.</span></span> <span data-ttu-id="8ec07-126">A ogni colonna a cui non è assegnata la larghezza minima o massima è assegnata una larghezza proporzionale al relativo peso.</span><span class="sxs-lookup"><span data-stu-id="8ec07-126">Each -column that is not assigned its minimum or maximum width is assigned a width proportional to its -weight.</span></span> <span data-ttu-id="8ec07-127">Per essere precisi, se si dichiara che due colonne hanno rispettivamente una larghezza x e y e se nessuna delle colonne riceve la larghezza minima o massima, le larghezze effettive v e w assegnate alle colonne hanno la stessa proporzione: v / w == x / y.</span><span class="sxs-lookup"><span data-stu-id="8ec07-127">To be precise, if two columns are declared with width x and y respectively, and if neither column receives its minimum or maximum width, the actual widths v and w assigned to the columns are in the same proportion: v / w == x / y.</span></span>

<span data-ttu-id="8ec07-128">C.</span><span class="sxs-lookup"><span data-stu-id="8ec07-128">C.</span></span> <span data-ttu-id="8ec07-129">La larghezza totale allocata alle colonne \* proporzionali è uguale allo spazio disponibile dopo avere effettuato l'allocazione alle colonne vincolate (fisse, automatiche e colonne \* che vengono allocate alla loro larghezza min o max).</span><span class="sxs-lookup"><span data-stu-id="8ec07-129">The total width allocated to "proportional" \*-columns is equal to the space available after allocating to the constrained columns (fixed, auto, and \*-columns that are allocated their min or max width).</span></span> <span data-ttu-id="8ec07-130">Potrebbe essere pari a zero, ad esempio se la somma delle larghezze minime è superiore alla larghezza disponibile della griglia.</span><span class="sxs-lookup"><span data-stu-id="8ec07-130">This might be zero, for instance if the sum of the minimum widths exceeds the Grid's availbable width.</span></span>

<span data-ttu-id="8ec07-131">D.</span><span class="sxs-lookup"><span data-stu-id="8ec07-131">D.</span></span> <span data-ttu-id="8ec07-132">Tutte queste istruzioni devono essere interpretate in base al layout "ideale".</span><span class="sxs-lookup"><span data-stu-id="8ec07-132">All these statements are to be interpreted with respect to the "ideal" layout.</span></span> <span data-ttu-id="8ec07-133">Quando l'arrotondamento del layout è attivo, le larghezze effettive possono differire dalle larghezze ideali per un massimo di un pixel.</span><span class="sxs-lookup"><span data-stu-id="8ec07-133">When layout rounding is in effect, the actual widths can differ from the ideal widths by as much as one pixel.</span></span>

<span data-ttu-id="8ec07-134">L'algoritmo precedente rispettava (A) ma non gli altri criteri nei casi descritti in precedenza.</span><span class="sxs-lookup"><span data-stu-id="8ec07-134">The old algorithm honored (A) but failed to honor the other criteria in the cases outlined above.</span></span>

<span data-ttu-id="8ec07-135">Quanto detto sulle colonne e le relative larghezze in questo argomento si applica anche a righe e altezza.</span><span class="sxs-lookup"><span data-stu-id="8ec07-135">Everything said about columns and widths in this topic applies as well to rows and heights.</span></span>

## <a name="impact"></a><span data-ttu-id="8ec07-136">Impatto</span><span class="sxs-lookup"><span data-stu-id="8ec07-136">Impact</span></span>

<span data-ttu-id="8ec07-137">Il nuovo algoritmo modifica la larghezza effettiva assegnata alle colonne \* in diversi casi:</span><span class="sxs-lookup"><span data-stu-id="8ec07-137">The new algorithm changes the actual width assigned to \*-columns in a number of cases:</span></span>

- <span data-ttu-id="8ec07-138">Quando una o più colonne \* hanno anche una larghezza minima o massima che esegue l'override dell'allocazione proporzionale per tale colonna.</span><span class="sxs-lookup"><span data-stu-id="8ec07-138">When one or more \*-columns also have a minimum or maximum width that overrides the proportional allocation for that column.</span></span> <span data-ttu-id="8ec07-139">(La larghezza minima può derivare da una dichiarazione esplicita <xref:System.Windows.FrameworkElement.MinWidth%2A> o da un minimo implicito ottenuto dal contenuto della colonna.</span><span class="sxs-lookup"><span data-stu-id="8ec07-139">(The minimum width can derive from an explicit <xref:System.Windows.FrameworkElement.MinWidth%2A> declaration, or from an implicit minimum obtained from the column's content.</span></span> <span data-ttu-id="8ec07-140">La larghezza massima può essere definita solo in modo esplicito da una dichiarazione <xref:System.Windows.FrameworkElement.MaxWidth%2A>.)</span><span class="sxs-lookup"><span data-stu-id="8ec07-140">The maximum width can only be defined explicitly, from a <xref:System.Windows.FrameworkElement.MaxWidth%2A> declaration.)</span></span>

- <span data-ttu-id="8ec07-141">Quando una o più colonne \* dichiarano un peso \* estremamente elevato, maggiore di 10^298.</span><span class="sxs-lookup"><span data-stu-id="8ec07-141">When one or more \*-columns declare an extremely large \*-weight, greater than 10^298.</span></span>

- <span data-ttu-id="8ec07-142">Quando i pesi \* sono diversi al punto da far sì che si verifichi un'instabilità a virgola mobile (overflow, underflow, perdita di precisione).</span><span class="sxs-lookup"><span data-stu-id="8ec07-142">When the \*-weights are sufficiently different to encounter floating-point instability (overflow, underflow, loss of precision).</span></span>

- <span data-ttu-id="8ec07-143">Quando è abilitato l'arrotondamento del layout e il DPI effettivamente visualizzato è sufficientemente elevato.</span><span class="sxs-lookup"><span data-stu-id="8ec07-143">When layout rounding is enabled, and the effective display DPI is sufficiently high.</span></span>

<span data-ttu-id="8ec07-144">Nei primi due casi, le larghezze generate dal nuovo algoritmo possono essere notevolmente diverse da quelle generate dal vecchio algoritmo; nell'ultimo caso, la differenza sarà di uno o due pixel al massimo.</span><span class="sxs-lookup"><span data-stu-id="8ec07-144">In the first two cases, the widths produced by the new algorithm can be significantly different from those produced by the old algorithm; in the last case, the difference will be at most one or two pixels.</span></span>

## <a name="mitigation"></a><span data-ttu-id="8ec07-145">Attenuazione</span><span class="sxs-lookup"><span data-stu-id="8ec07-145">Mitigation</span></span>

<span data-ttu-id="8ec07-146">Per impostazione predefinita, le applicazioni destinate alle versioni di .NET Framework a partire dalla 4.7 useranno il nuovo algoritmo, mentre le applicazioni destinate a .NET Framework 4.6.2 o versioni precedenti useranno il vecchio algoritmo.</span><span class="sxs-lookup"><span data-stu-id="8ec07-146">By default, apps that target versions of the .NET Framework starting with the .NET Framework 4.7 will use the new algorithm, while apps that target the .NET Framework 4.6.2 or earlier versions will use the old algorithm.</span></span>

<span data-ttu-id="8ec07-147">Per ignorare l'impostazione predefinita, usare l'impostazione di configurazione seguente:</span><span class="sxs-lookup"><span data-stu-id="8ec07-147">To override the default, use the following configuration setting:</span></span>

```xml
<runtime>
    <AppContextSwitchOverrides value="Switch.System.Windows.Controls.Grid.StarDefinitionsCanExceedAvailableSpace=true" /> 
</runtime>
```

<span data-ttu-id="8ec07-148">Tramite il valore 'true' è possibile selezionare il vecchio algoritmo, mentre con 'false' è possibile selezionare il nuovo algoritmo.</span><span class="sxs-lookup"><span data-stu-id="8ec07-148">The value 'true' selects the old algorithm, and 'false' selects the new algorithm.</span></span>

## <a name="see-also"></a><span data-ttu-id="8ec07-149">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8ec07-149">See also</span></span>
[<span data-ttu-id="8ec07-150">Retargeting Changes in the .NET Framework 4.7 (Reindirizzamento delle modifiche in .NET Framework 4.7)</span><span class="sxs-lookup"><span data-stu-id="8ec07-150">Retargeting Changes in the .NET Framework 4.7</span></span>](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-7.md)

