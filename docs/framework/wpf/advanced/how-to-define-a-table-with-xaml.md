---
title: 'Procedura: Definire un oggetto Table tramite XAML'
ms.date: 03/30/2017
helpviewer_keywords:
- XAML [WPF], defining tables
- documents [WPF], defining tables with XAML
- tables [WPF], defining with XAML
ms.assetid: 83f2dc58-437e-4cdc-b5dd-0019810c7a85
ms.openlocfilehash: 2a35a27567d962fc125cb3c408ccab95afa222af
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33543101"
---
# <a name="how-to-define-a-table-with-xaml"></a><span data-ttu-id="e05c7-102">Procedura: Definire un oggetto Table tramite XAML</span><span class="sxs-lookup"><span data-stu-id="e05c7-102">How to: Define a Table with XAML</span></span>
<span data-ttu-id="e05c7-103">Nell'esempio seguente viene illustrato come definire un <xref:System.Windows.Documents.Table> utilizzando [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e05c7-103">The following example demonstrates how to define a <xref:System.Windows.Documents.Table> using [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].</span></span>  <span data-ttu-id="e05c7-104">La tabella di esempio contiene quattro colonne (rappresentato da <xref:System.Windows.Documents.TableColumn> elementi) e più righe (rappresentati da <xref:System.Windows.Documents.TableRow> elementi) che contengono dati anche come titolo, intestazione e piè di pagina informazioni.</span><span class="sxs-lookup"><span data-stu-id="e05c7-104">The example table has four columns (represented by <xref:System.Windows.Documents.TableColumn> elements) and several rows (represented by <xref:System.Windows.Documents.TableRow> elements) containing data as well as title, header, and footer information.</span></span>  <span data-ttu-id="e05c7-105">Le righe devono essere contenute un <xref:System.Windows.Documents.TableRowGroup> elemento.</span><span class="sxs-lookup"><span data-stu-id="e05c7-105">Rows must be contained in a <xref:System.Windows.Documents.TableRowGroup> element.</span></span>  <span data-ttu-id="e05c7-106">Ogni riga della tabella è costituita da una o più celle (rappresentato da <xref:System.Windows.Documents.TableCell> elementi).</span><span class="sxs-lookup"><span data-stu-id="e05c7-106">Each row in the table is comprised of one or more cells (represented by <xref:System.Windows.Documents.TableCell> elements).</span></span>  <span data-ttu-id="e05c7-107">Contenuto in una cella della tabella deve essere contenuto in un <xref:System.Windows.Documents.Block> elemento, in questo caso <xref:System.Windows.Documents.Paragraph> vengono utilizzati gli elementi.</span><span class="sxs-lookup"><span data-stu-id="e05c7-107">Content in a table cell must be contained in a <xref:System.Windows.Documents.Block> element; in this case <xref:System.Windows.Documents.Paragraph> elements are used.</span></span>  <span data-ttu-id="e05c7-108">La tabella ospita anche un collegamento ipertestuale (rappresentato dal <xref:System.Windows.Documents.Hyperlink> elemento) nella riga di piè di pagina.</span><span class="sxs-lookup"><span data-stu-id="e05c7-108">The table also hosts a hyperlink (represented by the <xref:System.Windows.Documents.Hyperlink> element) in the footer row.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e05c7-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="e05c7-109">Example</span></span>  
 [!code-xaml[TableSnippetsXAML#_TableXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippetsXAML/CS/Window1.xaml#_tablexaml)]  
  
 <span data-ttu-id="e05c7-110">Nella figura seguente viene illustrato il rendering della tabella definita in questo esempio.</span><span class="sxs-lookup"><span data-stu-id="e05c7-110">The following figure shows how the table defined in this example renders.</span></span>  
  
 <span data-ttu-id="e05c7-111">![Tabella sottoposta a rendering.](../../../../docs/framework/wpf/advanced/media/tableeg.png "TableEG")</span><span class="sxs-lookup"><span data-stu-id="e05c7-111">![Rendered table.](../../../../docs/framework/wpf/advanced/media/tableeg.png "TableEG")</span></span>
