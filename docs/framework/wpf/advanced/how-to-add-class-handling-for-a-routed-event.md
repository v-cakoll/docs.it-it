---
title: 'Procedura: Aggiungere la gestione di classi per un evento indirizzato'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- routed events [WPF], class handlers
- task_core_add_class_handling_routed_properties [WPF]
- class handlers [WPF], routed events
ms.assetid: 15b7b06c-9112-4ee5-b30a-65d10c5c5df6
ms.openlocfilehash: 8c973871336c3389161ce25ae52d2dfaef9c53a5
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/05/2019
ms.locfileid: "57361772"
---
# <a name="how-to-add-class-handling-for-a-routed-event"></a>Procedura: Aggiungere la gestione di classi per un evento indirizzato
Gli eventi indirizzati possono essere gestiti mediante i gestori classi o gestori dell'istanza in qualsiasi nodo specificato nella route. I gestori classi vengono richiamati per primi e utilizzabile da implementazioni della classe per eliminare gli eventi dalla gestione di istanze o introdurre altri comportamenti specifici di evento degli eventi che appartengono a classi di base. Questo esempio illustra due tecniche strettamente correlate per l'implementazione di gestori di classi.  
  
## <a name="example"></a>Esempio  
 Questo esempio Usa una classe personalizzata in base il <xref:System.Windows.Controls.Canvas> pannello. La premessa alla base dell'applicazione è che la classe personalizzata presenta comportamenti nei relativi elementi figlio, tra cui intercettazione fa clic su qualsiasi pulsante del mouse a sinistra e il contrassegno che essi gestiti, prima che verranno richiamate la classe di elemento figlio o qualsiasi gestore di istanze su di esso.  
  
 Il <xref:System.Windows.UIElement> classe espone un metodo virtuale che consente la gestione della classe di <xref:System.Windows.UIElement.PreviewMouseLeftButtonDown> eventi, sostituendo semplicemente l'evento. Questo è il modo più semplice per implementare la gestione della classe se tale metodo virtuale è disponibile in una posizione nella gerarchia delle classi. Il codice seguente illustra il <xref:System.Windows.UIElement.OnPreviewMouseLeftButtonDown%2A> implementazione in "MyEditContainer" che è derivato da <xref:System.Windows.Controls.Canvas>. L'implementazione contrassegna l'evento come gestito negli argomenti e quindi aggiunge codice per apportare una modifica base visibile l'elemento di origine.  
  
 [!code-csharp[ClassHandling#OnStarClassHandler](~/samples/snippets/csharp/VS_Snippets_Wpf/ClassHandling/CSharp/SDKSampleLibrary/class1.cs#onstarclasshandler)]
 [!code-vb[ClassHandling#OnStarClassHandler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ClassHandling/visualbasic/sdksamplelibrary/class1.vb#onstarclasshandler)]  
  
 Se nessun metodo virtuale è disponibile nelle classi di base o per il metodo specifico, la gestione di classi può essere aggiunti direttamente usando un metodo di utilità del <xref:System.Windows.EventManager> classe <xref:System.Windows.EventManager.RegisterClassHandler%2A>. Questo metodo deve essere chiamato solo all'interno dell'inizializzazione statica delle classi che aggiunge la gestione di classi. Questo esempio viene aggiunto un altro gestore per <xref:System.Windows.UIElement.PreviewMouseLeftButtonDown> , e in questo caso la classe registrata è la classe personalizzata. Al contrario, quando si usano i metodi virtuali, la classe registrata è davvero il <xref:System.Windows.UIElement> classe di base. Nei casi in cui le classi di base e ogni sottoclasse registrare la gestione di classi, i gestori di sottoclasse siano richiamati per primi. Il comportamento in un'applicazione sarebbe che prima di tutto questo gestore visualizza la finestra di messaggio e quindi visualizzerà la modifica visiva nel gestore del metodo virtuale.  
  
 [!code-csharp[ClassHandling#StaticAndRegisterClassHandler](~/samples/snippets/csharp/VS_Snippets_Wpf/ClassHandling/CSharp/SDKSampleLibrary/class1.cs#staticandregisterclasshandler)]
 [!code-vb[ClassHandling#StaticAndRegisterClassHandler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ClassHandling/visualbasic/sdksamplelibrary/class1.vb#staticandregisterclasshandler)]  
  
## <a name="see-also"></a>Vedere anche
- <xref:System.Windows.EventManager>
- [Contrassegno degli eventi indirizzati come gestiti e gestione delle classi](marking-routed-events-as-handled-and-class-handling.md)
- [Gestire un evento indirizzato](how-to-handle-a-routed-event.md)
- [Cenni preliminari sugli eventi indirizzati](routed-events-overview.md)
