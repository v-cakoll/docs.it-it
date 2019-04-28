---
title: 'Procedura: Definire una tabella tramite XAML'
ms.date: 03/30/2017
helpviewer_keywords:
- XAML [WPF], defining tables
- documents [WPF], defining tables with XAML
- tables [WPF], defining with XAML
ms.assetid: 83f2dc58-437e-4cdc-b5dd-0019810c7a85
ms.openlocfilehash: 011f612527f0c9e89ec05643edbb95b2d908488c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61776583"
---
# <a name="how-to-define-a-table-with-xaml"></a>Procedura: Definire una tabella tramite XAML
Nell'esempio seguente viene illustrato come definire un <xref:System.Windows.Documents.Table> usando [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].  La tabella di esempio contiene quattro colonne (rappresentato da <xref:System.Windows.Documents.TableColumn> elementi) e più righe (rappresentato da <xref:System.Windows.Documents.TableRow> elementi) che contengono dati anche a titolo, intestazione e piè di pagina informazioni.  Le righe devono essere contenute in un <xref:System.Windows.Documents.TableRowGroup> elemento.  Ogni riga nella tabella è costituita da uno o più celle (rappresentato da <xref:System.Windows.Documents.TableCell> elementi).  Contenuto di una cella della tabella deve essere contenuto in un <xref:System.Windows.Documents.Block> elemento; in questo caso <xref:System.Windows.Documents.Paragraph> gli elementi vengono usati.  La tabella ospita anche un collegamento ipertestuale (rappresentato dal <xref:System.Windows.Documents.Hyperlink> elemento) nella riga del piè di pagina.  
  
## <a name="example"></a>Esempio  
 [!code-xaml[TableSnippetsXAML#_TableXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippetsXAML/CS/Window1.xaml#_tablexaml)]  
  
 La figura seguente mostra come la tabella definita in questo esempio viene eseguito il rendering:  
  
 ![Screenshot di una tabella definita con XAML.](./media/how-to-define-a-table-with-xaml/planetary-information-xaml-table.png)
