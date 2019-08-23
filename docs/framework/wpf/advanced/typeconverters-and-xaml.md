---
title: TypeConverter e XAML
ms.date: 03/30/2017
helpviewer_keywords:
- XAML [WPF], TypeConverter class
ms.assetid: f6313e4d-e89d-497d-ac87-b43511a1ae4b
ms.openlocfilehash: 0b64088f43b69a982fc305fc16ad10edd1faa593
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69966053"
---
# <a name="typeconverters-and-xaml"></a>TypeConverter e XAML
Questo argomento illustra lo scopo della conversione del tipo string come funzionalità generale del linguaggio XAML. Nel .NET Framework la <xref:System.ComponentModel.TypeConverter> classe svolge uno scopo specifico come parte dell'implementazione di una classe personalizzata gestita che può essere usata come valore della proprietà nell'utilizzo degli attributi XAML. Se si scrive una classe personalizzata e si vuole che le istanze della classe siano utilizzabili come valori di attributo impostabili XAML, potrebbe essere necessario applicare <xref:System.ComponentModel.TypeConverterAttribute> un alla classe, scrivere una classe <xref:System.ComponentModel.TypeConverter> personalizzata o entrambi.  

## <a name="type-conversion-concepts"></a>Concetti relativi alla conversione di tipi  
  
### <a name="xaml-and-string-values"></a>Valori XAML e stringa  
 Quando si imposta un valore di attributo in un file XAML, il tipo iniziale di tale valore è una stringa di solo testo. Anche altre primitive, ad <xref:System.Double> esempio, sono inizialmente stringhe di testo per un processore XAML.  
  
 Un processore XAML necessita di due informazioni per elaborare un valore di attributo. La prima informazione è il tipo di valore della proprietà che si imposta. Qualsiasi stringa che definisce un valore di attributo e che viene elaborata in XAML deve essere convertita o risolta in un valore di quel tipo. Se il valore è una primitiva riconosciuta dal parser XAML (ad esempio un valore numerico), viene tentata una conversione diretta della stringa. Se il valore è un'enumerazione, la stringa viene usata per controllare la corrispondenza di un nome con una costante denominata in tale enumerazione. Se il valore non è né una primitiva riconosciuta dal parser né un'enumerazione, il tipo in questione deve essere in grado di fornire un'istanza del tipo o un valore basato su una stringa convertita. Ciò è possibile indicando una classe di convertitore di tipi. Il convertitore di tipi è una classe helper che fornisce valori di un'altra classe, sia per gli scenari XAML che, potenzialmente, per le chiamate nel codice .NET.  
  
### <a name="using-existing-type-conversion-behavior-in-xaml"></a>Uso del comportamento di conversione dei tipi esistente in XAML  
 A seconda del livello di conoscenza dei concetti XAML sottostanti, è possibile che si usi già il comportamento di conversione dei tipi nel codice XAML dell'applicazione di base senza rendersene conto. WPF, ad esempio, definisce letteralmente centinaia di proprietà che accettano un valore di <xref:System.Windows.Point>tipo. Un <xref:System.Windows.Point> oggetto è un valore che descrive una coordinata in uno spazio delle coordinate bidimensionale e ha effettivamente solo due proprietà importanti <xref:System.Windows.Point.X%2A> : <xref:System.Windows.Point.Y%2A>e. Quando si specifica un punto in XAML, lo si specifica come stringa con un delimitatore (in genere una virgola) tra <xref:System.Windows.Point.X%2A> i <xref:System.Windows.Point.Y%2A> valori e forniti. Ad esempio: `<LinearGradientBrush StartPoint="0,0" EndPoint="1,1"/>`.  
  
 Anche questo tipo semplice di <xref:System.Windows.Point> e il relativo utilizzo semplice in XAML coinvolgono un convertitore di tipi. In questo caso è la classe <xref:System.Windows.PointConverter>.  
  
 Il convertitore di tipi <xref:System.Windows.Point> per definito a livello di classe semplifica gli utilizzi di markup di tutte le proprietà che <xref:System.Windows.Point>accettano. Senza un convertitore di tipi, per l'esempio illustrato in precedenza sarebbe necessario ricorrere al seguente markup molto più dettagliato:  

```xaml
<LinearGradientBrush>
  <LinearGradientBrush.StartPoint>
    <Point X="0" Y="0"/>
  </LinearGradientBrush.StartPoint>
  <LinearGradientBrush.EndPoint>
    <Point X="1" Y="1"/>
  </LinearGradientBrush.EndPoint>
</LinearGradientBrush>
 ```
  
 La scelta tra l'uso di una stringa di conversione del tipo o di una sintassi equivalente più dettagliata è, in genere, una questione di stile di codifica. Anche il flusso di lavoro degli strumenti XAML può influire sul modo in cui vengono impostati i valori. Alcuni strumenti XAML tendono a generare la forma più dettagliata del markup perché è più facile eseguire il round trip nelle visualizzazioni delle finestre di progettazione o nel meccanismo di serializzazione.  
  
 I convertitori di tipi esistenti possono in genere essere individuati in WPF e .NET Framework tipi controllando una classe (o una proprietà) per <xref:System.ComponentModel.TypeConverterAttribute>la presenza di un oggetto applicato. Questo attributo assegnerà un nome alla classe che costituisce il convertitore di tipi di supporto per i valori del tipo in questione, sia per gli scenari XAML sia, eventualmente, per altri scopi.  
  
### <a name="type-converters-and-markup-extensions"></a>Convertitori di tipi ed estensioni di markup  
 Le estensioni di markup e i convertitori di tipi rivestono ruoli ortogonali in termini di comportamento del processore XAML e di scenari ai cui sono applicati. Anche se il contesto è disponibile per gli utilizzi di estensione di markup, il comportamento della conversione di tipi di proprietà in cui un'estensione di markup fornisce un valore in genere non è selezionato nelle implementazioni dell'estensione di markup. In altre parole, anche se un'estensione di markup restituisce una stringa di testo come output di `ProvideValue`, il comportamento di conversione dei tipi su tale stringa così come applicato a una proprietà o a un tipo di valore della proprietà specifico non viene richiamato. In genere, lo scopo di un'estensione di markup è quello di elaborare una stringa e restituire un oggetto senza coinvolgere alcun convertitore di tipi.  
  
 Una situazione comune che richiede un'estensione di markup invece che un convertitore di tipi è il riferimento a un oggetto già esistente. Nella migliore delle ipotesi, un convertitore di tipi senza stato può solo generare una nuova istanza, che potrebbe non essere il comportamento ottimale. Per altre informazioni sulle estensioni di markup, vedere [Estensioni di markup e XAML WPF](markup-extensions-and-wpf-xaml.md).  
  
### <a name="native-type-converters"></a>Convertitori di tipi nativi  
 Nell'implementazione WPF e .NET Framework del parser XAML ci sono determinati tipi che prevedono la gestione nativa della conversione del tipo, anche se non si tratta di tipi convenzionalmente considerati primitive. Un esempio dei tipi in questione è <xref:System.DateTime>. Il motivo è basato sul funzionamento dell'architettura .NET Framework: il tipo <xref:System.DateTime> è definito in mscorlib, la libreria più elementare di .NET. <xref:System.DateTime>non è consentita l'attribuzione di un attributo che deriva da un altro assembly che introduce<xref:System.ComponentModel.TypeConverterAttribute> una dipendenza (è da System), quindi il consueto meccanismo di individuazione del convertitore di tipi mediante attribuzione non può essere supportato. Il parser XAML ha invece di un elenco di tipi che necessitano di tale elaborazione nativa ed elabora questi tipi in modo analogo all'elaborazione delle primitive effettive. Nel caso di <xref:System.DateTime> questa operazione è necessario effettuare una chiamata <xref:System.DateTime.Parse%2A>a.  
  
<a name="Implementing_a_Type_Converter"></a>   
## <a name="implementing-a-type-converter"></a>Implementazione di un convertitore di tipi  
  
### <a name="typeconverter"></a>TypeConverter  
 Nell'esempio indicato in precedenza, è stata indicata la classe <xref:System.Windows.PointConverter>. <xref:System.Windows.Point> Per le implementazioni di .NET di XAML, tutti i convertitori di tipi usati per XAML sono classi che derivano dalla classe <xref:System.ComponentModel.TypeConverter>di base. La <xref:System.ComponentModel.TypeConverter> classe era presente nelle versioni di .NET Framework che precedono l'esistenza di XAML; uno degli usi originali era quello di fornire la conversione di stringa per le finestre di dialogo delle proprietà nelle finestre di progettazione visiva. Per XAML, il ruolo di <xref:System.ComponentModel.TypeConverter> viene espanso in modo da includere la classe di base per le conversioni da a stringa e da stringa che consentono l'analisi di un valore di attributo stringa ed eventualmente l'elaborazione di un valore di runtime di una particolare proprietà dell'oggetto in una stringa per serializzazione come attributo.  
  
 <xref:System.ComponentModel.TypeConverter>definisce quattro membri rilevanti per la conversione da e verso stringhe per finalità di elaborazione XAML:  
  
- <xref:System.ComponentModel.TypeConverter.CanConvertTo%2A>  
  
- <xref:System.ComponentModel.TypeConverter.CanConvertFrom%2A>  
  
- <xref:System.ComponentModel.TypeConverter.ConvertTo%2A>  
  
- <xref:System.ComponentModel.TypeConverter.ConvertFrom%2A>  
  
 Di questi, il metodo più importante è <xref:System.ComponentModel.TypeConverter.ConvertFrom%2A>. Questo metodo converte la stringa di input nel tipo di oggetto richiesto. In modo rigoroso <xref:System.ComponentModel.TypeConverter.ConvertFrom%2A> , è possibile implementare il metodo per convertire una gamma molto più ampia di tipi nel tipo di destinazione designato del convertitore e, di conseguenza, fornire finalità che si estendono oltre XAML, ad esempio il supporto delle conversioni in fase di esecuzione, ma per finalità XAML si tratta solo del percorso del codice in grado di <xref:System.String> elaborare un input importante.  
  
 Il metodo più importante successivo è <xref:System.ComponentModel.TypeConverter.ConvertTo%2A>. Se un'applicazione viene convertita in una rappresentazione del markup (ad esempio, se viene salvata in XAML come file) <xref:System.ComponentModel.TypeConverter.ConvertTo%2A> , è responsabile della creazione di una rappresentazione di markup. In questo caso, il percorso del codice che è importante per XAML è quando si `destinationType` passa <xref:System.String> un di.  
  
 <xref:System.ComponentModel.TypeConverter.CanConvertTo%2A> e <xref:System.ComponentModel.TypeConverter.CanConvertFrom%2A> sono metodi di supporto usati quando un servizio esegue una query sulle funzionalità dell'implementazione di <xref:System.ComponentModel.TypeConverter> . È necessario implementare questi metodi per restituire `true` per i casi specifici del tipo supportati dai metodi di conversione equivalenti del convertitore. Per XAML, si tratta in genere del tipo <xref:System.String> .  
  
### <a name="culture-information-and-type-converters-for-xaml"></a>Informazioni relative alle impostazioni cultura e convertitori di tipi per XAML  
 Ogni <xref:System.ComponentModel.TypeConverter> implementazione può avere una propria interpretazione di ciò che costituisce una stringa valida per una conversione e può anche usare o ignorare la descrizione del tipo passata come parametri. C'è un'importante considerazione per quanto riguarda le impostazioni cultura e la conversione di tipi in XAML. L'uso di stringhe localizzabili come valori di attributo è completamente supportato in XAML. L'uso di una stringa localizzabile come input del convertitore di tipi con requisiti di impostazioni cultura specifici non è però supportato, perché i convertitori di tipi per i valori di attributi XAML implicano un comportamento di analisi basato su un'unica lingua e sulle impostazioni cultura `en-US`. Per altre informazioni sui motivi legati alla progettazione alla base di questa limitazione, vedere la specifica del linguaggio XAML ([\[MS-XAML\]](https://go.microsoft.com/fwlink/?LinkId=114525)).  
  
 Un caso in cui le impostazioni cultura possono rappresentare un problema è ad esempio l'uso, in alcune impostazioni cultura, della virgola come separatore decimale per i numeri. Tale caratteristica è in conflitto con il comportamento di molti convertitori di tipi XAML di WPF, che usano la virgola come delimitatore (in base a precedenti storici come il formato X,Y comune o gli elenchi delimitati da virgole). Nemmeno il passaggio di impostazioni cultura nel codice XAML adiacente (impostando ad esempio `Language` o `xml:lang` sulle impostazioni cultura `sl-SI` che prevedono l'uso della virgola come separatore decimale) può consentire di risolvere il problema.  
  
### <a name="implementing-convertfrom"></a>Implementazione di ConvertFrom  
 Per essere utilizzabile come implementazione di <xref:System.ComponentModel.TypeConverter> che supporti XAML, il metodo <xref:System.ComponentModel.TypeConverter.ConvertFrom%2A> per il convertitore deve accettare una stringa come parametro `value` . Se la stringa ha un formato valido e può essere convertita dall' <xref:System.ComponentModel.TypeConverter> implementazione di, l'oggetto restituito deve supportare un cast nel tipo previsto dalla proprietà. In caso contrario, l'implementazione <xref:System.ComponentModel.TypeConverter.ConvertFrom%2A> deve restituire `null`.  
  
 Ogni <xref:System.ComponentModel.TypeConverter> implementazione può avere una propria interpretazione di ciò che costituisce una stringa valida per una conversione e può anche usare o ignorare la descrizione del tipo o i contesti di impostazioni cultura passati come parametri. L'elaborazione della sintassi XAML di WPF potrebbe tuttavia non passare i valori al contesto della descrizione del tipo in tutti i casi e potrebbe non passare nemmeno le impostazioni cultura basate su `xml:lang`.  
  
> [!NOTE]
> Non usare i caratteri parentesi graffa, in particolare {, come elemento del formato stringa. Questi caratteri vengono usati esclusivamente come punti di ingresso e di uscita di una sequenza di estensione del markup.  
  
### <a name="implementing-convertto"></a>Implementazione di ConvertTo  
 <xref:System.ComponentModel.TypeConverter.ConvertTo%2A> viene potenzialmente usato per il supporto della serializzazione. Il supporto della serializzazione tramite <xref:System.ComponentModel.TypeConverter.ConvertTo%2A> per il tipo personalizzato e il relativo convertitore di tipi non è un requisito assoluto. Tuttavia, se si implementa un controllo o si usa la serializzazione come parte delle funzionalità o della progettazione della classe, sarà necessario implementare <xref:System.ComponentModel.TypeConverter.ConvertTo%2A>.  
  
 Per essere utilizzabile come <xref:System.ComponentModel.TypeConverter> implementazione di che supporta XAML, <xref:System.ComponentModel.TypeConverter.ConvertTo%2A> il metodo per il convertitore deve accettare un'istanza del tipo (o un valore `value` ) supportata come parametro. Quando il `destinationType` parametro è di tipo <xref:System.String>, l'oggetto restituito deve essere in grado di eseguire il cast <xref:System.String>come. La stringa restituita deve rappresentare un valore serializzato di `value`. Idealmente, il formato di serializzazione scelto deve essere in grado di generare lo stesso valore se tale stringa venisse passata <xref:System.ComponentModel.TypeConverter.ConvertFrom%2A> all'implementazione dello stesso convertitore, senza perdite significative di informazioni.  
  
 Se il valore non può essere serializzato o il convertitore non supporta la serializzazione, <xref:System.ComponentModel.TypeConverter.ConvertTo%2A> l'implementazione deve `null`restituire ed è consentito generare un'eccezione in questo caso. Tuttavia, se si generano eccezioni, è necessario segnalare l'impossibilità di usare tale conversione come parte dell' <xref:System.ComponentModel.TypeConverter.CanConvertTo%2A> implementazione in modo che sia supportata la procedura consigliata per il controllo con <xref:System.ComponentModel.TypeConverter.CanConvertTo%2A> First per evitare eccezioni.  
  
 Se `destinationType` il parametro non è di <xref:System.String>tipo, è possibile scegliere la gestione del convertitore. In genere, viene ripristinata la gestione dell'implementazione di base, che <xref:System.ComponentModel.TypeConverter.ConvertTo%2A> in basemost genera un'eccezione specifica.  
  
### <a name="implementing-canconvertto"></a>Implementazione di CanConvertTo  
 L'implementazione di <xref:System.ComponentModel.TypeConverter.CanConvertTo%2A> deve restituire `true` per un oggetto `destinationType` di tipo <xref:System.String>; in caso contrario, deve rinviare all'implementazione di base.  
  
### <a name="implementing-canconvertfrom"></a>Implementazione di CanConvertFrom  
 L'implementazione di <xref:System.ComponentModel.TypeConverter.CanConvertFrom%2A> deve restituire `true` per un oggetto `sourceType` di tipo <xref:System.String>; in caso contrario, deve rinviare all'implementazione di base.  
  
<a name="Applying_the_TypeConverterAttribute"></a>   
## <a name="applying-the-typeconverterattribute"></a>Applicazione di TypeConverterAttribute  
 Affinché il convertitore di tipi personalizzato venga usato come convertitore di tipi di azione per una classe personalizzata da un processore XAML, è necessario applicare alla definizione [!INCLUDE[TLA#tla_netframewkattr](../../../../includes/tlasharptla-netframewkattr-md.md)] della <xref:System.ComponentModel.TypeConverterAttribute> classe. L'oggetto <xref:System.ComponentModel.TypeConverterAttribute.ConverterTypeName%2A> specificato tramite l'attributo deve corrispondere al nome di tipo del convertitore dei tipi personalizzato. Se si applica questo attributo, quando un processore XAML gestisce valori per i quali il tipo di proprietà usa il tipo di classe personalizzato, può usare stringhe di input e restituire istanze di oggetti.  
  
 Si può anche fornire un convertitore dei tipi per le singole proprietà. Anziché applicare un [!INCLUDE[TLA#tla_netframewkattr](../../../../includes/tlasharptla-netframewkattr-md.md)] <xref:System.ComponentModel.TypeConverterAttribute> alla definizione della classe, applicarlo a una definizione della proprietà (la definizione principale, non le implementazioni di `get`/`set` al suo interno). Il tipo della proprietà deve corrispondere al tipo elaborato dal convertitore dei tipi personalizzato. Se questo attributo viene applicato, quando un processore XAML gestisce i valori di tale proprietà, può elaborare stringhe di input e restituire istanze di oggetti. La tecnica del convertitore dei tipi per proprietà è particolarmente utile se si sceglie di usare un tipo di proprietà da Microsoft .NET Framework o da un'altra libreria in cui non è possibile controllare la definizione della <xref:System.ComponentModel.TypeConverterAttribute> classe e non è possibile applicare un oggetto.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.ComponentModel.TypeConverter>
- [Cenni preliminari su XAML (WPF)](xaml-overview-wpf.md)
- [Estensioni di markup e XAML WPF](markup-extensions-and-wpf-xaml.md)
- [Descrizione dettagliata della sintassi XAML](xaml-syntax-in-detail.md)
