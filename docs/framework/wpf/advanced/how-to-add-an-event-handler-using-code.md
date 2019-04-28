---
title: 'Procedura: Aggiungere un gestore eventi usando il codice'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- event handlers [WPF], adding
- XAML [WPF], adding event handlers
ms.assetid: 269c61e0-6bd9-4291-9bed-1c5ee66da486
ms.openlocfilehash: 10f8e0899e61d5d54589c910bdcbcd92d8ee947c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61777065"
---
# <a name="how-to-add-an-event-handler-using-code"></a>Procedura: Aggiungere un gestore eventi usando il codice
In questo esempio viene illustrato come aggiungere un gestore eventi a un elemento tramite il codice.  
  
 Se si desidera aggiungere un gestore eventi per un [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] elemento e la pagina di markup che contiene l'elemento è già stato caricato, è necessario aggiungere il gestore usando il codice. In alternativa, se si sta compilando l'albero degli elementi per un'applicazione interamente tramite codice e non la dichiarazione di tutti gli elementi usando [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], è possibile chiamare i metodi specifici per aggiungere i gestori eventi per la struttura dell'elemento costruito.  
  
## <a name="example"></a>Esempio  
 L'esempio seguente aggiunge una nuova <xref:System.Windows.Controls.Button> a una pagina esistente che viene definita inizialmente in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]. Un file code-behind implementa un metodo del gestore eventi e quindi aggiunge tale metodo come un nuovo gestore eventi nel <xref:System.Windows.Controls.Button>.  
  
 Il C# esempio Usa la `+=` operatore per assegnare un gestore a un evento. Questo è lo stesso operatore che consente di assegnare un gestore nel [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] Gestione modelli di eventi. Microsoft Visual Basic non supporta questo operatore come strumento di aggiunta di gestori eventi. Richiede invece una delle due tecniche seguenti:  
  
- Usare la <xref:System.Windows.UIElement.AddHandler%2A> metodo, insieme a un `AddressOf` operatore, fare riferimento l'implementazione del gestore eventi.  
  
- Usare il `Handles` (parola chiave) come parte della definizione del gestore eventi. Questa tecnica non viene visualizzata in questa sede. visualizzare [Visual Basic e gestione degli eventi WPF](visual-basic-and-wpf-event-handling.md).  
  
 [!code-xaml[RoutedEventAddRemoveHandler#XAML](~/samples/snippets/csharp/VS_Snippets_Wpf/RoutedEventAddRemoveHandler/CSharp/default.xaml#xaml)]  
  
 [!code-csharp[RoutedEventAddRemoveHandler#Handler](~/samples/snippets/csharp/VS_Snippets_Wpf/RoutedEventAddRemoveHandler/CSharp/default.xaml.cs#handler)]
 [!code-vb[RoutedEventAddRemoveHandler#Handler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/RoutedEventAddRemoveHandler/VisualBasic/default.xaml.vb#handler)]  
  
> [!NOTE]
>  Aggiunta di un gestore eventi in inizialmente analizzata [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] pagina è molto più semplice. All'interno dell'elemento oggetto in cui si desidera aggiungere il gestore dell'evento, aggiungere un attributo che corrisponde al nome dell'evento che si desidera gestire. Quindi specificare il valore dell'attributo come nome del metodo del gestore eventi che è definito nel file code-behind del [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] pagina. Per altre informazioni, vedere [Cenni preliminari su XAML (WPF)](xaml-overview-wpf.md) oppure [Cenni preliminari sugli eventi indirizzati](routed-events-overview.md).  
  
## <a name="see-also"></a>Vedere anche

- [Cenni preliminari sugli eventi indirizzati](routed-events-overview.md)
- [Procedure relative alle proprietà](events-how-to-topics.md)
