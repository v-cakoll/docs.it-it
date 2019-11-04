---
title: 'Procedura: aggiungere un gestore eventi mediante codice'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- event handlers [WPF], adding
- XAML [WPF], adding event handlers
ms.assetid: 269c61e0-6bd9-4291-9bed-1c5ee66da486
ms.openlocfilehash: 457b8cf5c68096b20df7fe39f1cc3f40358f34d0
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/03/2019
ms.locfileid: "73460436"
---
# <a name="how-to-add-an-event-handler-using-code"></a>Procedura: aggiungere un gestore eventi mediante codice
Questo esempio illustra come aggiungere un gestore eventi a un elemento usando il codice.  
  
 Se si desidera aggiungere un gestore eventi a un elemento [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] e la pagina di markup che contiene l'elemento è già stata caricata, è necessario aggiungere il gestore utilizzando il codice. In alternativa, se si sta compilando la struttura ad albero dell'elemento per un'applicazione usando interamente il codice e non dichiarando alcun elemento usando [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], è possibile chiamare metodi specifici per aggiungere gestori eventi all'albero degli elementi costruito.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene aggiunto un nuovo <xref:System.Windows.Controls.Button> a una pagina esistente inizialmente definita in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]. Un file code-behind implementa un metodo del gestore eventi e quindi aggiunge tale metodo come nuovo gestore eventi nel <xref:System.Windows.Controls.Button>.  
  
 Nell' C# esempio viene utilizzato l'operatore `+=` per assegnare un gestore a un evento. Si tratta dello stesso operatore utilizzato per assegnare un gestore nel modello di gestione degli eventi Common Language Runtime (CLR). Microsoft Visual Basic non supporta questo operatore come mezzo per l'aggiunta di gestori eventi. Richiede invece una delle due tecniche seguenti:  
  
- Usare il metodo <xref:System.Windows.UIElement.AddHandler%2A> insieme a un operatore `AddressOf` per fare riferimento all'implementazione del gestore eventi.  
  
- Usare la parola chiave `Handles` come parte della definizione del gestore eventi. Questa tecnica non è illustrata di seguito. vedere [Visual Basic e gestione degli eventi WPF](visual-basic-and-wpf-event-handling.md).  
  
 [!code-xaml[RoutedEventAddRemoveHandler#XAML](~/samples/snippets/csharp/VS_Snippets_Wpf/RoutedEventAddRemoveHandler/CSharp/default.xaml#xaml)]  
  
 [!code-csharp[RoutedEventAddRemoveHandler#Handler](~/samples/snippets/csharp/VS_Snippets_Wpf/RoutedEventAddRemoveHandler/CSharp/default.xaml.cs#handler)]
 [!code-vb[RoutedEventAddRemoveHandler#Handler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/RoutedEventAddRemoveHandler/VisualBasic/default.xaml.vb#handler)]  
  
> [!NOTE]
> L'aggiunta di un gestore eventi nella pagina [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] analizzata inizialmente è molto più semplice. All'interno dell'elemento oggetto in cui si desidera aggiungere il gestore eventi, aggiungere un attributo che corrisponda al nome dell'evento che si desidera gestire. Specificare quindi il valore di tale attributo come nome del metodo del gestore eventi definito nel file code-behind della pagina [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]. Per altre informazioni, vedere Cenni [preliminari su XAML (WPF)](../../../desktop-wpf/fundamentals/xaml.md) o [Cenni preliminari sugli eventi indirizzati](routed-events-overview.md).  
  
## <a name="see-also"></a>Vedere anche

- [Cenni preliminari sugli eventi indirizzati](routed-events-overview.md)
- [Procedure relative alle proprietà](events-how-to-topics.md)
