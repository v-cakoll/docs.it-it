---
title: "Procedura: eseguire l'associazione a un servizio Web"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- binding data [WPF], Web service
- Web service binding [WPF]
- data binding [WPF], Web service
ms.assetid: 77e2d373-69ba-4cbd-b6f5-2c83c38fc98b
ms.openlocfilehash: 3a3f6edc974448ddab9fe30e97bdc1130d3b97dc
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "77449972"
---
# <a name="how-to-bind-to-a-web-service"></a>Procedura: eseguire l'associazione a un servizio Web
In questo esempio viene illustrato come eseguire l'associazione a oggetti restituiti dalle chiamate al metodo del servizio Web.  
  
## <a name="example"></a>Esempio  
 In questo esempio viene utilizzato il servizio contenuto MTPS (MSDN/TechNet Publishing System) per recuperare l'elenco delle lingue supportate da un documento specificato.  
  
 Prima di chiamare un servizio Web, è necessario crearvi un riferimento. Per creare un riferimento Web al servizio MTPS con Visual Studio, attenersi alla procedura seguente:  
  
1. Apri il progetto in Visual Studio.  
  
2. Scegliere **Aggiungi riferimento Web**dal menu **progetto** .  
  
3. Nella finestra di dialogo impostare l' **URL** su [http://services.msdn.microsoft.com/contentservices/contentservice.asmx?wsdl](https://services.msdn.microsoft.com/contentservices/contentservice.asmx?wsdl).  
  
4. Premere **go** e quindi **Aggiungi riferimento**.  
  
 Chiamare quindi il metodo del servizio Web e impostare l'<xref:System.Windows.FrameworkElement.DataContext%2A> del controllo o della finestra appropriata sull'oggetto restituito. Il `GetContent` metodo del servizio MTPS accetta un riferimento all'oggetto `getContentRequest`. Di conseguenza, l'esempio seguente configura prima di tutto un oggetto Request:  
  
 [!code-csharp[BindToWebService#Namespace](~/samples/snippets/csharp/VS_Snippets_Wpf/BindToWebService/CSharp/Window1.xaml.cs#namespace)]
 [!code-vb[BindToWebService#Namespace](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BindToWebService/VisualBasic/Window1.xaml.vb#namespace)]  
[!code-csharp[BindToWebService#WebServiceCall](~/samples/snippets/csharp/VS_Snippets_Wpf/BindToWebService/CSharp/Window1.xaml.cs#webservicecall)]
[!code-vb[BindToWebService#WebServiceCall](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BindToWebService/VisualBasic/Window1.xaml.vb#webservicecall)]  
  
 Una volta impostato il <xref:System.Windows.FrameworkElement.DataContext%2A>, è possibile creare binding per le proprietà dell'oggetto su cui è stato impostato il <xref:System.Windows.FrameworkElement.DataContext%2A>. In questo esempio, il <xref:System.Windows.FrameworkElement.DataContext%2A> viene impostato sull'oggetto `getContentResponse` restituito dal metodo `GetContent`. Nell'esempio seguente, il <xref:System.Windows.Controls.ItemsControl> viene associato a e Visualizza i valori di `locale` di `availableVersionsAndLocales` di `getContentResponse`.  
  
 [!code-xaml[BindToWebService#Binding](~/samples/snippets/csharp/VS_Snippets_Wpf/BindToWebService/CSharp/Window1.xaml#binding)]  
  
 Per informazioni sulla struttura di `getContentResponse`, vedere la [documentazione del servizio contenuto](https://services.msdn.microsoft.com/ContentServices/ContentService.asmx).  
  
## <a name="see-also"></a>Vedere anche

- [Panoramica sul data binding](../../../desktop-wpf/data/data-binding-overview.md)
- [Panoramica delle origini di associazione](binding-sources-overview.md)
- [Rendere i dati disponibili per l'associazione in XAML](how-to-make-data-available-for-binding-in-xaml.md)
