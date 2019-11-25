---
title: Associazione di dati a controlli (WCF Data Services)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- client applications, WCF Data Services
- WCF Data Services, client library
- data binding, WCF Data Services
ms.assetid: b32e1d49-c214-4cb1-867e-88fbb3d08c8d
ms.openlocfilehash: 605ff7a9acaaa217f0e482579968757dd451aed9
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/12/2019
ms.locfileid: "73974840"
---
# <a name="binding-data-to-controls-wcf-data-services"></a>Associazione di dati a controlli (WCF Data Services)
Con [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] è possibile associare controlli, quali `ComboBox` e `ListView`, a un'istanza della classe <xref:System.Data.Services.Client.DataServiceCollection%601>. Questa raccolta, che eredita dalla classe <xref:System.Collections.ObjectModel.ObservableCollection%601>, contiene i dati di un feed di Open Data Protocol (OData). Questa classe rappresenta una raccolta di dati dinamica che fornisce notifiche in caso di aggiunta o rimozione di elementi. Quando si usa un'istanza di <xref:System.Data.Services.Client.DataServiceCollection%601> per data binding, le librerie client [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] gestiscono questi eventi per garantire che gli oggetti rilevati dal <xref:System.Data.Services.Client.DataServiceContext> rimangano sincronizzati con i dati nell'elemento dell'interfaccia utente associato.  
  
 La classe <xref:System.Data.Services.Client.DataServiceCollection%601> implementa indirettamente l'interfaccia <xref:System.Collections.Specialized.INotifyCollectionChanged> per avvisare il contesto dell'aggiunta o della rimozione di oggetti dalla raccolta. Gli oggetti del tipo di servizio dati usati con <xref:System.Data.Services.Client.DataServiceCollection%601> devono inoltre implementare l'interfaccia <xref:System.ComponentModel.INotifyPropertyChanged> per informare l'oggetto <xref:System.Data.Services.Client.DataServiceCollection%601> quando le proprietà di oggetti inclusi nella raccolta di associazioni vengono modificate.  
  
> [!NOTE]
> Quando si utilizza la finestra di dialogo **Aggiungi riferimento al servizio** o lo strumento [DataSvcUtil. exe](wcf-data-service-client-utility-datasvcutil-exe.md) con l'opzione `/dataservicecollection` per generare le classi del servizio dati client, le classi di dati generate implementano l'interfaccia <xref:System.ComponentModel.INotifyPropertyChanged>. Per altre informazioni, vedere [procedura: generare manualmente classi del servizio dati client](how-to-manually-generate-client-data-service-classes-wcf-data-services.md).  
  
## <a name="creating-the-binding-collection"></a>Creazione della raccolta di associazioni  
 Creare una nuova istanza della classe <xref:System.Data.Services.Client.DataServiceCollection%601> chiamando uno dei metodi del costruttore di classi con un'istanza di <xref:System.Data.Services.Client.DataServiceContext> fornita e facoltativamente un oggetto <xref:System.Data.Services.Client.DataServiceQuery%601> o una query LINQ che al termine dell'esecuzione restituisce un'istanza di <xref:System.Collections.Generic.IEnumerable%601>. Questo <xref:System.Collections.Generic.IEnumerable%601> fornisce l'origine degli oggetti per la raccolta di associazioni, materializzata da un feed OData. Per altre informazioni, vedere [materializzazione degli oggetti](object-materialization-wcf-data-services.md). Per impostazione predefinita, le modifiche apportate agli oggetti associati e agli elementi inseriti nella raccolta vengono rilevate automaticamente dall'oggetto <xref:System.Data.Services.Client.DataServiceContext>. Se è necessario tenere traccia delle modifiche manualmente, chiamare uno dei metodi del costruttore che accetta un parametro di `trackingMode` e specificare un valore di <xref:System.Data.Services.Client.TrackingMode.None>.  
  
 Nell'esempio seguente viene illustrato come creare un'istanza di <xref:System.Data.Services.Client.DataServiceCollection%601> in base a un oggetto <xref:System.Data.Services.Client.DataServiceContext> fornito e un oggetto <xref:System.Data.Services.Client.DataServiceQuery%601> che restituisce tutti i clienti con gli ordini correlati:  
  
 [!code-csharp[Astoria Northwind Client#CustomersOrders2Binding](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/customerorders2.cs#customersorders2binding)]
 [!code-vb[Astoria Northwind Client#CustomersOrders2Binding](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/customerorders2.vb#customersorders2binding)]  
  
## <a name="binding-data-to-windows-presentation-foundation-elements"></a>Associazione di dati a elementi di Windows Presentation Foundation  
 Poiché la classe <xref:System.Data.Services.Client.DataServiceCollection%601> eredita dalla classe <xref:System.Collections.ObjectModel.ObservableCollection%601>, è possibile associare oggetti a un elemento o a un controllo in un'applicazione di Windows Presentation Foundation (WPF) in modo analogo a quando si usa la classe <xref:System.Collections.ObjectModel.ObservableCollection%601> per l'associazione. Per ulteriori informazioni, vedere [Data Binding (Windows Presentation Foundation)](../../../desktop-wpf/data/data-binding-overview.md). Un modo per associare dati del servizio dati a controlli WPF consiste nell'impostare la proprietà `DataContext` dell'elemento sull'istanza della classe <xref:System.Data.Services.Client.DataServiceCollection%601> che contiene il risultato della query. In questo caso, è possibile usare la proprietà <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> per impostare l'origine dell'oggetto per il controllo. Usare la proprietà <xref:System.Windows.Controls.ItemsControl.DisplayMemberPath%2A> per specificare quale proprietà dell'oggetto associato visualizzare. Quando si associa un elemento a un oggetto correlato restituito da una proprietà di navigazione, includere il percorso nell'associazione definita per la proprietà <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>. Questo percorso è relativo all'oggetto radice impostato dalla proprietà <xref:System.Windows.FrameworkElement.DataContext%2A> del controllo padre. Nell'esempio seguente viene impostata la proprietà <xref:System.Windows.FrameworkElement.DataContext%2A> di un elemento <xref:System.Windows.Controls.StackPanel> per associare il controllo padre a un oggetto <xref:System.Data.Services.Client.DataServiceCollection%601> di oggetti personalizzati:  
  
 [!code-csharp[Astoria Northwind Client#MasterDetailBinding](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/customerorderscustom.xaml.cs#masterdetailbinding)]
 [!code-csharp[Astoria Northwind Client#MasterDetailBinding](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/customerorderswpf.xaml.cs#masterdetailbinding)]
 [!code-vb[Astoria Northwind Client#MasterDetailBinding](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/customerorderscustom.xaml.vb#masterdetailbinding)]
 [!code-vb[Astoria Northwind Client#MasterDetailBinding](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/customerorderswpf.xaml.vb#masterdetailbinding)]
 [!code-vb[Astoria Northwind Client#MasterDetailBinding](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/customerorderscustom2.xaml.vb#masterdetailbinding)]  
  
 Nell'esempio è riportata la definizione dell'associazione XAML dei controlli figlio <xref:System.Windows.Controls.DataGrid> e <xref:System.Windows.Controls.ComboBox>:  
  
 [!code-xaml[Astoria Northwind Client#MasterDetailXaml](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/customerorderswpf.xaml#masterdetailxaml)]  
  
 Per altre informazioni, vedere [procedura: associare dati a elementi Windows Presentation Foundation](bind-data-to-wpf-elements-wcf-data-services.md).  
  
 Quando un'entità partecipa a una relazione uno-a-molti o molti-a-molti, la proprietà di navigazione per la relazione restituisce una raccolta di oggetti correlati. Quando si utilizza la finestra di dialogo **Aggiungi riferimento al servizio** o lo strumento DataSvcUtil. exe per generare le classi del servizio dati client, la proprietà di navigazione restituisce un'istanza di <xref:System.Data.Services.Client.DataServiceCollection%601>. In questo modo è possibile associare oggetti correlati a un controllo e supportare scenari di associazione WPF comuni, quale il modello di associazione Master-Details per entità correlate. Nell'esempio XAML precedente il codice XAML determina l'associazione dell'oggetto <xref:System.Data.Services.Client.DataServiceCollection%601> master all'elemento dati radice. L'oggetto <xref:System.Windows.Controls.DataGrid> dell'ordine viene quindi associato all'oggetto <xref:System.Data.Services.Client.DataServiceCollection%601> relativo agli ordini restituito dall'oggetto Customers selezionato, che viene a sua volta associato all'elemento dati radice di <xref:System.Windows.Window>.  
  
## <a name="binding-data-to-windows-forms-controls"></a>Associazione di dati a controlli Windows Form  
 Per associare dati a un controllo Windows Form, impostare la proprietà `DataSource` del controllo sull'istanza della classe <xref:System.Data.Services.Client.DataServiceCollection%601> che contiene il risultato della query.  
  
> [!NOTE]
> L'associazione dati è supportata solo per i controlli che sono in attesa di eventi di modifica mediante l'implementazione delle interfacce <xref:System.Collections.Specialized.INotifyCollectionChanged> e <xref:System.ComponentModel.INotifyPropertyChanged>. Quando un controllo non supporta questo tipo di notifica delle modifiche, le modifiche apportate all'oggetto <xref:System.Data.Services.Client.DataServiceCollection%601> sottostante non sono riflesse nel controllo associato.  
  
 Nell'esempio seguente viene associato un oggetto <xref:System.Data.Services.Client.DataServiceCollection%601> a un controllo <xref:System.Windows.Forms.ComboBox>:  
  
 [!code-csharp[Astoria Northwind Client#CustomersOrdersDataBindingSpecific](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/customerorders.cs#customersordersdatabindingspecific)]
 [!code-vb[Astoria Northwind Client#CustomersOrdersDataBindingSpecific](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/customerorders.vb#customersordersdatabindingspecific)]  
  
 Quando si utilizza la finestra di dialogo **Aggiungi riferimento al servizio** per generare le classi del servizio dati client, viene creata anche un'origine dati del progetto basata sulla <xref:System.Data.Services.Client.DataServiceContext>generata. Con questa origine dati è possibile creare elementi dell'interfaccia utente o controlli che visualizzano i dati dal servizio dati semplicemente trascinando gli elementi dalla finestra **origini dati** nella finestra di progettazione. Nell'interfaccia utente dell'applicazione questi elementi diventano elementi associati all'origine dati. Per ulteriori informazioni, vedere [procedura: associare dati utilizzando un'origine dati del progetto](how-to-bind-data-using-a-project-data-source-wcf-data-services.md).  
  
## <a name="binding-paged-data"></a>Associazione di dati di paging  
 È possibile configurare un servizio dati per limitare la quantità di dati sottoposti a query che vengono restituiti in un unico messaggio di risposta. Per ulteriori informazioni, vedere [configurazione del servizio dati](configuring-the-data-service-wcf-data-services.md). Quando il servizio dati esegue il paging dei dati di risposta, in ogni risposta è incluso un collegamento che consente di restituire la pagina successiva di risultati. Per ulteriori informazioni, vedere [caricamento di contenuto posticipato](loading-deferred-content-wcf-data-services.md). In questo caso, è necessario caricare in modo esplicito le pagine chiamando il metodo <xref:System.Data.Services.Client.DataServiceCollection%601.Load%2A> su <xref:System.Data.Services.Client.DataServiceCollection%601> e passando l'URI ottenuto dalla proprietà <xref:System.Data.Services.Client.DataServiceQueryContinuation.NextLinkUri%2A>, come illustrato nell'esempio seguente:  
  
 [!code-csharp[Astoria Northwind Client#BindPagedDataSpecific](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/customerorderswpf3.xaml.cs#bindpageddataspecific)]
 [!code-vb[Astoria Northwind Client#BindPagedDataSpecific](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/customerorderswpf3.xaml.vb#bindpageddataspecific)]  
  
 Gli oggetti correlati vengono caricati in modo analogo. Per altre informazioni, vedere [procedura: associare dati a elementi Windows Presentation Foundation](bind-data-to-wpf-elements-wcf-data-services.md).  
  
## <a name="customizing-data-binding-behaviors"></a>Personalizzazione dei comportamenti di data binding  
 La classe <xref:System.Data.Services.Client.DataServiceCollection%601> consente di intercettare gli eventi generati nel momento in cui vengono apportate modifiche alla raccolta, ad esempio l'aggiunta o la rimozione di un oggetto e la modifica delle proprietà di un oggetto in una raccolta. È possibile modificare gli eventi di data binding per eseguire l'override del comportamento predefinito che include i vincoli seguenti:  
  
- All'interno dei delegati non viene eseguita alcuna convalida.  
  
- L'aggiunta di un'entità determina automaticamente l'aggiunta delle entità correlate.  
  
- L'eliminazione di un'entità non determina l'eliminazione delle entità correlate.  
  
 Quando si crea una nuova istanza di <xref:System.Data.Services.Client.DataServiceCollection%601>, è possibile specificare i parametri seguenti che definiscono i delegati per i metodi che gestiscono gli eventi generati al momento della modifica degli oggetti associati:  
  
- `entityChanged`: metodo che viene chiamato quando la proprietà di un oggetto associato viene modificata. Questo delegato <xref:System.Func%602> accetta un oggetto <xref:System.Data.Services.Client.EntityChangedParams> e restituisce un valore booleano che indica se il comportamento predefinito, che implica la chiamata del metodo <xref:System.Data.Services.Client.DataServiceContext.UpdateObject%2A> su <xref:System.Data.Services.Client.DataServiceContext>, deve ancora verificarsi.  
  
- `entityCollectionChanged`: metodo che viene chiamato quando un oggetto viene aggiunto o rimosso dalla raccolta di associazioni. Questo delegato <xref:System.Func%602> accetta un oggetto <xref:System.Data.Services.Client.EntityCollectionChangedParams> e restituisce un valore booleano che indica se il comportamento predefinito, che implica la chiamata del metodo <xref:System.Data.Services.Client.DataServiceContext.AddObject%2A> per un'azione <xref:System.Collections.Specialized.NotifyCollectionChangedAction.Add> o del metodo <xref:System.Data.Services.Client.DataServiceContext.DeleteObject%2A> per un'azione <xref:System.Collections.Specialized.NotifyCollectionChangedAction.Remove> sull'oggetto <xref:System.Data.Services.Client.DataServiceContext>, deve ancora verificarsi.  
  
> [!NOTE]
> [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] non esegue alcuna convalida dei comportamenti personalizzati implementati in questi delegati.  
  
 Nell'esempio seguente l'azione <xref:System.Collections.Specialized.NotifyCollectionChangedAction.Remove> viene personalizzata per chiamare il metodo <xref:System.Data.Services.Client.DataServiceContext.DeleteLink%2A> e il metodo <xref:System.Data.Services.Client.DataServiceContext.DeleteObject%2A> per rimuovere le entità `Orders_Details` che appartengono a un'entità `Orders` eliminata. Questa azione personalizzata viene eseguita in quanto le entità dipendenti non vengono eliminate automaticamente al momento dell'eliminazione dell'entità padre.  
  
 [!code-csharp[Astoria Northwind Client#CustomersOrdersDeleteRelated](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/customerorderscustom.xaml.cs#customersordersdeleterelated)]
 [!code-vb[Astoria Northwind Client#CustomersOrdersDeleteRelated](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/customerorderscustom.xaml.vb#customersordersdeleterelated)]
 [!code-vb[Astoria Northwind Client#CustomersOrdersDeleteRelated](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/customerorderscustom2.xaml.vb#customersordersdeleterelated)]  
  
 Per altre informazioni, vedere [procedura: personalizzare i comportamenti di associazione dati](how-to-customize-data-binding-behaviors-wcf-data-services.md).  
  
 Il comportamento predefinito che si verifica quando un oggetto viene rimosso da un oggetto <xref:System.Data.Services.Client.DataServiceCollection%601> tramite il metodo <xref:System.Collections.ObjectModel.Collection%601.Remove%2A>, consiste nel fatto che l'oggetto viene contrassegnato come eliminato anche in <xref:System.Data.Services.Client.DataServiceContext>. Per modificare questo comportamento, è possibile specificare un delegato per un metodo nel parametro `entityCollectionChanged` che viene chiamato quando si verifica l'evento <xref:System.Collections.Specialized.INotifyCollectionChanged.CollectionChanged>.  
  
## <a name="data-binding-with-custom-client-data-classes"></a>Data binding con classi di dati client personalizzate  
 Per essere in grado di caricare oggetti in <xref:System.Data.Services.Client.DataServiceCollection%601>, gli oggetti stessi devono implementare l'interfaccia <xref:System.ComponentModel.INotifyPropertyChanged>. Le classi client del servizio dati generate quando si utilizza la finestra di dialogo **Aggiungi riferimento al servizio** o lo strumento [DataSvcUtil. exe](wcf-data-service-client-utility-datasvcutil-exe.md) implementano questa interfaccia. Se si forniscono classi di dati client personalizzate, sarà necessario usare un altro tipo di raccolta per il data binding. Quando gli oggetti vengono modificati, è necessario gestire gli eventi nei controlli associati ai dati per chiamare i metodi della classe <xref:System.Data.Services.Client.DataServiceContext> seguenti:  
  
- <xref:System.Data.Services.Client.DataServiceContext.AddObject%2A>: quando un nuovo oggetto viene aggiunto alla raccolta.  
  
- <xref:System.Data.Services.Client.DataServiceContext.DeleteObject%2A>: quando un oggetto viene rimosso dalla raccolta.  
  
- <xref:System.Data.Services.Client.DataServiceContext.UpdateObject%2A>: quando una proprietà viene modificata in un oggetto della raccolta.  
  
- <xref:System.Data.Services.Client.DataServiceContext.AddLink%2A>: quando un oggetto viene aggiunto alla raccolta di un oggetto correlato.  
  
- <xref:System.Data.Services.Client.DataServiceContext.SetLink%2A>: quando un oggetto viene aggiunto a una raccolta di oggetti correlati.  
  
 Per ulteriori informazioni, vedere [aggiornamento del servizio dati](updating-the-data-service-wcf-data-services.md).  
  
## <a name="see-also"></a>Vedere anche

- [Procedura: generare manualmente classi del servizio dati client](how-to-manually-generate-client-data-service-classes-wcf-data-services.md)
- [Procedura: aggiungere un riferimento al servizio dati](how-to-add-a-data-service-reference-wcf-data-services.md)
