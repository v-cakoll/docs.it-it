---
title: 'Procedura: Definire un oggetto Table tramite XAML'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- XAML [WPF], defining tables
- documents [WPF], defining tables with XAML
- tables [WPF], defining with XAML
ms.assetid: 83f2dc58-437e-4cdc-b5dd-0019810c7a85
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 350dff0b6ea9d92e919e45e4f46cf888f44f6212
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-define-a-table-with-xaml"></a>Procedura: Definire un oggetto Table tramite XAML
Nell'esempio seguente viene illustrato come definire un <xref:System.Windows.Documents.Table> utilizzando [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].  La tabella di esempio contiene quattro colonne (rappresentato da <xref:System.Windows.Documents.TableColumn> elementi) e più righe (rappresentati da <xref:System.Windows.Documents.TableRow> elementi) che contengono dati anche come titolo, intestazione e piè di pagina informazioni.  Le righe devono essere contenute un <xref:System.Windows.Documents.TableRowGroup> elemento.  Ogni riga della tabella è costituita da una o più celle (rappresentato da <xref:System.Windows.Documents.TableCell> elementi).  Contenuto in una cella della tabella deve essere contenuto in un <xref:System.Windows.Documents.Block> elemento, in questo caso <xref:System.Windows.Documents.Paragraph> vengono utilizzati gli elementi.  La tabella ospita anche un collegamento ipertestuale (rappresentato dal <xref:System.Windows.Documents.Hyperlink> elemento) nella riga di piè di pagina.  
  
## <a name="example"></a>Esempio  
 [!code-xaml[TableSnippetsXAML#_TableXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippetsXAML/CS/Window1.xaml#_tablexaml)]  
  
 Nella figura seguente viene illustrato il rendering della tabella definita in questo esempio.  
  
 ![Tabella sottoposta a rendering.](../../../../docs/framework/wpf/advanced/media/tableeg.png "TableEG")
