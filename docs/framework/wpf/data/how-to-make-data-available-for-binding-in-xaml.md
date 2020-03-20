---
title: "Procedura: rendere i dati disponibili per l'associazione in XAML"
ms.date: 01/29/2018
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data binding [WPF], making data available for binding
- binding data [WPF], making data available for
ms.assetid: 7103c2e8-0e31-4a13-bf12-ca382221a8d5
ms.openlocfilehash: 91e89dbf36024c31f4afcd9b6d956944baf13576
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79174186"
---
# <a name="how-to-make-data-available-for-binding-in-xaml"></a>Procedura: rendere i dati disponibili per l'associazione in XAML
In questo argomento vengono illustrati i vari [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]modi in cui è possibile rendere i dati disponibili per l'associazione in , a seconda delle esigenze dell'applicazione.  
  
## <a name="example"></a>Esempio  
 Se si dispone di un oggetto Common Language Runtime [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)](CLR) a cui si desidera eseguire l'associazione da , `x:Key`un modo per rendere l'oggetto disponibile per l'associazione consiste nel definirlo come risorsa e assegnargli un' estensione . Nell'esempio seguente si `Person` dispone di un `PersonName`oggetto con una proprietà stringa denominata . L'oggetto `Person` (nella riga evidenziata `<src>` che contiene l'elemento) è definito nello spazio dei nomi denominato `SDKSample`.  
  
 [!code-xaml[SimpleBinding#Instantiation](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleBinding/CSharp/Page1.xaml?highlight=9,37)]  
  
 È quindi possibile <xref:System.Windows.Controls.TextBlock> associare il [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]controllo all'oggetto in `<TextBlock>` , come illustrato nella riga evidenziata che contiene l'elemento .
  
 In alternativa, è <xref:System.Windows.Data.ObjectDataProvider> possibile utilizzare la classe, come nell'esempio seguente:Alternatively, you can use the class, as in the following example:  
  
 [!code-xaml[ObjectDataProvider}](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleBinding/VisualBasic/Page1.xaml?highlight=10-14,42)]  
  
 L'associazione viene definita nello stesso modo, `<TextBlock>` come viene visualizzata la riga evidenziata che contiene l'elemento.  
  
 In questo particolare esempio, il risultato <xref:System.Windows.Controls.TextBlock> è lo `Joe`stesso: si dispone di un con il contenuto di testo . Tuttavia, <xref:System.Windows.Data.ObjectDataProvider> la classe fornisce funzionalità, ad esempio la possibilità di associare al risultato di un metodo. È possibile scegliere <xref:System.Windows.Data.ObjectDataProvider> di utilizzare la classe se è necessaria la funzionalità che fornisce.  
  
 Tuttavia, se si esegue l'associazione a un oggetto `DataContext` che è già stato creato, è necessario impostare il nel codice, come nell'esempio seguente.  
  
 [!code-csharp[ADODataSet#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ADODataSet/CSharp/Window1.xaml.cs#1)]
 [!code-vb[ADODataSet#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ADODataSet/VisualBasic/Window1.xaml.vb#1)]  
  
 Per accedere ai dati <xref:System.Windows.Data.XmlDataProvider> XML per l'associazione mediante la classe, vedere [Associazione a dati XML tramite un XMLDataProvider e query XPath](how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md). Per accedere ai dati <xref:System.Windows.Data.ObjectDataProvider> XML per l'associazione tramite la classe, vedere [Associare a XDocument, XElement o LINQ per i risultati](how-to-bind-to-xdocument-xelement-or-linq-for-xml-query-results.md)delle query XML.  
  
 Per informazioni sui molti modi in cui è possibile specificare i dati a cui si esegue l'associazione, vedere [Specificare l'origine dell'associazione](how-to-specify-the-binding-source.md). Per informazioni sui tipi di dati a cui è possibile eseguire l'associazione o su come implementare oggetti CLR (Common Language Runtime) personalizzati per l'associazione, vedere [Cenni preliminari](binding-sources-overview.md)sulle origini di associazione .  
  
## <a name="see-also"></a>Vedere anche

- [Cenni preliminari sull'associazione dati](../../../desktop-wpf/data/data-binding-overview.md)
- [Argomenti relativi alle procedure](data-binding-how-to-topics.md)
