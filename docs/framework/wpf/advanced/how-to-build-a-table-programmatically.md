---
title: 'Procedura: Compilare oggetti Table a livello di codice'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- tables [WPF], creating programmatically
ms.assetid: e3ca88f3-6e94-4b61-82fc-42104c10b761
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: fca6a304ea12dd90a71f8718fed5f1595f4cd4b3
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-build-a-table-programmatically"></a>Procedura: Compilare oggetti Table a livello di codice
Gli esempi seguenti mostrano come creare a livello di codice un <xref:System.Windows.Documents.Table> e popolarlo con contenuto. Il contenuto della tabella viene ripartito cinque righe (rappresentati da <xref:System.Windows.Documents.TableRow> gli oggetti contenuti un <xref:System.Windows.Documents.Table.RowGroups%2A> oggetto) e sei colonne (rappresentato da <xref:System.Windows.Documents.TableColumn> oggetti). Le righe vengono usate per scopi di presentazione diversi, ad esempio una riga è destinata a contenere il titolo dell'intera tabella, una riga di intestazione a descrivere le colonne di dati nella tabella e una riga di piè di pagina a fornire informazioni di riepilogo.  Si noti che i concetti di righe di "titolo", "intestazione" e "piè di pagina" non sono inerenti alla tabella, ma fanno semplicemente riferimento a righe con caratteristiche diverse. Le celle di tabella contengono il contenuto effettivo, che può essere costituito da testo, immagini o qualsiasi altro [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] elemento.  
  
## <a name="example"></a>Esempio  
 Prima di tutto, un <xref:System.Windows.Documents.FlowDocument> viene creato all'host di <xref:System.Windows.Documents.Table>e un nuovo <xref:System.Windows.Documents.Table> viene creato e aggiunto al contenuto del <xref:System.Windows.Documents.FlowDocument>.  
  
 [!code-csharp[TableSnippets#_TableCreate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tablecreate)]
 [!code-vb[TableSnippets#_TableCreate](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tablecreate)]  
  
## <a name="example"></a>Esempio  
 Successivamente, sei <xref:System.Windows.Documents.TableColumn> gli oggetti vengono creati e aggiunti alla tabella <xref:System.Windows.Documents.Table.Columns%2A> raccolta, con alcune formattazione applicata.  
  
> [!NOTE]
>  Si noti che la tabella <xref:System.Windows.Documents.Table.Columns%2A> insieme utilizza l'indicizzazione in base zero standard.  
  
 [!code-csharp[TableSnippets#_TableCreateColumns](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tablecreatecolumns)]
 [!code-vb[TableSnippets#_TableCreateColumns](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tablecreatecolumns)]  
  
## <a name="example"></a>Esempio  
 Viene quindi creata una riga del titolo che viene aggiunta alla tabella con l'applicazione di alcuni elementi di formattazione.  La riga del titolo può contenere una sola cella che si estende su tutte e sei le colonne della tabella.  
  
 [!code-csharp[TableSnippets#_TableAddTitleRow](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tableaddtitlerow)]
 [!code-vb[TableSnippets#_TableAddTitleRow](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tableaddtitlerow)]  
  
## <a name="example"></a>Esempio  
 Successivamente, viene creata e aggiunta alla tabella una riga di intestazione, per la quale vengono create celle in cui viene inserito contenuto.  
  
 [!code-csharp[TableSnippets#_TableAddHeaderRow](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tableaddheaderrow)]
 [!code-vb[TableSnippets#_TableAddHeaderRow](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tableaddheaderrow)]  
  
## <a name="example"></a>Esempio  
 Successivamente, viene creata e aggiunta alla tabella una riga per i dati, per la quale vengono create celle in cui viene inserito contenuto.  La compilazione di questa riga è simile alla compilazione della riga di intestazione, con l'applicazione di una formattazione leggermente diversa.  
  
 [!code-csharp[TableSnippets#_TableAddDataRow](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tableadddatarow)]
 [!code-vb[TableSnippets#_TableAddDataRow](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tableadddatarow)]  
  
## <a name="example"></a>Esempio  
 Infine, viene creata, aggiunta e formattata una riga di piè di pagina.  Analogamente alla riga del titolo, il piè di pagina contiene una sola cella che si estende su tutte e sei le colonne della tabella.  
  
 [!code-csharp[TableSnippets#_TableAddFooterRow](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tableaddfooterrow)]
 [!code-vb[TableSnippets#_TableAddFooterRow](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tableaddfooterrow)]  
  
## <a name="see-also"></a>Vedere anche  
 [Cenni preliminari sull'elemento Table](../../../../docs/framework/wpf/advanced/table-overview.md)
