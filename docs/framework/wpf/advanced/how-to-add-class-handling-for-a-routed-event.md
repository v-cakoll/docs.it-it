---
title: 'Procedura: aggiungere la gestione di classi per un evento indirizzato'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- routed events [WPF], class handlers
- task_core_add_class_handling_routed_properties [WPF]
- class handlers [WPF], routed events
ms.assetid: 15b7b06c-9112-4ee5-b30a-65d10c5c5df6
ms.openlocfilehash: 85c3491c9035d807b4c654659a8641121bb5709f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-add-class-handling-for-a-routed-event"></a>Procedura: aggiungere la gestione di classi per un evento indirizzato
Gli eventi indirizzati possono essere gestiti tramite gestori di classi o gestori di istanza su qualsiasi nodo specificato nella route. Gestori di classi vengono richiamati prima e utilizzabile da implementazioni della classe per eliminare gli eventi dalla gestione di istanze o introdurre altri comportamenti specifici degli eventi per gli eventi che appartengono a classi di base. In questo esempio vengono illustrate due tecniche strettamente correlate per l'implementazione di gestori di classi.  
  
## <a name="example"></a>Esempio  
 Nell'esempio viene utilizzata una classe personalizzata in base il <xref:System.Windows.Controls.Canvas> pannello. Il presupposto di base dell'applicazione è che la classe personalizzata introduce i comportamenti relativi elementi figlio, inclusi l'intercettazione di che qualsiasi pulsante sinistro del mouse e il contrassegno che li gestiti, prima che la classe di elementi figlio o eventuali gestori di istanza su di essa verranno richiamati.  
  
 Il <xref:System.Windows.UIElement> classe espone un metodo virtuale che consente la gestione nella classe di <xref:System.Windows.UIElement.PreviewMouseLeftButtonDown> eventi, sostituendo semplicemente l'evento. Questo è il modo più semplice per implementare la gestione di classi, se tale metodo virtuale è disponibile nella gerarchia delle classi. Il codice seguente illustra il <xref:System.Windows.UIElement.OnPreviewMouseLeftButtonDown%2A> implementazione in "MyEditContainer" derivato da <xref:System.Windows.Controls.Canvas>. L'implementazione contrassegna l'evento come gestito negli argomenti e quindi aggiunge codice per fornire l'elemento di origine di una modifica visibile di base.  
  
 [!code-csharp[ClassHandling#OnStarClassHandler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ClassHandling/CSharp/SDKSampleLibrary/class1.cs#onstarclasshandler)]
 [!code-vb[ClassHandling#OnStarClassHandler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ClassHandling/visualbasic/sdksamplelibrary/class1.vb#onstarclasshandler)]  
  
 Se non virtuale è disponibile sulle classi di base o per il metodo specifico, la gestione di classi è possibile aggiungere direttamente tramite un metodo di utilità del <xref:System.Windows.EventManager> (classe), <xref:System.Windows.EventManager.RegisterClassHandler%2A>. Questo metodo deve essere chiamato solo all'interno dell'inizializzazione statica delle classi che aggiungono la gestione di classi. Questo esempio viene aggiunto un altro gestore per <xref:System.Windows.UIElement.PreviewMouseLeftButtonDown> , e in questo caso la classe registrata è la classe personalizzata. Al contrario, quando l'utilizzo di virtuali, la classe registrata è effettivamente il <xref:System.Windows.UIElement> classe di base. In casi in cui le classi base e sottoclasse registrare la gestione di classi, i gestori della sottoclasse vengono richiamati prima. Si sarebbe il comportamento in un'applicazione che prima di tutto questo gestore permetterebbe di visualizzare la finestra di messaggio e quindi verranno visualizzata la modifica visiva nel gestore del metodo virtuale.  
  
 [!code-csharp[ClassHandling#StaticAndRegisterClassHandler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ClassHandling/CSharp/SDKSampleLibrary/class1.cs#staticandregisterclasshandler)]
 [!code-vb[ClassHandling#StaticAndRegisterClassHandler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ClassHandling/visualbasic/sdksamplelibrary/class1.vb#staticandregisterclasshandler)]  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.EventManager>  
 [Contrassegno degli eventi indirizzati come gestiti e gestione delle classi](../../../../docs/framework/wpf/advanced/marking-routed-events-as-handled-and-class-handling.md)  
 [Gestire un evento indirizzato](../../../../docs/framework/wpf/advanced/how-to-handle-a-routed-event.md)  
 [Cenni preliminari sugli eventi indirizzati](../../../../docs/framework/wpf/advanced/routed-events-overview.md)
