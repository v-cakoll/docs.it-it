---
title: Callback e convalida delle proprietà di dipendenza
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- dependency properties [WPF], validation
- coerce value callbacks [WPF]
- callbacks [WPF], validation
- dependency properties [WPF], callbacks
- validation of dependency properties [WPF]
ms.assetid: 48db5fb2-da7f-49a6-8e81-3540e7b25825
ms.openlocfilehash: e181c2d9610619587642f982959f809b96b011dc
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="dependency-property-callbacks-and-validation"></a>Callback e convalida delle proprietà di dipendenza
Questo argomento descrive come creare proprietà di dipendenza usando le implementazioni personalizzate alternative per funzionalità correlate alle proprietà, ad esempio la determinazione della convalida, i callback richiamati ogni volta che il valore effettivo della proprietà viene modificato e l'override delle possibili influenze esterne sulla determinazione del valore. In questo argomento vengono anche presentati scenari in cui è possibile espandere i comportamenti predefiniti del sistema di proprietà usando queste tecniche.  
  
  
  
<a name="prerequisites"></a>   
## <a name="prerequisites"></a>Prerequisiti  
 Nell'argomento si presuppone la conoscenza degli scenari di base dell'implementazione di una proprietà di dipendenza e del modo in cui i metadati vengono applicati a una proprietà di dipendenza personalizzata. Per il contesto, vedere [Proprietà di dipendenza personalizzate](../../../../docs/framework/wpf/advanced/custom-dependency-properties.md) e [Metadati delle proprietà di dipendenza](../../../../docs/framework/wpf/advanced/dependency-property-metadata.md).  
  
<a name="Validation_Callbacks"></a>   
## <a name="validation-callbacks"></a>Callback di convalida  
 I callback di convalida possono essere assegnati a una proprietà di dipendenza al momento della sua prima registrazione. Il callback di convalida non fa parte dei metadati della proprietà; è un input diretto del <xref:System.Windows.DependencyProperty.Register%2A> metodo. Di conseguenza, dopo averlo creato per una proprietà di dipendenza, un callback di convalida non può essere sottoposto a override da parte di una nuova implementazione.  
  
 [!code-csharp[DPCallbackOverride#CurrentDefinitionWithWrapper](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DPCallbackOverride/CSharp/SDKSampleLibrary/class1.cs#currentdefinitionwithwrapper)]
 [!code-vb[DPCallbackOverride#CurrentDefinitionWithWrapper](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DPCallbackOverride/visualbasic/sdksamplelibrary/class1.vb#currentdefinitionwithwrapper)]  
  
 I callback vengono implementati in modo che venga loro fornito un valore di oggetto. Restituiscono `true` se il valore fornito è valido per la proprietà e in caso contrario restituiscono `false`. Si presuppone che la proprietà sia del tipo corretto per il tipo registrato nel sistema di proprietà, quindi all'interno dei callback non viene generalmente eseguito il controllo del tipo. I callback vengono usati dal sistema di proprietà in varie operazioni diverse. Ad esempio l'inizializzazione del tipo iniziale dal valore predefinito, modificare a livello di codice richiamando <xref:System.Windows.DependencyObject.SetValue%2A>, o tenta di eseguire l'override dei metadati con un nuovo valore predefinito fornito. Se il callback di convalida viene richiamato da una di queste operazioni e restituisce `false`, verrà generata un'eccezione. Gli autori di applicazioni devono essere preparati a gestire queste eccezioni. Un uso comune dei callback di convalida è la convalida dei valori di enumerazione o il vincolo di valori di Integer o Double quando la proprietà imposta misure che devono essere uguali o maggiori di zero.  
  
 I callback di convalida sono specificamente concepiti come validator di classi, non di istanze. I parametri del metodo di callback non comunicano l'uno specifico <xref:System.Windows.DependencyObject> in cui vengono impostate le proprietà da convalidare. Di conseguenza, i callback di convalida non sono utili per applicare le possibili "dipendenze" che possono influenzare un valore di proprietà, in cui il valore specifico delle istanze di una proprietà è dipendente da fattori quali i valori specifici delle istanze di altre proprietà o lo stato di runtime.  
  
 Di seguito è riportato il codice di esempio per uno scenario di callback di convalida molto semplice: verifica che una proprietà che è tipizzata come il <xref:System.Double> primitivi non <xref:System.Double.PositiveInfinity> o <xref:System.Double.NegativeInfinity>.  
  
 [!code-csharp[DPCallbackOverride#ValidateValueCallback](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DPCallbackOverride/CSharp/SDKSampleLibrary/class1.cs#validatevaluecallback)]
 [!code-vb[DPCallbackOverride#ValidateValueCallback](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DPCallbackOverride/visualbasic/sdksamplelibrary/class1.vb#validatevaluecallback)]  
  
<a name="Coerce_Value_Callbacks_and_Property_Changed_Events"></a>   
## <a name="coerce-value-callbacks-and-property-changed-events"></a>Callback di valori soggetti a coercizione ed eventi di proprietà modificate  
 Assegnare valore callback passare specifico <xref:System.Windows.DependencyObject> istanza per le proprietà, come <xref:System.Windows.PropertyChangedCallback> implementazioni che vengono richiamate dal sistema di proprietà ogni volta che cambia il valore della proprietà di dipendenza. Usando questi due callback in combinazione, è possibile creare una serie di proprietà su elementi in cui le modifiche in una proprietà imporranno una coercizione o una rivalutazione di un'altra proprietà.  
  
 Un scenario tipico per l'uso di un collegamento di proprietà di dipendenza è il caso in cui si dispone di una proprietà basata su un'interfaccia utente in cui l'elemento contiene una proprietà per il valore minimo e una per il valore massimo, oltre a una terza proprietà per il valore effettivo o corrente. In questo caso, se il massimo è stato regolato in modo che il valore corrente superi il nuovo massimo, sarà opportuno assegnare il valore corrente in modo che non sia maggiore del nuovo massimo e impostare una relazione simile per il valore minimo rispetto al valore corrente.  
  
 Di seguito viene riportato un brevissimo esempio di codice per una delle tre proprietà di dipendenza che illustrano questa relazione. Nell'esempio viene illustrata la modalità di registrazione della proprietà `CurrentReading` di un set Min/Max/Current di proprietà *Reading. Viene usata la convalida come illustrato nella sezione precedente.  
  
 [!code-csharp[DPCallbackOverride#CurrentDefinitionWithWrapper](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DPCallbackOverride/CSharp/SDKSampleLibrary/class1.cs#currentdefinitionwithwrapper)]
 [!code-vb[DPCallbackOverride#CurrentDefinitionWithWrapper](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DPCallbackOverride/visualbasic/sdksamplelibrary/class1.vb#currentdefinitionwithwrapper)]  
  
 Il callback per proprietà modificate per il valore Current viene usato per inoltrare la modifica ad altre proprietà dipendenti, richiamando in modo esplicito i callback di valori soggetti a coercizione registrati per tali proprietà:  
  
 [!code-csharp[DPCallbackOverride#OnPCCurrent](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DPCallbackOverride/CSharp/SDKSampleLibrary/class1.cs#onpccurrent)]
 [!code-vb[DPCallbackOverride#OnPCCurrent](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DPCallbackOverride/visualbasic/sdksamplelibrary/class1.vb#onpccurrent)]  
  
 Il callback di valori soggetti a coercizione verifica i valori delle proprietà da cui la proprietà corrente è potenzialmente dipendente e assegna il valore corrente, se necessario:  
  
 [!code-csharp[DPCallbackOverride#CoerceCurrent](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DPCallbackOverride/CSharp/SDKSampleLibrary/class1.cs#coercecurrent)]
 [!code-vb[DPCallbackOverride#CoerceCurrent](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DPCallbackOverride/visualbasic/sdksamplelibrary/class1.vb#coercecurrent)]  
  
> [!NOTE]
>  I valori predefiniti delle proprietà non vengono assegnati. Un valore uguale al valore predefinito della proprietà può verificarsi se un valore della proprietà ha ancora l'impostazione predefinita iniziale, o tramite la cancellazione degli altri valori con <xref:System.Windows.DependencyObject.ClearValue%2A>.  
  
 I callback di valori soggetti a coercizione e per proprietà modificate fanno parte dei metadati delle proprietà. Pertanto, è possibile modificare i callback per una determinata proprietà di dipendenza quando quest'ultima è presente su un tipo derivato dal tipo proprietario della proprietà di dipendenza, eseguendo l'override dei metadati per tale proprietà sul tipo.  
  
<a name="Advanced"></a>   
## <a name="advanced-coercion-and-callback-scenarios"></a>Coercizione avanzata e scenari di callback  
  
### <a name="constraints-and-desired-values"></a>Vincoli e valori desiderati  
 Il <xref:System.Windows.PropertyMetadata.CoerceValueCallback%2A> callback verranno utilizzati dal sistema di proprietà per assegnare un valore in base alla logica dichiarata, ma un valore di coercizione di impostato localmente proprietà verrà mantenute ancora un "valore desiderato" internamente. Se i vincoli sono basati su altri valori di proprietà che possono essere modificati in modo dinamico nel corso della durata dell'applicazione, anche i vincoli di coercizione vengono modificati in modo dinamico e la proprietà vincolata può modificare il proprio valore per avvicinarsi il più possibile al valore desiderato in base ai nuovi vincoli. Il valore diventerà il valore desiderato se tutti i vincoli verranno rimossi. È potenzialmente possibile introdurre alcuni scenari di dipendenze piuttosto complicati se si hanno più proprietà dipendenti l'una dall'altra in modo circolare. Ad esempio, nello scenario Min/Max/Current, è possibile scegliere che i valori Minimum e Maximum siano impostabili dall'utente. In questo caso, potrebbe essere necessario imporre che il valore Maximum sia sempre superiore al valore Minimum e viceversa. Ma se tale coercizione è attiva e il valore Maximum viene assegnato a Minimum, il valore Current viene lasciato in uno stato non impostabile, poiché è dipendente da entrambi ed è vincolato all'intervallo compreso tra i valori, che è pari a zero. Se i valori Maximum o Minimum vengono modificati, il valore Current sembrerà seguire uno dei valori, perché il valore desiderato di Current è ancora archiviato e tenta di raggiungere il valore desiderato con l'allentarsi dei vincoli.  
  
 Le dipendenze complesse non sono errate dal punto di vista tecnico, ma possono causare una leggera riduzione delle prestazioni se richiedono numerose rivalutazioni, oltre a generare confusione negli utenti se influiscono direttamente sull'interfaccia utente. È necessario prestare attenzione con i callback di valori soggetti a coercizione e per proprietà modificate e accertarsi che la coercizione tentata possa essere considerata nel modo meno ambiguo possibile e non imponga vincoli eccessivi.  
  
### <a name="using-coercevalue-to-cancel-value-changes"></a>Uso di CoerceValue per annullare le modifiche dei valori  
 Il sistema di proprietà considererà qualsiasi <xref:System.Windows.CoerceValueCallback> che restituisce il valore <xref:System.Windows.DependencyProperty.UnsetValue> come un caso speciale. Ciò significa che la modifica della proprietà che ha comportato il <xref:System.Windows.CoerceValueCallback> la chiamata deve essere rifiutata dal sistema di proprietà e che il sistema di proprietà deve invece segnalare qualsiasi valore precedente della proprietà. Questo meccanismo può essere utile per controllare che le modifiche a una proprietà avviate in modo asincrono siano ancora valide per lo stato dell'oggetto corrente e per eliminarle in caso non lo siano. Un altro possibile scenario è costituito dalla possibilità di eliminare in modo selettivo un valore a seconda di quale componente della determinazione dei valori di proprietà sia responsabile del valore segnalato. A tale scopo, è possibile utilizzare il <xref:System.Windows.DependencyProperty> passato come input per il callback e l'identificatore della proprietà <xref:System.Windows.DependencyPropertyHelper.GetValueSource%2A>, quindi elaborare il <xref:System.Windows.ValueSource>.  
  
## <a name="see-also"></a>Vedere anche  
 [Panoramica sulle proprietà di dipendenza](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md)  
 [Metadati delle proprietà di dipendenza](../../../../docs/framework/wpf/advanced/dependency-property-metadata.md)  
 [Proprietà di dipendenza personalizzate](../../../../docs/framework/wpf/advanced/custom-dependency-properties.md)
