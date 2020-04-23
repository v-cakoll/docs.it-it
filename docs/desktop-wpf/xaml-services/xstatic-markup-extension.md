---
title: Estensione del markup x:Static
ms.date: 03/30/2017
f1_keywords:
- StaticExtension
- xStatic
- x:Static
helpviewer_keywords:
- x:Static markup extension [XAML Services]
- Static markup extension in XAML [XAML Services]
- XAML [XAML Services], x:Static markup extension
ms.assetid: 056aee79-7cdd-434f-8174-dfc856cad343
ms.openlocfilehash: fb9ee6807135f17fd9e0c799533bba28b369ebe2
ms.sourcegitcommit: 99b153b93bf94d0fecf7c7bcecb58ac424dfa47c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/25/2020
ms.locfileid: "82072025"
---
# <a name="xstatic-markup-extension"></a>Estensione del markup x:Static

Fa riferimento a qualsiasi entità di codice statico per valore definita in modo conforme a CLS (Common Language Specification). La proprietà statica a cui si fa riferimento può essere utilizzata per fornire il valore di una proprietà in XAML.

## <a name="xaml-attribute-usage"></a>Uso della sintassi XAML per gli attributi

```xaml
<object property="{x:Static prefix:typeName.staticMemberName}" .../>
```

## <a name="xaml-values"></a>Valori XAML

| | |
|-|-|
|`prefix`|Facoltativa. Prefisso che fa riferimento a uno spazio dei nomi XAML mappato e non predefinito. `prefix`viene mostrato in modo esplicito nell'utilizzo perché raramente si fa riferimento a proprietà statiche che provengono da uno spazio dei nomi XAML predefinito. Vedere la sezione Osservazioni.|
|`typeName`|Obbligatorio. Nome del tipo che definisce il membro statico desiderato.|
|`staticMemberName`|Obbligatorio. Nome del membro del valore statico desiderato (una costante, una proprietà statica, un campo o un valore di enumerazione).|

## <a name="remarks"></a>Osservazioni

L'entità di codice a cui viene fatto riferimento deve essere una delle seguenti:

- Una costante
- Una proprietà statica
- Un campo
- Valore di enumerazioneAn enumeration value

Se si specifica qualsiasi altra entità di codice, ad esempio una proprietà non statica, si verifica un errore in fase di compilazione se il codice XAML viene compilato markup o un'eccezione di analisi in fase di caricamento XAML.

È possibile `x:Static` creare riferimenti a campi statici o proprietà che non si trovano nello spazio dei nomi XAML predefinito per il documento XAML corrente. tuttavia, ciò richiede un mapping di prefisso. Gli spazi dei nomi XAML sono quasi sempre definiti nell'elemento radice del documento XAML.

Le operazioni di ricerca per le proprietà statiche possono essere eseguite dai servizi XAML .NET e dai relativi reader XAML e writer XAML, quando vengono eseguite con il contesto dello schema XAML predefinito. Questo contesto dello schema XAML può usare la reflection CLR per fornire i valori statici necessari per la costruzione dell'oggetto grafico. L'impostazione `typeName` specificata è in realtà un nome di tipo XAML, non un nome di tipo CLR, anche se questi sono essenzialmente lo stesso nome quando si usa il contesto dello schema XAML predefinito o quando si utilizzano tutti i framework di implementazione XAML basati su CLR esistenti.

Prestare attenzione `x:Static` quando si effettuano riferimenti che non sono direttamente il tipo di valore di una proprietà. Nella sequenza di elaborazione XAML, i valori forniti da un'estensione di markup non richiamano la conversione di valori aggiuntivi. Questo vale anche `x:Static` se il riferimento crea una stringa di testo e una conversione di valore per i valori di attributo in base alla stringa di testo si verifica in genere per quel membro specifico o per qualsiasi valore del membro del tipo restituito.

La sintassi per gli attributi è quella più comunemente utilizzata con questa estensione di markup. Il token di stringa fornito dopo la stringa dell'identificatore `x:Static` viene assegnato come valore <xref:System.Windows.Markup.StaticExtension.Member%2A> della classe dell'estensione <xref:System.Windows.Markup.StaticExtension> sottostante.

Esistono altri due utilizzi XAML tecnicamente possibili. Tuttavia, questi utilizzi sono meno comuni perché sono inutilmente dettagliati:However, these usages are less common because they are unnecessarily verbose:

01. Sintassi degli elementi oggetto.

    ```xaml
    <x:Static Member="prefix:typeName.staticMemberName" ... />
    ```

02. Sintassi dell'attributo con proprietà Member esplicita per la stringa di inizializzazione.

    ```xaml
    <object property="{x:Static Member=prefix:typeName.staticMemberName}" ... />
    ```

Nell'implementazione dei servizi XAML .NET, la <xref:System.Windows.Markup.StaticExtension> gestione di questa estensione di markup è definita dalla classe .

`x:Static` è un'estensione di markup. Tutte le estensioni `{` di `}` markup in XAML usano i caratteri e nella sintassi degli attributi, ovvero la convenzione in base alla quale un processore XAML riconosce che un'estensione di markup deve fornire un valore. Per ulteriori informazioni sulle estensioni di markup, vedere [Markup Extensions for XAML Overview](markup-extensions-overview.md).

## <a name="wpf-usage-notes"></a>Note sull'utilizzo di WPF

Lo spazio dei nomi XAML predefinito utilizzato per la programmazione WPFWPF non contiene molte proprietà statiche utili `{x:Static}` e la maggior parte delle proprietà statiche utili dispone di supporto, ad esempio convertitori di tipi che facilitano l'utilizzo senza richiedere . Per le proprietà statiche, è necessario eseguire il mapping di un prefisso per uno spazio dei nomi XAML se si verifica una delle condizioni seguenti:For static properties, you must map a prefix for a XAML namespace if one of the following is true:

- Si fa riferimento a un tipo esistente in WPFWPF ma non`http://schemas.microsoft.com/winfx/2006/xaml/presentation`fa parte dello spazio dei nomi XAML predefinito per WPF ( ). Si tratta di uno `x:Static`scenario abbastanza comune per l'utilizzo di . Ad esempio, è `x:Static` possibile utilizzare un riferimento <xref:System> con un mapping dello spazio dei nomi XAML <xref:System.Environment> allo spazio dei nomi CLR e all'assembly mscorlib per fare riferimento alle proprietà statiche della classe.

- Si fa riferimento a un tipo da un assembly personalizzato.

- Si fa riferimento a un tipo esistente in un assembly WPF, ma tale tipo si trova all'interno di uno spazio dei nomi CLR di cui non è stato eseguito il mapping per far parte dello spazio dei nomi XAML predefinito WPF. Il mapping degli spazi dei nomi CLR nello spazio dei nomi XAML predefinito per WPF viene eseguito mediante definizioni nei vari assembly WPF (per ulteriori informazioni su questo concetto, vedere [Spazi dei nomi XAML e Mapping degli spazi dei nomi per XAML WPF](../../framework/wpf/advanced/xaml-namespaces-and-namespace-mapping-for-wpf-xaml.md)). Gli spazi dei nomi CLR non mappati possono esistere se tale spazio dei nomi <xref:System.Windows.Threading>CLR è composto principalmente da definizioni di classe che in genere non sono destinate a XAML, ad esempio .

Per altre informazioni su come usare prefissi e spazi dei nomi XAML per WPF, vedere [Spazi dei nomi XAML e Mapping degli spazi dei nomi per XAML WPF.](../../framework/wpf/advanced/xaml-namespaces-and-namespace-mapping-for-wpf-xaml.md)

## <a name="see-also"></a>Vedere anche

- [Estensione del markup x:Type](xtype-markup-extension.md)
- [Tipi migrati da WPF a System.Xaml](../../framework/wpf/advanced/types-migrated-from-wpf-to-system.md)
