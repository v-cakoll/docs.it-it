---
title: Direttiva x:Class
ms.date: 03/30/2017
f1_keywords:
- x:Class
- xClass
- Class
helpviewer_keywords:
- Class attribute in XAML [XAML Services]
- XAML [XAML Services], x:Class attribute
- x:Class attribute [XAML Services]
ms.assetid: bc4a3d8e-76e2-423e-a5d1-159a023e82ec
ms.openlocfilehash: f589fa70c2ee1c56544fa0f0152990478aa3761f
ms.sourcegitcommit: 99b153b93bf94d0fecf7c7bcecb58ac424dfa47c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/25/2020
ms.locfileid: "82072039"
---
# <a name="xclass-directive"></a>Direttiva x:Class
Configura la compilazione del markup XAML per unire classi parziali tra markup e code-behind. La classe parziale del codice viene definita in un file di codice separato in un linguaggio CLS (Common Language Specification), mentre la classe parziale del markup viene in genere creata dalla generazione del codice durante la compilazione XAML.

## <a name="xaml-attribute-usage"></a>Uso della sintassi XAML per gli attributi

```xaml
<object x:Class="namespace.classname"...>
  ...
</object>
```

## <a name="xaml-values"></a>Valori XAML

|||
|-|-|
|`namespace`|Facoltativa. Specifica uno spazio dei nomi CLR `classname`che contiene la classe parziale identificata da . Se `namespace` viene specificato, un punto `namespace` (.) separa e `classname`. Vedere la sezione Osservazioni.|
|`classname`|Obbligatorio. Specifica il nome CLR della classe parziale che connette il codice XAML caricato e il code-behind per tale codice XAML.|

## <a name="dependencies"></a>Dependencies

`x:Class`può essere specificato solo nell'elemento radice di una produzione XAML. `x:Class`non è valido in qualsiasi oggetto che dispone di un elemento padre nella produzione XAML. Per ulteriori informazioni, vedere [ \[Sezione MS-XAML\] 4.3.1.6.](https://docs.microsoft.com/previous-versions/msp-n-p/ff650760(v=pandp.10))

## <a name="remarks"></a>Osservazioni

Il `namespace` valore può contenere punti aggiuntivi per organizzare gli spazi dei nomi correlati in gerarchie di nomi, che è una tecnica comune nella programmazione .NET. Solo l'ultimo punto `x:Class` in una stringa `namespace` `classname.` di valori viene `x:Class` interpretato per separare e la classe utilizzata come non può essere una classe annidata. Le classi annidate non sono consentite `x:Class` perché la determinazione del significato dei punti per le stringhe è ambigua se sono consentite classi annidate.

Nei modelli di `x:Class`programmazione esistenti che utilizzano , `x:Class` è facoltativo nel senso che è del tutto valido avere una pagina XAML senza code-behind. Tuttavia, tale funzionalità interagisce con le azioni di compilazione implementate dai framework che usano XAML. `x:Class`La funzionalità è influenzata anche dai ruoli che le varie classificazioni del contenuto specificato da XAML hanno in un modello di applicazione e nelle azioni di compilazione corrispondenti. Se il codice XAML dichiara i valori degli attributi di gestione degli eventi o crea un'istanza di elementi personalizzati in cui le classi di definizione si trovano nella classe code-behind, è necessario fornire il `x:Class` riferimento alla direttiva (o [x:Subclass](xsubclass-directive.md)) alla classe appropriata per il code-behind.

Il valore `x:Class` della direttiva deve essere una stringa che specifica il nome completo di <xref:System.Type.FullName%2A?displayProperty=nameWithType>una classe ma senza informazioni sull'assembly (equivalente a ). Per le applicazioni semplici, è possibile omettere le informazioni sullo spazio dei nomi CLR se il code-behind è anche strutturato in questo modo (la definizione del codice inizia a livello di classe).

Il file code-behind per una definizione di pagina o applicazione deve trovarsi all'interno di un file di codice incluso come parte del progetto che produce un'applicazione compilata e prevede la compilazione del markup. È necessario seguire le regole dei nomi per le classi CLR. Per ulteriori informazioni, vedere Linee guida per la [progettazione di Framework](../../../api/index.md). Per impostazione predefinita, la `public`classe code-behind deve essere ; Tuttavia, è possibile definirlo a un livello di accesso diverso utilizzando la [direttiva x:ClassModifier](xclassmodifier-directive.md).

Questa interpretazione `x:Class` dell'attributo si applica solo a un'implementazione XAML basata su CLR, in particolare ai servizi XAML .NET. Altre implementazioni XAML che non sono basate su CLR e che non utilizzano i servizi XAML .NET potrebbero usare una formula di risoluzione diversa per la connessione del markup XAML e il backup del codice in fase di esecuzione. Per ulteriori informazioni sulle interpretazioni più generali di `x:Class`, vedere [ \[MS-XAML\]](https://docs.microsoft.com/previous-versions/msp-n-p/ff650760(v=pandp.10)).

A un certo livello di `x:Class` architettura, il significato di è undefined nei servizi XAML di .NET. Ciò è dovuto al fatto che i servizi XAML .NET non specificano il modello di programmazione mediante il quale sono connessi il markup XAML e il codice di backup. Ulteriori utilizzi `x:Class` della direttiva potrebbero essere implementati da framework specifici che utilizzano modelli di programmazione o modelli di applicazione per definire come connettere il markup XAML e code-behind basati su CLR. Ogni framework può avere le proprie azioni di compilazione che consentono alcuni dei comportamenti o componenti specifici che devono essere inclusi nell'ambiente di compilazione. All'interno di un framework, le azioni di compilazione possono anche variare a seconda del linguaggio CLR specifico utilizzato per il code-behind.

## <a name="xclass-in-the-wpf-programming-model"></a>x:Classe nel modello di programmazione WPFX:Class in the WPF Programming Model

Nelle applicazioni WPFWPF e `x:Class` nel modello di applicazione WPFWPF, può essere dichiarato come attributo per qualsiasi elemento che è `Page` la radice di <xref:System.Windows.Application> un file XAML e viene compilato (dove il codice XAML è incluso in un progetto di applicazione WPF CON azione di compilazione) o per la radice nella definizione dell'applicazione di un'applicazione WPF compilata. La `x:Class` dichiarazione in un elemento diverso da una radice della pagina o dell'applicazione o in un file XAML WPF non compilato genera un errore in fase di compilazione nel compilatore XAML WPF di .NET Framework 3.0 e .NET Framework 3.5. Per informazioni su altri `x:Class` aspetti della gestione in WPFWPF, vedere [Code-Behind e XAML in WPF.](../../framework/wpf/advanced/code-behind-and-xaml-in-wpf.md)

## <a name="xclass-for-windows-workflow-foundation"></a>x:Classe per Windows Workflow Foundation
Per Windows Workflow `x:Class` Foundation, denomina la classe di un'attività personalizzata composta interamente in XAML o denomina la classe parziale della pagina XAML per un ActivityDesigner con code-behind.

## <a name="silverlight-usage-notes"></a>Note sull'utilizzo di Silverlight

`x:Class`per Silverlight è documentato separatamente. Per altre informazioni, vedere [Spazio dei nomi XAML (x:) Funzionalità del linguaggio (Silverlight)](https://docs.microsoft.com/previous-versions/windows/silverlight/dotnet-windows-silverlight/cc188995(v=vs.95)).

## <a name="see-also"></a>Vedere anche

- [Direttiva x:Subclass](xsubclass-directive.md)
- [Classi XAML e personalizzate per WPF](../../framework/wpf/advanced/xaml-and-custom-classes-for-wpf.md)
- [Direttiva x:ClassModifier](xclassmodifier-directive.md)
- [Tipi migrati da WPF a System.Xaml](../../framework/wpf/advanced/types-migrated-from-wpf-to-system.md)
