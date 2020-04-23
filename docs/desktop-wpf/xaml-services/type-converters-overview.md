---
title: Panoramica dei convertitori di tipi per XAML
ms.date: 03/30/2017
helpviewer_keywords:
- XAML [XAML Services], type converters
- XAML [XAML Services], TypeConverter
- type conversion for XAML [XAML Services]
ms.assetid: 51a65860-efcb-4fe0-95a0-1c679cde66b7
ms.openlocfilehash: c3c69aebacd140a14e74545d601c0207cb8de681
ms.sourcegitcommit: c2d9718996402993cf31541f11e95531bc68bad0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/27/2020
ms.locfileid: "82071633"
---
# <a name="overview-of-type-converters-for-xaml"></a>Panoramica dei convertitori di tipi per XAMLOverview of type converters for XAML

I convertitori di tipi forniscono la logica per un writer di oggetti che esegue una conversione da una stringa nel markup XAML in particolari oggetti in un oggetto grafico. Nei servizi XAML .NET, il convertitore di <xref:System.ComponentModel.TypeConverter>tipi deve essere una classe che deriva da . Alcuni convertitori supportano anche il percorso di salvataggio XAML e possono essere usati per serializzare un oggetto in un formato stringa nel markup di serializzazione. Questo argomento descrive come e quando vengono richiamati i convertitori di tipi in XAML e vengono forniti consigli di implementazione per gli override del metodo di <xref:System.ComponentModel.TypeConverter>.

## <a name="type-conversion-concepts"></a>Concetti relativi alla conversione di tipi

Nelle sezioni seguenti vengono illustrati i concetti di base sull'utilizzo delle stringhe da parte di XAML e sull'utilizzo dei convertitori di tipi nei servizi XAML .NET da parte dei writer di oggetti.

### <a name="xaml-and-string-values"></a>Valori XAML e stringa

Quando si imposta un valore dell'attributo in un file XAML, il tipo iniziale del valore è una stringa in senso generale e un valore dell'attributo di stringa in XML. Anche altre primitive, ad esempio <xref:System.Double> , sono inizialmente stringhe per un processore XAML.

Nella maggior parte dei casi, un processore XAML deve disporre di due informazioni per elaborare un valore di attributo. La prima informazione è il tipo di valore della proprietà che si imposta. Qualsiasi stringa che definisce un valore di attributo e che viene elaborata in XAML deve essere convertita o risolta in un valore di quel tipo. Se il valore è una primitiva riconosciuta dal parser XAML (ad esempio un valore numerico), viene tentata una conversione diretta della stringa. Se il valore dell'attributo fa riferimento a un'enumerazione, nella stringa specificata viene verificata la corrispondenza del nome con una costante denominata in tale enumerazione. Se il valore non è una primitiva riconosciuta dal parser o un nome costante da un'enumerazione, il tipo applicabile deve essere in grado di fornire un valore o un riferimento basato su una stringa convertita.

> [!NOTE]
> Le direttive del linguaggio XAML non usano convertitori di tipi.

### <a name="type-converters-and-markup-extensions"></a>Convertitori di tipi ed estensioni di markup

Gli utilizzi di estensioni di markup devono essere gestiti da un processore XAML prima che questo verifichi il tipo di proprietà e altre considerazioni. Ad esempio, se una proprietà impostata come attributo viene associata normalmente a una conversione di tipi, ma in un caso particolare viene impostata mediante un utilizzo dell'estensione di markup, viene innanzitutto elaborato il comportamento dell'estensione di markup. Una situazione comune che richiede un'estensione di markup è la creazione di un riferimento a un oggetto già esistente. Per questo scenario, un convertitore di tipi senza stato può solo generare una nuova istanza, che non necessariamente è appropriata. Per ulteriori informazioni sulle estensioni di markup, vedere [Markup Extensions for XAML Overview](markup-extensions-overview.md).

### <a name="native-type-converters"></a>Convertitori di tipi nativi

Nelle implementazioni dei servizi XAML di Windows Presentation Foundation (WPF) e .NET sono disponibili alcuni tipi CLR con gestione della conversione dei tipi nativi. Tuttavia, tali tipi CLR non sono convenzionalmente considerati come primitive. Un esempio dei tipi in questione è <xref:System.DateTime>. Un motivo consiste nel funzionamento dell'architettura di .NET Framework: il tipo <xref:System.DateTime> è definito in mscorlib, la libreria più elementare di .NET. <xref:System.DateTime>non è consentito essere attribuito con un attributo proveniente<xref:System.ComponentModel.TypeConverterAttribute> da un altro assembly che introduce una dipendenza ( è da System). Pertanto, il meccanismo di individuazione del convertitore di tipi consueto attribuendo non può essere supportato. Il parser XAML dispone invece di un elenco di tipi che necessitano di elaborazione nativa ed elabora questi tipi con modalità analoghe all'elaborazione delle primitive effettive. Nel caso di <xref:System.DateTime>, l'elaborazione comporta una chiamata a <xref:System.DateTime.Parse%2A>.

## <a name="implementing-a-type-converter"></a>Implementazione di un convertitore di tipi

Le sezioni seguenti illustrano l'API della classe <xref:System.ComponentModel.TypeConverter> .

### <a name="typeconverter"></a>TypeConverter

In Servizi XAML .NET tutti i convertitori di tipi utilizzati per <xref:System.ComponentModel.TypeConverter>scopi XAML sono classi che derivano dalla classe base. La classe <xref:System.ComponentModel.TypeConverter> era presente nelle versioni di .NET Framework precedenti all'introduzione di XAML; in origine, uno degli scenari di <xref:System.ComponentModel.TypeConverter> consisteva nel fornire la conversione delle stringhe per gli editor delle proprietà nelle finestre di progettazione visiva.

Per XAML, il ruolo di <xref:System.ComponentModel.TypeConverter> viene esteso. In XAML, <xref:System.ComponentModel.TypeConverter> è la classe base che fornisce il supporto per determinate conversioni da stringa e in stringa. La conversione da stringa consente l'analisi di un valore dell'attributo di stringa da XAML. La conversione in stringa può permettere l'elaborazione di un valore di runtime di una particolare proprietà dell'oggetto in un attributo in XAML per la serializzazione.

<xref:System.ComponentModel.TypeConverter> definisce quattro membri rilevanti per la conversione da e in stringa per l'elaborazione XAML:

- <xref:System.ComponentModel.TypeConverter.CanConvertTo%2A>

- <xref:System.ComponentModel.TypeConverter.CanConvertFrom%2A>

- <xref:System.ComponentModel.TypeConverter.ConvertTo%2A>

- <xref:System.ComponentModel.TypeConverter.ConvertFrom%2A>

Di questi membri, il metodo più importante è <xref:System.ComponentModel.TypeConverter.ConvertFrom%2A>, che converte la stringa di input nel tipo di oggetto richiesto. È possibile implementare il metodo <xref:System.ComponentModel.TypeConverter.ConvertFrom%2A> per convertire una più vasta gamma di tipi nel tipo di destinazione previsto dal convertitore. Il metodo assolve quindi scopi che si estendono oltre quelli definiti per XAML, ad esempio il supporto delle conversioni in fase di esecuzione. Per quanto riguarda XAML, tuttavia, l'unico elemento importante è il percorso del codice che consente di elaborare un input <xref:System.String> .

Il secondo metodo più <xref:System.ComponentModel.TypeConverter.ConvertTo%2A>importante è . Se un'applicazione viene convertita in una rappresentazione di markup (ad esempio, se viene salvata in XAML come file), <xref:System.ComponentModel.TypeConverter.ConvertTo%2A> è coinvolta nello scenario più ampio di un writer di testo XAML per produrre una rappresentazione di markup. In questo caso, il percorso di codice importante per XAML è il passaggio di `destinationType` di <xref:System.String>da parte del chiamante.

<xref:System.ComponentModel.TypeConverter.CanConvertTo%2A> e <xref:System.ComponentModel.TypeConverter.CanConvertFrom%2A> sono metodi di supporto usati quando un servizio esegue una query sulle funzionalità dell'implementazione di <xref:System.ComponentModel.TypeConverter> . È necessario implementare questi metodi per restituire `true` per i casi specifici del tipo supportati dai metodi di conversione equivalenti del convertitore. Per XAML, si tratta in genere del tipo <xref:System.String> .

### <a name="culture-information-and-type-converters-for-xaml"></a>Informazioni relative alle impostazioni cultura e convertitori di tipi per XAML

Ogni implementazione di <xref:System.ComponentModel.TypeConverter> può interpretare in modo univoco il concetto di stringa valida per una conversione e può quindi usare o ignorare la descrizione del tipo passata come parametri. Una considerazione importante circa le impostazioni cultura e la conversione di tipi XAML: anche se l'uso di stringhe localizzabili come valori di attributo è supportato da XAML, non è possibile usare queste stringhe come input del convertitore di tipi con requisiti specifici per le impostazioni cultura. Questa limitazione è dovuta al fatto che i convertitori di tipi per i valori di attributo XAML implicano necessariamente un comportamento di elaborazione XAML basato su un'unica lingua che usa le impostazioni cultura `en-US` . Per ulteriori informazioni sui motivi di progettazione di questa restrizione, vedere la specifica del linguaggio XAML ([\[MS-XAML\]](https://docs.microsoft.com/previous-versions/msp-n-p/ff650760(v=pandp.10))) o Cenni preliminari sulla [globalizzazione e localizzazione WPF](../../framework/wpf/advanced/wpf-globalization-and-localization-overview.md).

Un esempio delle problematiche che possono presentarsi con le impostazioni cultura è rappresentato dal separatore decimale per i numeri in formato stringa, che per alcune impostazioni cultura è la virgola anziché il punto. Quest'uso è in conflitto con il comportamento di molti convertitori di tipi esistenti, che prevede l'uso della virgola come delimitatore. Il passaggio di impostazioni cultura tramite `xml:lang` nel codice XAML adiacente non risolve il problema.

### <a name="implementing-convertfrom"></a>Implementazione di ConvertFrom

Per essere utilizzabile come implementazione di <xref:System.ComponentModel.TypeConverter> che supporti XAML, il metodo <xref:System.ComponentModel.TypeConverter.ConvertFrom%2A> per il convertitore deve accettare una stringa come parametro `value` . Se la stringa ha un formato valido e può essere convertita dall'implementazione di <xref:System.ComponentModel.TypeConverter> , l'oggetto restituito deve supportare un cast nel tipo previsto dalla proprietà. In caso contrario, l'implementazione <xref:System.ComponentModel.TypeConverter.ConvertFrom%2A> deve restituire `null`.

Ogni implementazione di <xref:System.ComponentModel.TypeConverter> può interpretare in modo univoco il concetto di stringa valida per una conversione e può anche usare o ignorare i contesti di descrizione del tipo o di impostazione cultura passati come parametri. Tuttavia, l'elaborazione della sintassi XAML di WPF potrebbe non passare i valori al contesto della descrizione del tipo in tutti i casi e potrebbe perfino non passare le impostazioni cultura basate su `xml:lang`.

> [!NOTE]
> Non utilizzare le parentesi graffe ({}), in particolare la parentesi graffa di apertura , come elemento del formato della stringa. Questi caratteri vengono usati esclusivamente come punti di ingresso e di uscita di una sequenza di estensione del markup.

È opportuno generare un'eccezione quando il convertitore di tipi deve avere <xref:System.IServiceProvider.GetService%2A> accesso a un servizio XAML dal writer di oggetti dei servizi XAML .NET, ma la chiamata effettuata sul contesto non restituisce tale servizio.

### <a name="implementing-convertto"></a>Implementazione di ConvertTo

<xref:System.ComponentModel.TypeConverter.ConvertTo%2A> viene potenzialmente usato per il supporto della serializzazione. Il supporto della serializzazione tramite <xref:System.ComponentModel.TypeConverter.ConvertTo%2A> per il tipo personalizzato e il relativo convertitore di tipi non è un requisito assoluto. Tuttavia, se si implementa un controllo o si usa la serializzazione come parte delle funzionalità o della progettazione della classe, sarà necessario implementare <xref:System.ComponentModel.TypeConverter.ConvertTo%2A>.

Per essere utilizzabile come implementazione di <xref:System.ComponentModel.TypeConverter> che supporti XAML, il metodo <xref:System.ComponentModel.TypeConverter.ConvertTo%2A> per il convertitore deve accettare un'istanza del tipo (o un valore) supportata come parametro `value` . Quando il parametro `destinationType` è di tipo <xref:System.String>, deve essere possibile eseguire il cast dell'oggetto restituito come <xref:System.String>. La stringa restituita deve rappresentare un valore serializzato di `value`. In teoria, il formato di serializzazione scelto deve essere in grado di generare lo stesso valore che si otterrebbe se quella stringa venisse passata all'implementazione di <xref:System.ComponentModel.TypeConverter.ConvertFrom%2A> dello stesso convertitore, senza perdite significative di informazioni.

Se il valore non può essere serializzato o il convertitore non supporta la serializzazione, l'implementazione di <xref:System.ComponentModel.TypeConverter.ConvertTo%2A> deve restituire `null` e può generare un'eccezione. Tuttavia, se si generano eccezioni, sarà necessario segnalare l'impossibilità di usare tale conversione nell'implementazione di <xref:System.ComponentModel.TypeConverter.CanConvertTo%2A> in modo da supportare un controllo preventivo con <xref:System.ComponentModel.TypeConverter.CanConvertTo%2A> , che rappresenta la procedura consigliata per evitare eccezioni.

Se il parametro `destinationType` non è di tipo <xref:System.String>, è possibile scegliere la gestione del convertitore. In genere viene ripristinata la gestione dell'implementazione di base, che nella forma base di <xref:System.ComponentModel.TypeConverter.ConvertTo%2A> genera un'eccezione specifica.

È opportuno generare un'eccezione quando il convertitore di tipi deve avere <xref:System.IServiceProvider.GetService%2A> accesso a un servizio XAML dal writer di oggetti dei servizi XAML .NET, ma la chiamata effettuata sul contesto non restituisce tale servizio.

### <a name="implementing-canconvertfrom"></a>Implementazione di CanConvertFrom

L'implementazione di <xref:System.ComponentModel.TypeConverter.CanConvertFrom%2A> deve restituire `true` per un oggetto `sourceType` di tipo <xref:System.String> ; in caso contrario, deve rinviare all'implementazione di base. Non generare eccezioni da <xref:System.ComponentModel.TypeConverter.CanConvertFrom%2A>.

### <a name="implementing-canconvertto"></a>Implementazione di CanConvertTo

L'implementazione di <xref:System.ComponentModel.TypeConverter.CanConvertTo%2A> deve restituire `true` per un oggetto `destinationType` di tipo <xref:System.String>; in caso contrario, deve rinviare all'implementazione di base. Non generare eccezioni da <xref:System.ComponentModel.TypeConverter.CanConvertTo%2A>.

## <a name="applying-the-typeconverterattribute"></a>Applicazione di TypeConverterAttribute

Affinché il convertitore di tipi personalizzato venga utilizzato come convertitore di tipi <xref:System.ComponentModel.TypeConverterAttribute> che agisce per una classe personalizzata dai servizi XAML .NET, è necessario applicare l'oggetto alla definizione della classe. L'oggetto <xref:System.ComponentModel.TypeConverterAttribute.ConverterTypeName%2A> specificato tramite l'attributo deve corrispondere al nome di tipo del convertitore dei tipi personalizzato. Se si applica questo attributo, quando un processore XAML gestisce valori per cui il tipo di proprietà usa il tipo di classe personalizzato, può immettere stringhe e restituire istanze di oggetti.

Si può anche fornire un convertitore dei tipi per le singole proprietà. Anziché applicare <xref:System.ComponentModel.TypeConverterAttribute> un alla definizione della classe, applicarlo a una `get` / `set` definizione di proprietà (la definizione principale, non le implementazioni al suo interno). Il tipo della proprietà deve corrispondere al tipo elaborato dal convertitore dei tipi personalizzato. Se questo attributo viene applicato, quando un processore XAML gestisce i valori di quella proprietà, può elaborare stringhe di input e restituire istanze di oggetti. La tecnica del convertitore di tipi per proprietà è utile se si sceglie di utilizzare un tipo di proprietà <xref:System.ComponentModel.TypeConverterAttribute> da Microsoft .NET Framework o da un'altra libreria in cui non è possibile controllare la definizione della classe e non è possibile applicare un tipo.

Per fornire un comportamento di conversione di tipi per un membro associato personalizzato, applicare <xref:System.ComponentModel.TypeConverterAttribute> al metodo della funzione di accesso `Get` del modello di implementazione per il membro associato.

## <a name="accessing-service-provider-context-from-a-markup-extension-implementation"></a>Accesso al contesto del provider di servizi da un'implementazione dell'estensione di markup

I servizi disponibili sono gli stessi per qualsiasi convertitore di valori. L'unica differenza risiede nel modo in cui ogni convertitore di valori riceve il contesto del servizio. L'accesso ai servizi e i servizi disponibili sono illustrati nell'argomento [Type Converters and Markup Extensions for XAML](type-converters-and-markup-extensions.md).

## <a name="type-converters-in-the-xaml-node-stream"></a>Convertitori di tipi nel flusso di nodi XAML

Se si usa un flusso del nodo XAML, l'azione o il risultato finale di un convertitore di tipi non è ancora eseguito. In un percorso di caricamento, la stringa dell'attributo che necessita di una conversione di tipi ai fini del caricamento resta sotto forma di valore testuale all'interno di un membro iniziale e di un membro finale. Il convertitore di tipi eventualmente necessario per questa operazione può essere determinato tramite la proprietà <xref:System.Xaml.XamlMember.TypeConverter%2A?displayProperty=nameWithType> . Tuttavia, per ottenere un valore valido da <xref:System.Xaml.XamlMember.TypeConverter%2A?displayProperty=nameWithType> è necessario avere un contesto dello schema XAML, che può accedere a queste informazioni tramite il membro sottostante, o il tipo del valore dell'oggetto usato dal membro. Il richiamo del comportamento di conversione di tipi richiede anche il contesto dello schema XAML poiché ciò richiede il mapping dei tipi e la creazione di un'istanza del convertitore.

## <a name="see-also"></a>Vedere anche

- <xref:System.ComponentModel.TypeConverterAttribute>
- [Convertitori di tipi ed estensioni di markup per XAML](type-converters-and-markup-extensions.md)
- [Panoramica di XAML (WPF)](../fundamentals/xaml.md)
