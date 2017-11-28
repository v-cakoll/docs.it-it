---
title: 'Procedura: eseguire l''associazione a un servizio Web'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- binding data [WPF], Web service
- Web service binding [WPF]
- data binding [WPF], Web service
ms.assetid: 77e2d373-69ba-4cbd-b6f5-2c83c38fc98b
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 5d1b81949d6d91420c828564debd311af47dfdfd
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-bind-to-a-web-service"></a>Procedura: eseguire l'associazione a un servizio Web
In questo esempio viene illustrato come associare gli oggetti restituiti dalle chiamate al metodo del servizio Web.  
  
## <a name="example"></a>Esempio  
 Questo esempio viene utilizzato il [servizio contenuto MSDN o TechNet Publishing System (MTPS)](http://go.microsoft.com/fwlink/?LinkId=95677) per recuperare l'elenco delle lingue supportate da un documento specificato.  
  
 Prima di chiamare un servizio Web, è necessario creare un riferimento a esso. Per creare un riferimento Web al servizio MTPS utilizzando [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)], seguire i passaggi seguenti:  
  
1.  Aprire il progetto in [!INCLUDE[TLA2#tla_visualstu](../../../../includes/tla2sharptla-visualstu-md.md)].  
  
2.  Dal **progetto** menu, fare clic su **Aggiungi riferimento Web**.  
  
3.  Nella finestra di dialogo, impostare il **URL** a [http://services.msdn.microsoft.com/contentservices/contentservice.asmx?wsdl](http://services.msdn.microsoft.com/contentservices/contentservice.asmx?wsdl).  
  
4.  Premere **passare** e quindi **aggiungere riferimento**.  
  
 Successivamente, si chiama il metodo del servizio Web e impostare il <xref:System.Windows.FrameworkElement.DataContext%2A> appropriati del controllo o la finestra per l'oggetto restituito. Il **GetContent** metodo del servizio MTPS accetta un riferimento di **getContentRequest** oggetto. Pertanto, l'esempio seguente imposta prima di tutto un oggetto della richiesta:  
  
 [!code-csharp[BindToWebService#Namespace](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BindToWebService/CSharp/Window1.xaml.cs#namespace)]
 [!code-vb[BindToWebService#Namespace](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BindToWebService/VisualBasic/Window1.xaml.vb#namespace)]  
[!code-csharp[BindToWebService#WebServiceCall](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BindToWebService/CSharp/Window1.xaml.cs#webservicecall)]
[!code-vb[BindToWebService#WebServiceCall](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BindToWebService/VisualBasic/Window1.xaml.vb#webservicecall)]  
  
 Dopo il <xref:System.Windows.FrameworkElement.DataContext%2A> è stato impostato, è possibile creare associazioni per le proprietà dell'oggetto di <xref:System.Windows.FrameworkElement.DataContext%2A> è stata impostata su. In questo esempio, il <xref:System.Windows.FrameworkElement.DataContext%2A> è impostato sul **getContentResponse** oggetto restituito dal **GetContent** metodo. Nell'esempio seguente, il <xref:System.Windows.Controls.ItemsControl> viene associato e visualizza il **delle impostazioni locali** valori di **availableVersionsAndLocales** di **getContentResponse**.  
  
 [!code-xaml[BindToWebService#Binding](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BindToWebService/CSharp/Window1.xaml#binding)]  
  
 Per informazioni sulla struttura di **getContentResponse**, vedere [Content Service documentation](http://services.msdn.microsoft.com/ContentServices/ContentService.asmx).  
  
## <a name="see-also"></a>Vedere anche  
 [Cenni preliminari sull'associazione dati](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [Panoramica delle origini di associazione](../../../../docs/framework/wpf/data/binding-sources-overview.md)  
 [Rendere i dati disponibili per l'associazione in XAML](../../../../docs/framework/wpf/data/how-to-make-data-available-for-binding-in-xaml.md)
