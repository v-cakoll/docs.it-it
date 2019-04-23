---
title: Esporre il contenuto di una tabella utilizzando l'automazione interfaccia utente
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- tables, exposing content of
- UI Automation, exposing content of tables
- exposing content of tables using UI Automation
ms.assetid: ac3c5eaa-49c7-4653-b83e-532e2a2604a2
ms.openlocfilehash: a9867a07207f825f3f4a781f1c05607fc6b071b9
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59174707"
---
# <a name="expose-the-content-of-a-table-using-ui-automation"></a><span data-ttu-id="3bb7f-102">Esporre il contenuto di una tabella utilizzando l'automazione interfaccia utente</span><span class="sxs-lookup"><span data-stu-id="3bb7f-102">Expose the Content of a Table Using UI Automation</span></span>
> [!NOTE]
>  <span data-ttu-id="3bb7f-103">Questa documentazione è destinata agli sviluppatori di .NET Framework che vogliono usare le classi gestite di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] definite nello spazio dei nomi <xref:System.Windows.Automation>.</span><span class="sxs-lookup"><span data-stu-id="3bb7f-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="3bb7f-104">Per informazioni aggiornate sulle [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], vedere [Windows Automation API: Automazione interfaccia utente](https://go.microsoft.com/fwlink/?LinkID=156746).</span><span class="sxs-lookup"><span data-stu-id="3bb7f-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](https://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="3bb7f-105">Questo argomento viene illustrato come [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] può essere utilizzata per esporre le proprietà intrinseche e contenute di ogni cella all'interno di un controllo tabulare.</span><span class="sxs-lookup"><span data-stu-id="3bb7f-105">This topic shows how [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] can be used to expose the content and intrinsic properties of each cell within a tabular control.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3bb7f-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="3bb7f-106">Example</span></span>  
 <span data-ttu-id="3bb7f-107">Esempio di codice seguente viene illustrato come ottenere un <xref:System.Windows.Automation.AutomationElement> che rappresenta il contenuto di una cella della tabella, sono anche ottenere le proprietà di cella, ad esempio gli indici di riga e colonna, riga e colonna intervalli e le informazioni di intestazione di riga e colonna.</span><span class="sxs-lookup"><span data-stu-id="3bb7f-107">The following code example demonstrates how to obtain a <xref:System.Windows.Automation.AutomationElement> that represents the content of a table cell; cell properties such as row and column indices, row and column spans, and row and column header information are also obtained.</span></span> <span data-ttu-id="3bb7f-108">Questo esempio Usa un gestore dell'evento di modifica dello stato attivo per simulare l'attraversamento della tastiera di un controllo in formato tabulare che implementa [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3bb7f-108">This example uses a focus change event handler to simulate keyboard traversal of a tabular control that implements [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span></span> <span data-ttu-id="3bb7f-109">Le informazioni per ogni elemento della tabella viene esposta in un evento di modifica dello stato attivo.</span><span class="sxs-lookup"><span data-stu-id="3bb7f-109">Information for each table item is exposed on a focus change event.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3bb7f-110">Poiché le modifiche dello stato attivo sono eventi globali del desktop, gli eventi di modifica dello stato attivo all'esterno della tabella devono essere filtrati.</span><span class="sxs-lookup"><span data-stu-id="3bb7f-110">Since focus changes are global desktop events, focus change events outside the table should be filtered.</span></span> <span data-ttu-id="3bb7f-111">Vedere le [TrackFocus Sample](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms771428(v=vs.90)) per un'implementazione correlata.</span><span class="sxs-lookup"><span data-stu-id="3bb7f-111">See the [TrackFocus Sample](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms771428(v=vs.90)) for a related implementation.</span></span>  
  
 [!code-csharp[UIATableItemPattern_snip#StartTarget](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIATableItemPattern_snip/CSharp/UIATableItemPattern_snippets.cs#starttarget)]
 [!code-vb[UIATableItemPattern_snip#StartTarget](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIATableItemPattern_snip/VisualBasic/UIATableItemPattern_snippets.vb#starttarget)]  
[!code-csharp[UIATableItemPattern_snip#GetTableElement](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIATableItemPattern_snip/CSharp/UIATableItemPattern_snippets.cs#gettableelement)]
[!code-vb[UIATableItemPattern_snip#GetTableElement](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIATableItemPattern_snip/VisualBasic/UIATableItemPattern_snippets.vb#gettableelement)]  
[!code-csharp[UIATableItemPattern_snip#101](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIATableItemPattern_snip/CSharp/UIATableItemPattern_snippets.cs#101)]
[!code-vb[UIATableItemPattern_snip#101](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIATableItemPattern_snip/VisualBasic/UIATableItemPattern_snippets.vb#101)]  
[!code-csharp[UIATableItemPattern_snip#1015](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIATableItemPattern_snip/CSharp/UIATableItemPattern_snippets.cs#1015)]
[!code-vb[UIATableItemPattern_snip#1015](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIATableItemPattern_snip/VisualBasic/UIATableItemPattern_snippets.vb#1015)]  
[!code-csharp[UIATableItemPattern_snip#102](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIATableItemPattern_snip/CSharp/UIATableItemPattern_snippets.cs#102)]
[!code-vb[UIATableItemPattern_snip#102](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIATableItemPattern_snip/VisualBasic/UIATableItemPattern_snippets.vb#102)]  
[!code-csharp[UIATableItemPattern_snip#103](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIATableItemPattern_snip/CSharp/UIATableItemPattern_snippets.cs#103)]
[!code-vb[UIATableItemPattern_snip#103](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIATableItemPattern_snip/VisualBasic/UIATableItemPattern_snippets.vb#103)]  
  
## <a name="see-also"></a><span data-ttu-id="3bb7f-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3bb7f-112">See also</span></span>

- [<span data-ttu-id="3bb7f-113">Panoramica dei pattern di controllo per l'automazione interfaccia utente</span><span class="sxs-lookup"><span data-stu-id="3bb7f-113">UI Automation Control Patterns Overview</span></span>](../../../docs/framework/ui-automation/ui-automation-control-patterns-overview.md)
- [<span data-ttu-id="3bb7f-114">Pattern di controllo di automazione interfaccia utente per i client</span><span class="sxs-lookup"><span data-stu-id="3bb7f-114">UI Automation Control Patterns for Clients</span></span>](../../../docs/framework/ui-automation/ui-automation-control-patterns-for-clients.md)
- [<span data-ttu-id="3bb7f-115">Implementazione del pattern di controllo Table di automazione interfaccia utente</span><span class="sxs-lookup"><span data-stu-id="3bb7f-115">Implementing the UI Automation Table Control Pattern</span></span>](../../../docs/framework/ui-automation/implementing-the-ui-automation-table-control-pattern.md)
- [<span data-ttu-id="3bb7f-116">Implementazione del pattern di controllo TableItem di automazione interfaccia utente</span><span class="sxs-lookup"><span data-stu-id="3bb7f-116">Implementing the UI Automation TableItem Control Pattern</span></span>](../../../docs/framework/ui-automation/implementing-the-ui-automation-tableitem-control-pattern.md)
- [<span data-ttu-id="3bb7f-117">Implementazione del pattern di controllo Grid di automazione interfaccia utente</span><span class="sxs-lookup"><span data-stu-id="3bb7f-117">Implementing the UI Automation Grid Control Pattern</span></span>](../../../docs/framework/ui-automation/implementing-the-ui-automation-grid-control-pattern.md)
- [<span data-ttu-id="3bb7f-118">Implementazione del pattern di controllo GridItem di automazione interfaccia utente</span><span class="sxs-lookup"><span data-stu-id="3bb7f-118">Implementing the UI Automation GridItem Control Pattern</span></span>](../../../docs/framework/ui-automation/implementing-the-ui-automation-griditem-control-pattern.md)
