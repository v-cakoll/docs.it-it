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
# <a name="how-to-define-a-table-with-xaml"></a>Procedura: Definire un oggetto Table tramite XAML
Nell'esempio seguente viene illustrato come definire un <xref:System.Windows.Documents.Table> utilizzando [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].  La tabella di esempio contiene quattro colonne (rappresentato da <xref:System.Windows.Documents.TableColumn> elementi) e più righe (rappresentati da <xref:System.Windows.Documents.TableRow> elementi) che contengono dati anche come titolo, intestazione e piè di pagina informazioni.  Le righe devono essere contenute un <xref:System.Windows.Documents.TableRowGroup> elemento.  Ogni riga della tabella è costituita da una o più celle (rappresentato da <xref:System.Windows.Documents.TableCell> elementi).  Contenuto in una cella della tabella deve essere contenuto in un <xref:System.Windows.Documents.Block> elemento, in questo caso <xref:System.Windows.Documents.Paragraph> vengono utilizzati gli elementi.  La tabella ospita anche un collegamento ipertestuale (rappresentato dal <xref:System.Windows.Documents.Hyperlink> elemento) nella riga di piè di pagina.  
  
## <a name="example"></a>Esempio  
 [!code-xaml[TableSnippetsXAML#_TableXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippetsXAML/CS/Window1.xaml#_tablexaml)]  
  
 Nella figura seguente viene illustrato il rendering della tabella definita in questo esempio.  
  
 ![Tabella sottoposta a rendering.](../../../../docs/framework/wpf/advanced/media/tableeg.png "TableEG")
