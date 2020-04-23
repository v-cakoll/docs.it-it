---
title: Contesti di servizio disponibili per convertitori di tipi ed estensioni di markup
ms.date: 03/30/2017
helpviewer_keywords:
- XAML [XAML Services], type converter services how-to
ms.assetid: b4dad00f-03da-4579-a4e9-d8d72d2ccbce
ms.openlocfilehash: 59c4385eb4df8c622be6164cdb0a1a911c445ca8
ms.sourcegitcommit: c2d9718996402993cf31541f11e95531bc68bad0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/27/2020
ms.locfileid: "82071661"
---
# <a name="service-contexts-available-to-type-converters-and-markup-extensions"></a>Contesti di servizio disponibili per convertitori di tipi ed estensioni di markup
Gli autori dei tipi che supportano gli utilizzi di convertitori di tipi e estensioni di markup devono spesso disporre di informazioni contestuali sulla posizione di utilizzo nel markup o nella struttura dell'oggetto grafico circostante. Le informazioni potrebbero essere necessarie per garantire che venga creata correttamente un'istanza dell'oggetto fornito o che vengano definiti i riferimenti dell'oggetto agli oggetti esistenti nell'oggetto grafico. Quando si usano i servizi XAML .NET, il contesto che potrebbe essere necessario viene esposto come una serie di interfacce di servizio. Nel codice di supporto del convertitore di tipi o dell'estensione di markup può essere eseguita una query per un servizio usando il contesto di un provider di servizi disponibile e passato da <xref:System.Xaml.XamlObjectWriter> o da tipi correlati. Il contesto dello schema XAML è disponibile direttamente attraverso uno di questi servizi. In questo argomento viene illustrato come accedere ai contesti di servizio da un'implementazione del convertitore di valori e vengono elencati i servizi generalmente disponibili e i relativi ruoli.

## <a name="obtaining-services"></a>Acquisizione di servizi

In qualità di implementatore di un convertitore di valori, è spesso necessario accedere a un determinato tipo di contesto in cui viene applicato il convertitore di valori. Questo contesto può includere informazioni quali il contesto dello schema XAML attivo, l'accesso al sistema di mapping dei tipi fornito dal contesto dello schema XAML e dal writer di oggetti XAML e così via. I servizi disponibili per un'implementazione di un'estensione di markup o un convertitore tipo vengono comunicati tramite i parametri di contesto che fanno parte della firma di ogni metodo virtuale. In ogni caso, si dispone di <xref:System.IServiceProvider> implementato nel contesto e si può chiamare <xref:System.IServiceProvider.GetService%2A?displayProperty=nameWithType> per richiedere un servizio.

## <a name="services-for-a-markup-extension"></a>Servizi per un'estensione di markup

<xref:System.Windows.Markup.MarkupExtension> dispone un solo di metodo virtuale, <xref:System.Windows.Markup.MarkupExtension.ProvideValue%2A>. Il parametro `serviceProvider` di input rappresenta il modo in cui i servizi vengono comunicati alle implementazioni quando l'estensione di markup viene chiamata da un processore XAML. Nello pseudocodice seguente viene illustrato il modo in cui un'implementazione dell'estensione di markup potrebbe eseguire query per i servizi nel relativo metodo <xref:System.Windows.Markup.MarkupExtension.ProvideValue%2A>:

```csharp
public override object ProvideValue(IServiceProvider serviceProvider)
{
...
    // Get the IXamlTypeResolver from the service provider
    if (serviceProvider == null)
    {
        throw new ArgumentNullException("serviceProvider");
    }
    IXamlTypeResolver xamlTypeResolver = serviceProvider.GetService(typeof(IXamlTypeResolver)) as IXamlTypeResolver;
    if (xamlTypeResolver == null)
   {
        throw new ArgumentException("IXamlTypeResolver"));
    }
...
}
```

## <a name="services-for-a-type-converter"></a>Servizi per un convertitore di tipi

<xref:System.ComponentModel.TypeConverter> dispone di quattro metodi virtuali che usano un contesto del servizio e che supportano utilizzi di XAML. Ognuno di questi metodi passa un parametro `context` di input. Questo parametro è di tipo <xref:System.ComponentModel.ITypeDescriptorContext>, ma tale interfaccia eredita <xref:System.IServiceProvider>ed è quindi disponibile un metodo <xref:System.IServiceProvider.GetService%2A> per le implementazioni di convertitori di tipi.

Nello pseudocodice seguente viene illustrato il modo in cui un'implementazione del convertitore di tipi per utilizzi di XAML potrebbe eseguire query per i servizi in uno dei relativi override, in questo caso <xref:System.ComponentModel.TypeConverter.ConvertFrom%2A>:

```csharp
public override object ConvertFrom(ITypeDescriptorContext typeDescriptorContext,
  CultureInfo cultureInfo,
  object source)
{
    IRootObjectProvider rootProvider = typeDescriptorContext.GetService(typeof(IRootObjectProvider)) as IRootObjectProvider;
    if (rootProvider != null && source is String)
    {
        //return something, else ...
    }
    throw GetConvertFromException(source);
}
```

## <a name="services-for-a-value-serializer"></a>Servizi per un serializzatore di valori

Per il contesto del serializzatore di valori, si usa un tipo di provider di servizi specifico per la classe <xref:System.Windows.Markup.ValueSerializer> , <xref:System.Windows.Markup.IValueSerializerContext>. Tale contesto viene passato agli override dei quattro metodi virtuali di <xref:System.Windows.Markup.ValueSerializer> . Per ottenere servizi, chiamare <xref:System.IServiceProvider.GetService%2A> dal contesto.

## <a name="using-the-xaml-service-provider-contexts"></a>Utilizzo dei contesti di provider di servizi XAML

Il provider <xref:System.IServiceProvider.GetService%2A> di servizi per l'accesso ai servizi XAML disponibili per le estensioni di markup o i convertitori di tipi viene implementato come classe interna, con esposizione solo tramite l'interfaccia e come viene passata nel contesto pertinente. Ogni volta che un'operazione di elaborazione XAML nelle implementazioni predefinite dei servizi XAML .NET del percorso di caricamento o del percorso di salvataggio richiama l'estensione di markup pertinente o i metodi del convertitore di tipi che richiedono un contesto del servizio, questo oggetto interno viene passato. A seconda delle circostanze, il contesto del servizio del sistema fornisce `MarkupExtensionContext` o `TextSyntaxContext`, sebbene le specifiche di entrambe queste classi siano interne. L'interazione con queste classi è limitato alla richiesta dei servizi da tali classi tramite <xref:System.IServiceProvider.GetService%2A>.

## <a name="available-services-from-the-net-xaml-service-context"></a>Servizi disponibili dal contesto del servizio XAML .NET

I servizi XAML .NET definiscono i servizi per le estensioni di markup, i convertitori di tipi, i serializzatori di valori e potenzialmente altri utilizzi. Nelle sezioni seguenti viene descritto ognuno di questi servizi e forniscono materiale sussidiario sulla modalità di utilizzo del servizio in un'implementazione.

### <a name="iserviceprovider"></a>IServiceProvider

**Documentazione di riferimento**:<xref:System.IServiceProvider>

**Relativo a:** Funzionamento di base di un'infrastruttura basata su <xref:System.IServiceProvider.GetService%2A?displayProperty=nameWithType>servizi in .NET in modo che sia possibile chiamare .

### <a name="itypedescriptorcontext"></a>ITypeDescriptorContext

**Documentazione di riferimento**:<xref:System.ComponentModel.ITypeDescriptorContext>

Classe derivata da <xref:System.IServiceProvider>. Questa classe rappresenta il contesto nelle firme <xref:System.ComponentModel.TypeConverter> standard; <xref:System.ComponentModel.TypeConverter> è una classe già esistente da .NET Framework 1.0. Anticipa XAML e lo scenario XAML <xref:System.ComponentModel.TypeConverter> per la conversione del tipo valore stringa. Nel contesto dei servizi <xref:System.ComponentModel.TypeConverter> XAML .NET, i metodi di vengono implementati in modo esplicito. Il comportamento dell'implementazione esplicita indica ai chiamanti che l'API <xref:System.ComponentModel.ITypeDescriptorContext> non è relativa a sistemi di tipi XAML o alla lettura o scrittura di oggetti da XAML. <xref:System.ComponentModel.ITypeDescriptorContext.Container%2A>, <xref:System.ComponentModel.ITypeDescriptorContext.Instance%2A>e <xref:System.ComponentModel.ITypeDescriptorContext.PropertyDescriptor%2A> in `null` genere restituiscono da contesti dei servizi XAML .NET.

### <a name="ivalueserializercontext"></a>IValueSerializerContext

**Documentazione di riferimento**:<xref:System.Windows.Markup.IValueSerializerContext>

Deriva da <xref:System.ComponentModel.ITypeDescriptorContext> e si basa anche su implementazioni esplicite per eliminare le implicazioni erronee relative al sistema di tipi XAML. Supporta i metodi di supporto statici della ricerca in <xref:System.Windows.Markup.ValueSerializer>.

### <a name="ixamltyperesolver"></a>IXamlTypeResolver

**Documentazione di riferimento**:<xref:System.Windows.Markup.IXamlTypeResolver>

**Definito da:** <xref:System.Windows.Markup> spazio dei nomi, assembly System.XamlDefined by: namespace, System.Xaml assembly  

**Relativo a:** scenari del percorso di caricamento e interazione con il contesto dello schema XAML

**API del servizio:**  <xref:System.Windows.Markup.IXamlTypeResolver.Resolve%2A>

Può influire sul mapping dei tipi da XAML a CLR che si rende necessario quando il writer XAML costruisce un oggetto CLR in un oggetto grafico. <xref:System.Windows.Markup.IXamlTypeResolver.Resolve%2A> elabora una stringa di prefisso potenzialmente qualificata che corrisponde al nome di un tipo XAML (<xref:System.Xaml.XamlType.Name%2A?displayProperty=nameWithType>) e restituisce un oggetto <xref:System.Type>CLR. La risoluzione dei tipi in genere dipende in misura rilevante dal contesto dello schema XAML. Determinati aspetti, ad esempio quali assembly vengono caricati e a quali di questi è possibile o necessario accedere per la risoluzione di tipi, vengono considerati esclusivamente dal contesto dello schema XAML.

### <a name="iuricontext"></a>IUriContext

**Documentazione di riferimento**:<xref:System.Windows.Markup.IUriContext>

**Definito da:** <xref:System.Windows.Markup> spazio dei nomi, assembly System.XamlDefined by: namespace, System.Xaml assembly  

**Relativo a:** gestione del percorso di caricamento e del percorso di salvataggio di valori di membro che sono valori di URI o `x:Uri` .

**API del servizio:**  <xref:System.Windows.Markup.IUriContext.BaseUri%2A>

Questo servizio segnala una radice dell'URI disponibile a livello globale, se presente. La radice dell'URI può essere usata per risolvere gli URI relativi in URI assoluti o viceversa. Questo scenario riguarda principalmente i servizi dell'applicazione esposti da un particolare framework o le funzionalità di una classe di elementi radice di uso frequente in un framework. L'URI di base può essere stabilito come impostazione del reader XAML, che viene quindi passata al writer di oggetti XAML e segnalata da questo servizio.

### <a name="iambientprovider"></a>IAmbientProvider

**Documentazione di riferimento**:<xref:System.Xaml.IAmbientProvider>

**Definito da:** <xref:System.Xaml> spazio dei nomi, assembly System.XamlDefined by: namespace, System.Xaml assembly  

**Relativo a:** gestione del percorso di caricamento e rinvii o ottimizzazioni della ricerca di tipi.

**API**  <xref:System.Xaml.IAmbientProvider.GetAllAmbientValues%2A>di servizio: , altre tre.

Il concetto di ambiente in XAML è relativo a una tecnica per contrassegnare un particolare membro di un tipo come ambiente. In alternativa, un tipo può costituire un ambiente in modo che tutti i valori di proprietà contenenti un'istanza del tipo debbano essere considerati proprietà di ambiente. Le estensioni di markup o convertitori di tipi che si trovano più all'interno nel flusso del nodo XAML e sono discendenti nell'oggetto grafico possono accedere alla proprietà di ambiente o l'istanza del tipo al momento del caricamento oppure usare la conoscenza della struttura di ambiente al momento del salvataggio. Ciò può influire sul grado di qualificazione necessario per la risoluzione dei tipi per altri servizi, ad esempio per <xref:System.Windows.Markup.IXamlTypeResolver> o per `x:Type`. Vedere anche <xref:System.Xaml.AmbientPropertyValue>.

### <a name="ixamlschemacontextprovider"></a>IXamlSchemaContextProvider

**Documentazione di riferimento**:<xref:System.Xaml.IXamlSchemaContextProvider>

**Definito da:** <xref:System.Xaml> spazio dei nomi, assembly System.XamlDefined by: namespace, System.Xaml assembly  

**Relativo a:** percorso di caricamento e qualsiasi operazione che deve risolvere un tipo XAML in un tipo di supporto.

**API del servizio:**  <xref:System.Xaml.IXamlSchemaContextProvider.SchemaContext%2A>

Il contesto dello schema XAML è necessario per qualsiasi operazione di caricamento posticipato, poiché lo stesso contesto dello schema deve agire sull'area posticipata per integrare il contenuto posticipato. Per altre informazioni sul ruolo del contesto dello schema XAML, vedere [XAML Services](../../../api/index.md).

### <a name="irootobjectprovider"></a>IRootObjectProvider

**Documentazione di riferimento**:<xref:System.Xaml.IRootObjectProvider>

**Definito da:** <xref:System.Xaml> spazio dei nomi, assembly System.XamlDefined by: namespace, System.Xaml assembly  

**Relativo a:** percorso di caricamento.

**API del servizio:**  <xref:System.Xaml.IRootObjectProvider.RootObject%2A>

Il servizio riguarda i servizi dell'applicazione esposti da un particolare framework o dalle funzionalità di una classe di elementi radice di uso frequente in un framework. Uno scenario per l'acquisizione dell'oggetto radice è la connessione tra code-behind e collegamento di eventi. Ad esempio, l'implementazione di WPF di `x:Class` viene usata per la compilazione del markup e il collegamento di qualsiasi attributo del gestore eventi che si trova in corrispondenza di qualsiasi altra posizione nel markup XAML. Il punto di connessione delle classi parziali definite da markup e code-behind per- la compilazione di markup si trova in corrispondenza dell'elemento radice.

### <a name="ixamlnamespaceresolver"></a>IXamlNamespaceResolver

**Documentazione di riferimento**:<xref:System.Xaml.IXamlNamespaceResolver>

**Definito da:** <xref:System.Xaml> spazio dei nomi, assembly System.XamlDefined by: namespace, System.Xaml assembly  

**Relativo a:** percorso di caricamento, percorso di salvataggio.

**API del servizio:** <xref:System.Xaml.IXamlNamespaceResolver.GetNamespace%2A> per il percorso di caricamento, <xref:System.Xaml.IXamlNamespaceResolver.GetNamespacePrefixes%2A> per il percorso di salvataggio.

<xref:System.Xaml.IXamlNamespaceResolver> è un servizio che può restituire un identificatore dello spazio dei nomi XAML/URI in base al prefisso corrispondente mappato nel markup XAML di origine.

### <a name="iprovidevaluetarget"></a>IProvideValueTarget

**Documentazione di riferimento**:<xref:System.Windows.Markup.IProvideValueTarget>

**Definito da:** <xref:System.Windows.Markup> spazio dei nomi, assembly System.XamlDefined by: namespace, System.Xaml assembly  

**Relativo a:** percorso di caricamento e percorso di salvataggio.

**API**<xref:System.Windows.Markup.IProvideValueTarget.TargetObject%2A>di servizio: <xref:System.Windows.Markup.IProvideValueTarget.TargetProperty%2A>, .  

<xref:System.Windows.Markup.IProvideValueTarget> consente a convertitore di tipi o a un'estensione di markup di ottenere il contesto su cui agisce al momento del caricamento. Le implementazioni possono usare questo contesto per invalidare un utilizzo. In alcune estensioni di markup come <xref:System.Windows.DynamicResourceExtension>, ad esempio, è presente la logica WPF che controlla <xref:System.Windows.Markup.IProvideValueTarget.TargetProperty%2A> per garantire che l'estensione venga usata solo per impostare proprietà di dipendenza (o un breve elenco di altre proprietà di non dipendenza).

### <a name="ixamlnameresolver"></a>IXamlNameResolver

**Documentazione di riferimento**:<xref:System.Xaml.IXamlNameResolver>

**Definito da:** <xref:System.Xaml> spazio dei nomi, assembly System.XamlDefined by: namespace, System.Xaml assembly  

**Relativo a:** Caricare la definizione dell'oggetto `x:Name`grafico `x:Reference`del percorso, risolvendo gli oggetti identificati da tecniche specifiche di , , o del framework.

**API dei servizi:**  <xref:System.Xaml.IXamlNameResolver.Resolve%2A>. Altre API per scenari più avanzati, ad esempio, la gestione dei riferimenti in avanti.

L'implementazione dei `x:Reference` servizi XAML .NET della gestione si basa su questo servizio. Framework o strumenti specifici che supportano il framework usano questo servizio per la gestione di `x:Name` o per la gestione di proprietà (con attributo<xref:System.Windows.Markup.RuntimeNamePropertyAttribute> ) equivalenti.

### <a name="idestinationtypeprovider"></a>IDestinationTypeProvider

**Documentazione di riferimento**:<xref:System.Xaml.IDestinationTypeProvider>

**Definito da:** <xref:System.Xaml> spazio dei nomi, assembly System.XamlDefined by: namespace, System.Xaml assembly  

**Relativo a:** risoluzione del percorso di caricamento di informazioni sul tipo CLR indiretto.

**API del servizio:** <xref:System.Xaml.IDestinationTypeProvider.GetDestinationType%2A>

Per altre informazioni, vedere <xref:System.Xaml.IDestinationTypeProvider>.

## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Markup.MarkupExtension>
- <xref:System.Xaml.XamlObjectWriter>
- [Panoramica delle estensioni di markup per XAML](markup-extensions-overview.md)
- [Panoramica dei convertitori di tipi per XAML](type-converters-overview.md)
