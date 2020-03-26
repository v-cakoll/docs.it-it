---
title: Tipi migrati da WPF a System.Xaml
ms.date: 03/30/2017
helpviewer_keywords:
- WPF XAML [XAML Services], migration to System.Xaml
- XAML [XAML Services], System.Xaml and WPF
- System.Xaml [XAML Services], types migrated from WPF
ms.assetid: d79dabf5-a2ec-4e8d-a37a-67c4ba8a2b91
ms.openlocfilehash: 5aa2d8a39be47d9affb97c3b60e53c4722c63cce
ms.sourcegitcommit: 99b153b93bf94d0fecf7c7bcecb58ac424dfa47c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/25/2020
ms.locfileid: "80249802"
---
# <a name="types-migrated-from-wpf-to-systemxaml"></a>Tipi migrati da WPF a System.XamlTypes migrated from WPF to System.Xaml

In .NET Framework 3.5 e .NET Framework 3.0, sia Windows Presentation Foundation (WPF) che Windows Workflow Foundation includevano un'implementazione del linguaggio XAML. Molti dei tipi pubblici che fornivano l'estensibilità per l'implementazione XAML di WPF erano inclusi negli assembly WindowsBase, PresentationCore e PresentationFramework. Analogamente, i tipi pubblici che fornivano l'estensibilità per XAML di Windows Workflow Foundation esistevano nell'assembly System.Workflow.ComponentModel. In .NET Framework 4, alcuni dei tipi correlati a XAML sono stati migrati all'assembly System.Xaml. Un'implementazione comune di .NET Framework dei servizi di linguaggio XAML consente molti scenari di estensibilità XAML originariamente definiti dall'implementazione XAML di un framework specifico, ma che ora fanno parte del supporto generale del linguaggio XAML di .NET Framework 4. In questo articolo vengono elencati i tipi di cui è stata eseguita la migrazione e vengono illustrati i problemi relativi alla migrazione.

## <a name="assemblies-and-namespaces"></a>Assembly e spazi dei nomi

In .NET Framework 3.5 e .NET Framework 3.0, i tipi <xref:System.Windows.Markup> implementati da WPF per supportare XAML erano in genere nello spazio dei nomi. La maggior parte di questi tipi era inclusa nell'assembly WindowsBase.

In .NET Framework 4 è <xref:System.Xaml> disponibile un nuovo spazio dei nomi e un nuovo assembly System.Xaml. Molti dei tipi implementati in origine per XAML di WPF sono ora forniti come punti di estendibilità o servizi per qualsiasi implementazione di XAML. Nell'ambito della scelta di renderli disponibili per scenari più generali, i tipi sono stati inoltrati dall'assembly WPF originale all'assembly System.Xaml. In questo modo gli scenari di estensibilità XAML senza dover includere gli assembly di altri framework (ad esempio WPF e Windows Workflow Foundation).

Per quanto riguarda i tipi migrati, la maggior parte rimane nello spazio dei nomi <xref:System.Windows.Markup> . Questa scelta deriva parzialmente dalla necessità di evitare l'interruzione dei mapping dello spazio dei nomi CLR nelle implementazioni esistenti su base file. Di conseguenza, <xref:System.Windows.Markup> lo spazio dei nomi in .NET Framework 4 contiene una combinazione di tipi di supporto del linguaggio XAML generale (dall'assembly System.Xaml) e tipi specifici per l'implementazione XAML WPF (da WindowsBase e altri assembly WPF). Per qualsiasi tipo di cui è stata eseguita la migrazione a System.Xaml e che in precedenza era incluso in un assembly WPF è disponibile il supporto per l'inoltro dei tipi nella versione 4 dell'assembly WPF.

### <a name="workflow-xaml-support-types"></a>Tipi di supporto XAML del flusso di lavoro

Windows Workflow Foundation ha anche fornito tipi di supporto XAML e in molti casi questi avevano nomi brevi identici a quelli di un equivalente WPFWPF. Di seguito è riportato un elenco dei tipi di supporto XAML di Windows Workflow Foundation:

- <xref:System.Workflow.ComponentModel.Serialization.ContentPropertyAttribute>

- <xref:System.Workflow.ComponentModel.Serialization.RuntimeNamePropertyAttribute>

- <xref:System.Workflow.ComponentModel.Serialization.XmlnsPrefixAttribute>

Questi tipi di supporto esistono ancora negli assembly di Windows Workflow Foundation per .NET Framework 4 e possono comunque essere utilizzati per applicazioni Windows Workflow Foundation specifiche; tuttavia, non devono essere referenziati da applicazioni o framework che non utilizzano Windows Workflow Foundation.However, they should not be referenced by applications or frameworks that do not use Windows Workflow Foundation.

## <a name="markupextension"></a>MarkupExtension

In .NET Framework 3.5 e .NET Framework <xref:System.Windows.Markup.MarkupExtension> 3.0, la classe per WPF era nell'assembly WindowsBase. Una classe parallela per <xref:System.Workflow.ComponentModel.Serialization.MarkupExtension>Windows Workflow Foundation, , esisteva nell'assembly System.Workflow.ComponentModel. In .NET Framework 4 <xref:System.Windows.Markup.MarkupExtension> viene eseguita la migrazione della classe all'assembly System.Xaml. In .NET Framework <xref:System.Windows.Markup.MarkupExtension> 4.NET Framework 4, è destinato a qualsiasi scenario di estendibilità XAML che utilizza i servizi XAML di .NET, non solo per quelli che si basano su framework specifici. Quando possibile, framework specifici o codice utente nel framework deve essere basati anche sulla classe <xref:System.Windows.Markup.MarkupExtension> per l'estensione XAML.

## <a name="markupextension-supporting-service-classes"></a>MarkupExtension con supporto di classi del servizio

.NET Framework 3.5 e .NET Framework 3.0 per <xref:System.Windows.Markup.MarkupExtension> WPF fornivano diversi servizi disponibili agli implementatori e <xref:System.ComponentModel.TypeConverter> alle implementazioni per supportare l'utilizzo di tipi/proprietà in XAML. Questi servizi sono i seguenti:

- <xref:System.Windows.Markup.IProvideValueTarget>

- <xref:System.Windows.Markup.IUriContext>

- <xref:System.Windows.Markup.IXamlTypeResolver>

> [!NOTE]
> Un altro servizio da.NET Framework 3.5 che <xref:System.Windows.Markup.IReceiveMarkupExtension> è correlato alle estensioni di markup è l'interfaccia. <xref:System.Windows.Markup.IReceiveMarkupExtension>non è stata migrata ed è contrassegnata `[Obsolete]` per .NET Framework 4. Negli scenari in precedenza veniva usato <xref:System.Windows.Markup.IReceiveMarkupExtension> , ora invece è necessario usare callback con attributi <xref:System.Windows.Markup.XamlSetMarkupExtensionAttribute> . Anche<xref:System.Windows.Markup.AcceptedMarkupExtensionExpressionTypeAttribute> è contrassegnato come `[Obsolete]`.

## <a name="xaml-language-features"></a>Funzionalità del linguaggio XAML

Diversi componenti e funzionalità del linguaggio XAML per WPF erano in precedenza inclusi nell'assembly PresentationFramework. Questi venivano implementati come una sottoclasse <xref:System.Windows.Markup.MarkupExtension> per esporre gli utilizzi delle estensioni di markup nel markup XAML. In .NET Framework 4 questi elementi esistono nell'assembly System.Xaml in modo che i progetti che non includono assembly WPF possano utilizzare queste funzionalità a livello di linguaggio XAML. WPFWPF usa queste stesse implementazioni per le applicazioni .NET Framework 4. Come per gli altri casi elencati in questo argomento, i tipi di supporto continuano a esistere nello spazio dei nomi <xref:System.Windows.Markup> per evitare l'interruzione di riferimenti precedenti.

Nella tabella seguente è riportato un elenco delle classi di supporto delle funzionalità del linguaggio XAML definite in System.Xaml:

|Funzionalità del linguaggio XAML|Uso|
|---------------------------|-----------|
|<xref:System.Windows.Markup.ArrayExtension>|`<x:Array ...>`|
|<xref:System.Windows.Markup.NullExtension>|`{x:Null}`|
|<xref:System.Windows.Markup.StaticExtension>|`{x:Static ...}`|
|<xref:System.Windows.Markup.TypeExtension>|`{x:Type ...}`|

Sebbene in System.Xaml possano non essere presenti classi di supporto specifiche, la logica generale per l'elaborazione delle funzionalità del linguaggio per XAML si trova ora in System.Xaml e nei relativi reader XAML e writer XAML implementati. Ad esempio, `x:TypeArguments` è un attributo elaborato da reader XAML e writer XAML delle implementazioni di System.Xaml. Può essere indicato nel flusso del nodo XAML, viene gestito nel contesto dello schema XAML predefinito (basato su CLR), dispone di una rappresentazione del sistema di tipi di XAML e così via. Di conseguenza, la documentazione di riferimento per tutte le funzionalità a livello di linguaggio XAML è un argomento secondario per i [servizi XAML](../../../desktop-wpf/xaml-services/index.md) nella Guida del desktop per Windows Presentation [Foundation (WPF)](../../../desktop-wpf/overview/index.md).

## <a name="valueserializer-and-supporting-classes"></a>ValueSerializer e classi di supporto

La classe <xref:System.Windows.Markup.ValueSerializer> supporta la conversione di tipi in una stringa, in particolare per i casi di serializzazione di XAML in cui per la serializzazione possono essere necessarie più modalità o nodi nell'output. In .NET Framework 3.5 e .NET <xref:System.Windows.Markup.ValueSerializer> Framework 3.0, per WPF era nell'assembly WindowsBase. In .NET Framework 4,NET Framework 4, la <xref:System.Windows.Markup.ValueSerializer> classe è in System.Xaml ed è destinata a qualsiasi scenario di estendibilità XAML, non solo per quelli che si basano su WPFWPF. Viene inoltre eseguita la migrazione degli oggetti<xref:System.Windows.Markup.IValueSerializerContext> (servizio di supporto) e <xref:System.Windows.Markup.DateTimeValueSerializer> (sottoclasse specifica) a System.Xaml.

## <a name="xaml-related-attributes"></a>Attributi correlati a XAML

In XAML per WPF erano inclusi vari attributi che potevano essere applicati a tipi CLR per fornire indicazioni sul relativo comportamento XAML. Di seguito è riportato un elenco degli attributi esistenti negli assembly WPF in .NET Framework 3.5 e .NET Framework 3.0. Questi attributi vengono migrati in System.Xaml in .NET Framework 4.

- <xref:System.Windows.Markup.AmbientAttribute>

- <xref:System.Windows.Markup.ContentPropertyAttribute>

- <xref:System.Windows.Markup.ContentWrapperAttribute>

- <xref:System.Windows.Markup.DependsOnAttribute>

- <xref:System.Windows.Markup.MarkupExtensionReturnTypeAttribute>

- <xref:System.Windows.Markup.NameScopePropertyAttribute>

- <xref:System.Windows.Markup.RootNamespaceAttribute>

- <xref:System.Windows.Markup.RuntimeNamePropertyAttribute>

- <xref:System.Windows.Markup.TrimSurroundingWhitespaceAttribute>

- <xref:System.Windows.Markup.ValueSerializerAttribute>

- <xref:System.Windows.Markup.WhitespaceSignificantCollectionAttribute>

- <xref:System.Windows.Markup.XmlLangPropertyAttribute>

- <xref:System.Windows.Markup.XmlnsCompatibleWithAttribute>

- <xref:System.Windows.Markup.XmlnsDefinitionAttribute>

- <xref:System.Windows.Markup.XmlnsPrefixAttribute>

## <a name="miscellaneous-classes"></a>Classi di vario tipo

L'interfaccia <xref:System.Windows.Markup.IComponentConnector> esisteva in WindowsBase in .NET Framework 3.5 e .NET Framework 3.0, ma esiste in System.Xaml in .NET Framework 4. L'interfaccia<xref:System.Windows.Markup.IComponentConnector> è principalmente destinata al supporto per gli strumenti di supporto e compilatori di markup XAML.

L'interfaccia <xref:System.Windows.Markup.INameScope> esisteva in WindowsBase in .NET Framework 3.5 e .NET Framework 3.0, ma esiste in System.Xaml in .NET Framework 4. <xref:System.Windows.Markup.INameScope> definisce le operazioni di base per un NameScope XAML.

## <a name="xaml-related-classes-with-shared-names-that-exist-in-wpf-and-systemxaml"></a>Classi correlate a XAML con nomi condivisi incluse in WPF e System.Xaml

Le classi seguenti esistono sia negli assembly WPF che nell'assembly System.Xaml in .NET Framework 4:

`XamlReader`

`XamlWriter`

`XamlParseException`

L'implementazione WPF si trova nello spazio dei nomi <xref:System.Windows.Markup> e nell'assembly PresentationFramework. L'implementazione di System.Xaml si trova nello spazio dei nomi <xref:System.Xaml> . Se si usano tipi WPF o si deriva da tipi WPF, è in genere necessario usare le implementazioni WPF di <xref:System.Windows.Markup.XamlReader> e <xref:System.Windows.Markup.XamlWriter> anziché le implementazioni di System.Xaml. Per altre informazioni, vedere la sezione Osservazioni in <xref:System.Windows.Markup.XamlReader?displayProperty=nameWithType> e <xref:System.Windows.Markup.XamlWriter?displayProperty=nameWithType>.

Se si includono riferimenti agli assembly WPF a System.Xaml e si usano anche istruzioni `include` per gli spazi dei nomi <xref:System.Windows.Markup> e <xref:System.Xaml> , potrebbe essere necessario qualificare completamente le chiamate a queste API per risolvere i tipi senza ambiguità.
