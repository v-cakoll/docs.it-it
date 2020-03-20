---
title: Associazione dati in un client Windows Presentation Foundation
ms.date: 03/30/2017
ms.assetid: bb8c8293-5973-4aef-9b07-afeff5d3293c
ms.openlocfilehash: 7bc389056872841905336dcf658a07223906bf82
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79183814"
---
# <a name="data-binding-in-a-windows-presentation-foundation-client"></a>Associazione dati in un client Windows Presentation Foundation
In questo esempio viene illustrato come usare un'associazione dati in un client Windows Presentation Foundation (WPF). L'esempio usa un servizio Windows Communication Foundation (WCF) che genera in modo casuale una matrice di album da restituire al client. Ogni album è dotato di un nome, di un prezzo e di un elenco di tracce. Le tracce dell'album sono dotate di un nome e di una durata. Le informazioni restituite dal servizio vengono associate automaticamente all'interfaccia utente fornita dal client Windows Presentation Foundation (WPF).  
  
> [!NOTE]
> La procedura di installazione e le istruzioni di compilazione per questo esempio si trovano alla fine di questo argomento.  
  
 L'associazione dati fa sì che un'origine dati venga associata automaticamente a un'interfaccia utente. Questa operazione semplifica il modello di programmazione, perché non richiede che ogni elemento dell'interfaccia utente venga aggiornato a livello di programmazione con i dati da un oggetto dati o da una matrice di oggetti dati. È possibile associare un oggetto a un singolo elemento dell'interfaccia utente oppure una matrice a un controllo che accetta più input, ad esempio un oggetto `ListBox`. Nell'esempio di codice seguente viene illustrato come associare i dati al `DataContext` di un elemento dell'interfaccia utente.  
  
```csharp  
// Event handler executed when call is complete  
void client_GetAlbumListCompleted(object sender, GetAlbumListCompletedEventArgs e)  
{  
    // This is on the UI thread, myPanel can be accessed directly  
    myPanel.DataContext = e.Result;
}  
```  
  
 Nell'esempio precedente, il `DataContext` per l'elemento del layout `grid` denominato `myPanel` viene impostato sui dati restituiti dal metodo `GetAlbumList`. Il `DataContext` consente agli elementi di ereditare informazioni dagli elementi padre sull'origine dati usata per l'associazione e su altre caratteristiche dell'associazione, ad esempio il percorso. La riga di codice deve essere eseguita ogni volta che i dati nel server vengono aggiornati. Ad esempio, viene eseguita quando viene avviata la finestra e quando viene aggiunto un nuovo album.  
  
 Nell'esempio di codice XAML seguente, il `ListBox` specifica `ItemsSource="{Binding }"`.  
  
```xml  
<ListBox
          ItemTemplate="{StaticResource AlbumStyle}"  
          ItemsSource="{Binding }"
          IsSynchronizedWithCurrentItem="true" />  
```  
  
 In questo modo specifica che i dati associati all'elemento dell'interfaccia utente di livello superiore venga associato anche a questo controllo (ovvero, la matrice di album). Specifica inoltre `ItemTemplate="{StaticResource AlbumStyle}"` il modello di dati da utilizzare `ListBox`per ogni elemento nel file . È inoltre possibile definire modelli di dati per specificare come formattare i dati. Questi modelli di dati possono essere riusati per altri elementi dell'interfaccia utente dell'applicazione. Il vantaggio è che il modello di dati viene definito e gestito in un solo posto.  
  
 Il modello di dati `AlbumStyle` crea una griglia con due `TextBlock`, uno accanto all'altro. Uno specifica il nome dell'album e l'altro il numero di tracce contenute nell'album.  
  
```xaml  
<DataTemplate x:Key="AlbumStyle">  
    <Grid>  
        <Grid.ColumnDefinitions>  
            <ColumnDefinition Width="260" />  
            <ColumnDefinition Width="60" />  
        </Grid.ColumnDefinitions>  
        <TextBlock Grid.Column="0" TextContent="{Binding Path=Title}" />  
        <TextBlock Grid.Column="1" TextContent="{Binding Path=Tracks#.Count}" HorizontalAlignment="Right" />  
    </Grid>  
</DataTemplate>  
```  
  
 Il codice XAML seguente crea un secondo `ListBox`.  
  
```xaml  
<ListBox Grid.Row="2"
            Grid.ColumnSpan="2"
            ItemTemplate="{StaticResource TrackStyle}"  
            ItemsSource="{Binding Path=Tracks}" />  
```  
  
 Il codice specifica un percorso per `ItemsSource`. Questo indica che i dati associati a questo controllo non sono i dati di livello superiore, ma una proprietà dei dati di livello superiore denominata `Tracks`. Questa proprietà rappresenta la matrice di tracce contenute all'interno dell'album. Viene inoltre specificato un `DataTemplate` diverso, denominato `TrackStyle`. Il layout del modello `TrackStyle` è simile a quello del modello `AlbumStyle`, ma i `TextBlock` sono associati a proprietà diverse. Questo succede perché i due modelli vengono usati con oggetti dati diversi.  
  
### <a name="to-set-up-build-and-run-the-sample"></a>Per impostare, compilare ed eseguire l'esempio  
  
1. Assicurarsi di aver eseguito la procedura di [installazione una tantera per Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2. Per compilare l'edizione in C# o Visual Basic .NET della soluzione, seguire le istruzioni in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
3. Per eseguire l'esempio in una configurazione su un singolo o più computer, seguire le istruzioni in Esecuzione di [Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
> [!IMPORTANT]
> È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> Se questa directory non esiste, passare a [Windows Communication Foundation (WCF) e Windows Workflow Foundation (WF) Esempi per .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) per scaricare tutti gli esempi e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Windows Communication Foundation (WCF). Questo esempio si trova nella directory seguente.  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Scenario\DataBinding\WPFDataBinding`  
