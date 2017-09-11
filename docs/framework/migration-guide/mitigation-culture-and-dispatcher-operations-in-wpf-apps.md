---
title: 'Mitigazione: Impostazioni cultura e operazioni asincrone in app WPF'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-bcl
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 455c1452-8ce0-45ae-a092-21fb8edf1cac
caps.latest.revision: 3
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 41fc52679884d547809f1c1e9f47e29eb668cb8e
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="mitigation-culture-and-dispatcher-operations-in-wpf-apps"></a><span data-ttu-id="450e2-102">Mitigazione: Impostazioni cultura e operazioni asincrone in app WPF</span><span class="sxs-lookup"><span data-stu-id="450e2-102">Mitigation: Culture and Dispatcher Operations in WPF Apps</span></span>
<span data-ttu-id="450e2-103">Nelle app destinate a .NET Framework 4.6 e .NET Framework 4.6.1 le modifiche alla proprietà <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> o <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName> eseguite all'interno di <xref:System.Windows.Threading.Dispatcher> vengono perse al termine dell'operazione di Dispatcher.</span><span class="sxs-lookup"><span data-stu-id="450e2-103">In apps that target the .NET Framework 4.6 and the .NET Framework 4.6.1, changes to the <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> or <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName> properties that are made within a <xref:System.Windows.Threading.Dispatcher> are lost at the end of that dispatcher operation.</span></span> <span data-ttu-id="450e2-104">In modo analogo, le modifiche apportate a <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> o <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName> all'esterno di un'operazione di Dispatcher potrebbero non essere disponibili quando viene eseguita l'operazione.</span><span class="sxs-lookup"><span data-stu-id="450e2-104">Similarly, changes to <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> or <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName> made outside of a dispatcher operation may not be reflected when that operation executes.</span></span>  
  
 <span data-ttu-id="450e2-105">Questo è dovuto a una modifica in <xref:System.Threading.ExecutionContext> che determina l'archiviazione di <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> e <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName> nel contesto di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="450e2-105">This is due to a change in <xref:System.Threading.ExecutionContext> that causes the <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> and <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName> to be stored in the execution context.</span></span> <span data-ttu-id="450e2-106">Le operazioni del dispatcher WPF archiviano il contesto di esecuzione usato per avviare l'operazione e ripristinano il contesto precedente dopo il completamento dell'operazione.</span><span class="sxs-lookup"><span data-stu-id="450e2-106">WPF dispatcher operations store the execution context used to begin the operation and restore the previous context when the operation is completed.</span></span> <span data-ttu-id="450e2-107">Dato che <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> e <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName> fanno ora parte di tale contesto, le modifiche di questi elementi all'interno di un'operazione di Dispatcher non vengono mantenute all'esterno dell'operazione.</span><span class="sxs-lookup"><span data-stu-id="450e2-107">Because <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> and <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName> are now part of that context, changes to them within a dispatcher operation are not persisted outside of the operation.</span></span>  
  
## <a name="impact"></a><span data-ttu-id="450e2-108">Impatto</span><span class="sxs-lookup"><span data-stu-id="450e2-108">Impact</span></span>  
 <span data-ttu-id="450e2-109">In pratica, questo significa che le modifiche apportate alle proprietà <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> e <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName> potrebbero non essere trasferite tra i callback dell'interfaccia utente di WPF e altro codice in un'applicazione WPF.</span><span class="sxs-lookup"><span data-stu-id="450e2-109">Practically, this means that changes to the <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> and  <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName> properties may not flow between WPF UI callbacks and other code in a WPF application.</span></span>  
  
## <a name="mitigation"></a><span data-ttu-id="450e2-110">Mitigazione</span><span class="sxs-lookup"><span data-stu-id="450e2-110">Mitigation</span></span>  
 <span data-ttu-id="450e2-111">Le app interessate da questa modifica possono aggirare il problema in uno dei due modi:</span><span class="sxs-lookup"><span data-stu-id="450e2-111">Apps affected by this change may work around it in either of two ways:</span></span>  
  
-   <span data-ttu-id="450e2-112">archiviando i valori <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> o <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName> desiderati in un campo e controllando che siano impostati i valori corretti di <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> o <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName> in tutti i corpi delle operazioni di <xref:System.Windows.Threading.Dispatcher> (inclusi i gestori di callback degli eventi dell'interfaccia utente).</span><span class="sxs-lookup"><span data-stu-id="450e2-112">By storing the desired <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> or  <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName> in a field and checking in all <xref:System.Windows.Threading.Dispatcher> operation bodies (including UI event callback handlers) that the correct <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> or  <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName> is set.</span></span>  
  
-   <span data-ttu-id="450e2-113">Poiché la modifica alla proprietà <xref:System.Threading.ExecutionContext> interessa solo le applicazioni WPF destinate a .NET Framework 4.6 o a .NET Framework 4.6.1, tale modifica può essere evitata impostando come destinazione .NET Framework 4.5.2 o a una versione di .NET Framework a partire dalla 4.6.2.</span><span class="sxs-lookup"><span data-stu-id="450e2-113">Because the change to <xref:System.Threading.ExecutionContext> only affects WPF apps that target the .NET Framework 4.6 or the .NET Framework 4.6.1, this change can be avoided by targeting the .NET Framework 4.5.2 or by targeting a version of the .NET Framework starting with 4.6.2.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="450e2-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="450e2-114">See Also</span></span>  
 [<span data-ttu-id="450e2-115">Modifiche di reindirizzamento</span><span class="sxs-lookup"><span data-stu-id="450e2-115">Retargeting Changes</span></span>](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-6.md)

