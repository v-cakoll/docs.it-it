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
ms.openlocfilehash: 1a1d956ee7f41ac1ac0fc9bd051a18b9ff438930
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/03/2019
ms.locfileid: "73459842"
---
# <a name="initialization-for-object-elements-not-in-an-object-tree"></a>Inizializzazione di elementi oggetto non presenti in una struttura ad albero di oggetti
Alcuni aspetti dell'inizializzazione di [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] vengono rinviati ai processi che in genere si basano sulla connessione dell'elemento interessato all'albero logico o alla struttura ad albero visuale. In questo argomento vengono descritti i passaggi necessari per inizializzare un elemento non connesso ad alcuno di questi alberi.  

## <a name="elements-and-the-logical-tree"></a>Elementi e albero logico  
 Quando si crea un'istanza di una classe [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] all'interno del codice, è necessario tenere presente che molti aspetti dell'inizializzazione dell'oggetto per una classe [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] non fanno deliberatamente parte del codice che viene eseguito quando si chiama il costruttore della classe. In particolare, per le classi di controlli, la maggior parte della rappresentazione visiva di un controllo non viene definita dal costruttore, ma dal modello del controllo. Sebbene possa provenire da diverse origini, nella maggior parte dei casi il modello viene ottenuto dagli stili dei temi. I modelli sono in pratica un binding tardivo. Il modello necessario viene associato al controllo in questione solo quando il controllo è pronto per il layout e quest'ultima condizione si verifica solo quando il controllo viene associato a un albero logico che si connette a una superficie di rendering nella radice. È tale elemento a livello radice che avvia il rendering di tutti i relativi elementi figlio definiti nell'albero logico.  
  
 Anche la struttura ad albero visuale partecipa a questo processo. Anche un'istanza completa per gli elementi che fanno parte della struttura ad albero visuale tramite i modelli viene creata solo quando gli elementi stessi vengono connessi.  
  
 La conseguenza di questo comportamento è la necessità di passaggi aggiuntivi per alcune operazioni basate sulle caratteristiche visive completate di un elemento. Un esempio è rappresentato dal tentativo di ottenere le caratteristiche visive di una classe costruita, ma non ancora associata a un albero. Se, ad esempio, si desidera chiamare <xref:System.Windows.Media.Imaging.RenderTargetBitmap.Render%2A> in un <xref:System.Windows.Media.Imaging.RenderTargetBitmap> e l'oggetto visivo che si sta passando è un elemento non connesso a un albero, l'elemento non viene completato visivamente fino a quando non vengono completati altri passaggi di inizializzazione.  
  
### <a name="using-begininit-and-endinit-to-initialize-the-element"></a>Uso di BeginInit e EndInit per inizializzare l'elemento  
 Varie classi di [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] implementano l'interfaccia <xref:System.ComponentModel.ISupportInitialize>. Usare i metodi <xref:System.ComponentModel.ISupportInitialize.BeginInit%2A> e <xref:System.ComponentModel.ISupportInitialize.EndInit%2A> dell'interfaccia per indicare un'area nel codice che contiene passaggi di inizializzazione, ad esempio l'impostazione di valori di proprietà che influiscono sul rendering. Dopo la chiamata di <xref:System.ComponentModel.ISupportInitialize.EndInit%2A> nella sequenza, il sistema di layout può elaborare l'elemento e iniziare a cercare uno stile implicito.  
  
 Se l'elemento in cui si impostano le proprietà è un <xref:System.Windows.FrameworkElement> o <xref:System.Windows.FrameworkContentElement> classe derivata, è possibile chiamare le versioni della classe <xref:System.Windows.FrameworkElement.BeginInit%2A> e <xref:System.Windows.FrameworkElement.EndInit%2A> anziché eseguire il cast a <xref:System.ComponentModel.ISupportInitialize>.  
  
### <a name="sample-code"></a>Codice di esempio  
 Nell'esempio seguente è riportato il codice di esempio per un'applicazione console che usa le API di rendering e <xref:System.Windows.Markup.XamlReader.Load%28System.IO.Stream%29?displayProperty=nameWithType> di un file di [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] libero per illustrare il posizionamento appropriato di <xref:System.Windows.FrameworkElement.BeginInit%2A> e <xref:System.Windows.FrameworkElement.EndInit%2A> intorno ad altre chiamate API che regolano le proprietà che influiscono sul rendering.  
  
 L'esempio illustrata solo la funzione principale. Le funzioni `Rasterize` e `Save` (non illustrate) sono funzioni di utilità che gestiscono l'elaborazione di immagini e l'I/O.  
  
 [!code-csharp[InitializeElements#Main](~/samples/snippets/csharp/VS_Snippets_Wpf/InitializeElements/CSharp/initializeelements.cs#main)]
 [!code-vb[InitializeElements#Main](~/samples/snippets/visualbasic/VS_Snippets_Wpf/InitializeElements/VisualBasic/initializeelements.vb#main)]  
  
## <a name="see-also"></a>Vedere anche

- [Strutture ad albero in WPF](trees-in-wpf.md)
- [Cenni preliminari sul rendering della grafica WPF](../graphics-multimedia/wpf-graphics-rendering-overview.md)
- [Cenni preliminari su XAML (WPF)](../../../desktop-wpf/fundamentals/xaml.md)
