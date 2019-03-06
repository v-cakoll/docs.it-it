---
title: 'Procedura: Definire un oggetto Table tramite XAML'
ms.date: 03/30/2017
helpviewer_keywords:
- XAML [WPF], defining tables
- documents [WPF], defining tables with XAML
- tables [WPF], defining with XAML
ms.assetid: 83f2dc58-437e-4cdc-b5dd-0019810c7a85
ms.openlocfilehash: 7398af6fddae56238e1af3ee4e726420c01ab7ea
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/05/2019
ms.locfileid: "57376923"
---
# <a name="how-to-define-a-table-with-xaml"></a>Procedura: Definire un oggetto Table tramite XAML
Nell'esempio seguente viene illustrato come definire un <xref:System.Windows.Documents.Table> usando [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].  La tabella di esempio contiene quattro colonne (rappresentato da <xref:System.Windows.Documents.TableColumn> elementi) e più righe (rappresentato da <xref:System.Windows.Documents.TableRow> elementi) che contengono dati anche a titolo, intestazione e piè di pagina informazioni.  Le righe devono essere contenute in un <xref:System.Windows.Documents.TableRowGroup> elemento.  Ogni riga nella tabella è costituita da uno o più celle (rappresentato da <xref:System.Windows.Documents.TableCell> elementi).  Contenuto di una cella della tabella deve essere contenuto in un <xref:System.Windows.Documents.Block> elemento; in questo caso <xref:System.Windows.Documents.Paragraph> gli elementi vengono usati.  La tabella ospita anche un collegamento ipertestuale (rappresentato dal <xref:System.Windows.Documents.Hyperlink> elemento) nella riga del piè di pagina.  
  
## <a name="example"></a>Esempio  
 [!code-xaml[TableSnippetsXAML#_TableXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippetsXAML/CS/Window1.xaml#_tablexaml)]  
  
 Nella figura seguente viene illustrato il rendering della tabella definita in questo esempio.  
  
 ![Tabella sottoposta a rendering.](./media/tableeg.png "TableEG")
