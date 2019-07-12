---
title: Inizializzazione di elementi oggetto non presenti in una struttura ad albero di oggetti
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- logical tree [WPF]
- visual tree [WPF]
- elements [WPF], initializing
- initializing elements [WPF]
ms.assetid: 7b8dfc9b-46ac-4ce8-b7bb-035734d688b7
ms.openlocfilehash: 4f8ee4b31c135595770338831c23d8a0f419e8cd
ms.sourcegitcommit: 83ecdf731dc1920bca31f017b1556c917aafd7a0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/12/2019
ms.locfileid: "67857003"
---
# <a name="initialization-for-object-elements-not-in-an-object-tree"></a>Inizializzazione di elementi oggetto non presenti in una struttura ad albero di oggetti
Alcuni aspetti dell'inizializzazione di [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] vengono rinviati ai processi che in genere si basano sulla connessione dell'elemento interessato all'albero logico o alla struttura ad albero visuale. In questo argomento vengono descritti i passaggi necessari per inizializzare un elemento non connesso ad alcuno di questi alberi.  

## <a name="elements-and-the-logical-tree"></a>Elementi e albero logico  
 Quando si crea un'istanza di una classe [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] all'interno del codice, è necessario tenere presente che molti aspetti dell'inizializzazione dell'oggetto per una classe [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] non fanno deliberatamente parte del codice che viene eseguito quando si chiama il costruttore della classe. In particolare, per le classi di controlli, la maggior parte della rappresentazione visiva di un controllo non viene definita dal costruttore, ma dal modello del controllo. Sebbene possa provenire da diverse origini, nella maggior parte dei casi il modello viene ottenuto dagli stili dei temi. I modelli sono in pratica un binding tardivo. Il modello necessario viene associato al controllo in questione solo quando il controllo è pronto per il layout e quest'ultima condizione si verifica solo quando il controllo viene associato a un albero logico che si connette a una superficie di rendering nella radice. È tale elemento a livello radice che avvia il rendering di tutti i relativi elementi figlio definiti nell'albero logico.  
  
 Anche la struttura ad albero visuale partecipa a questo processo. Anche un'istanza completa per gli elementi che fanno parte della struttura ad albero visuale tramite i modelli viene creata solo quando gli elementi stessi vengono connessi.  
  
 La conseguenza di questo comportamento è la necessità di passaggi aggiuntivi per alcune operazioni basate sulle caratteristiche visive completate di un elemento. Un esempio è rappresentato dal tentativo di ottenere le caratteristiche visive di una classe costruita, ma non ancora associata a un albero. Ad esempio, se si desidera chiamare <xref:System.Windows.Media.Imaging.RenderTargetBitmap.Render%2A> su un <xref:System.Windows.Media.Imaging.RenderTargetBitmap> e l'oggetto visivo si sta passando è un elemento non connesso a una struttura ad albero, tale elemento non viene completato visivamente finché non vengono completati i passaggi di inizializzazione aggiuntiva.  
  
### <a name="using-begininit-and-endinit-to-initialize-the-element"></a>Uso di BeginInit e EndInit per inizializzare l'elemento  
 Varie classi nello [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] implementano il <xref:System.ComponentModel.ISupportInitialize> interfaccia. Si utilizza il <xref:System.ComponentModel.ISupportInitialize.BeginInit%2A> e <xref:System.ComponentModel.ISupportInitialize.EndInit%2A> metodi dell'interfaccia per indicare un'area del codice che contiene i passaggi di inizializzazione (ad esempio l'impostazione di proprietà, i valori che influiscono sul rendering). Dopo aver <xref:System.ComponentModel.ISupportInitialize.EndInit%2A> viene chiamato nella sequenza, il sistema di layout può elaborare l'elemento e avviare la ricerca di uno stile implicito.  
  
 È l'elemento si impostano le proprietà in un <xref:System.Windows.FrameworkElement> oppure <xref:System.Windows.FrameworkContentElement> classe, è possibile chiamare le versioni della classe derivata <xref:System.Windows.FrameworkElement.BeginInit%2A> e <xref:System.Windows.FrameworkElement.EndInit%2A> anziché eseguire il cast a <xref:System.ComponentModel.ISupportInitialize>.  
  
### <a name="sample-code"></a>Codice di esempio  
 L'esempio seguente è codice di esempio per un'applicazione console che usa le API di rendering e <xref:System.Windows.Markup.XamlReader.Load%28System.IO.Stream%29?displayProperty=nameWithType> di tipo loose [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] per illustrare il posizionamento corretto di file <xref:System.Windows.FrameworkElement.BeginInit%2A> e <xref:System.Windows.FrameworkElement.EndInit%2A> intorno ad altre chiamate API che regolano le proprietà che influiscono sul rendering.  
  
 L'esempio illustrata solo la funzione principale. Le funzioni `Rasterize` e `Save` (non illustrate) sono funzioni di utilità che gestiscono l'elaborazione di immagini e l'I/O.  
  
 [!code-csharp[InitializeElements#Main](~/samples/snippets/csharp/VS_Snippets_Wpf/InitializeElements/CSharp/initializeelements.cs#main)]
 [!code-vb[InitializeElements#Main](~/samples/snippets/visualbasic/VS_Snippets_Wpf/InitializeElements/VisualBasic/initializeelements.vb#main)]  
  
## <a name="see-also"></a>Vedere anche

- [Strutture ad albero in WPF](trees-in-wpf.md)
- [Cenni preliminari sul rendering della grafica WPF](../graphics-multimedia/wpf-graphics-rendering-overview.md)
- [Cenni preliminari su XAML (WPF)](xaml-overview-wpf.md)
