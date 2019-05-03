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
ms.openlocfilehash: 3da2f6afc7e7ecf20c91f0badca38bc26083d3ae
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61938938"
---
# <a name="xstatic-markup-extension"></a>Estensione del markup x:Static
Fa riferimento a qualsiasi entità di codice statico in base al valore definito in un [!INCLUDE[TLA#tla_cls](../../../includes/tlasharptla-cls-md.md)]: modalità conforme. La proprietà statica a cui viene fatto riferimento è utilizzabile per fornire il valore di una proprietà in XAML.  
  
## <a name="xaml-attribute-usage"></a>Uso della sintassi XAML per gli attributi  
  
```xaml  
<object property="{x:Static prefix:typeName.staticMemberName}" .../>  
```  
  
## <a name="xaml-values"></a>Valori XAML  
  
| | |  
|-|-|  
|`prefix`|Facoltativo. Un prefisso che fa riferimento a uno spazio dei nomi XAML con mapping non predefinito. `prefix` viene visualizzato in modo esplicito nell'utilizzo perché raramente fanno riferimento a proprietà statiche che provengono da uno spazio dei nomi XAML predefinito. Vedere la sezione Osservazioni.|  
|`typeName`|Obbligatorio. Il nome del tipo che definisce il membro statico desiderato.|  
|`staticMemberName`|Obbligatorio. Il nome del membro valore statico desiderato (una costante, una proprietà statica, un campo o un valore di enumerazione).|  
  
## <a name="remarks"></a>Note  

L'entità di codice a cui viene fatto riferimento deve essere uno dei seguenti:  
  
- Una costante  
- Una proprietà statica  
- Un campo  
- Un valore di enumerazione

Specifica di qualsiasi altra entità di codice, ad esempio una proprietà non statica, provoca un errore in fase di compilazione se il XAML è compilazione dal markup, o un'eccezione di analisi in fase di caricamento XAML.  

È possibile rendere `x:Static` riferimenti a campi statici o proprietà che non si trovano nello spazio dei nomi XAML predefinito per il documento XAML corrente; tuttavia, questo richiede un mapping del prefisso. Gli spazi dei nomi XAML sono quasi sempre definiti per l'elemento radice del documento XAML.  

Le operazioni di ricerca per le proprietà statiche possono essere eseguite dai servizi XAML di .NET Framework e relativi reader XAML e writer XAML, quando vengono eseguite con il contesto dello schema XAML predefinito. In questo contesto dello schema XAML è possibile usare la reflection CLR per fornire i valori statici necessari per la costruzione dell'oggetto grafico. Il `typeName` specificare è effettivamente un nome di tipo XAML, non un nome di tipo CLR, anche se si tratta essenzialmente lo stesso nome quando si usa il contesto dello schema XAML predefinito o quando si usa tutti i framework basati su CLR che implementa XAML esistenti.  

Prestare attenzione quando si apportano `x:Static` riferimenti che non sono direttamente il tipo di valore della proprietà. In XAML la sequenza di valori fornito da un'estensione di markup di elaborazione non richiamare conversione del valore aggiuntive. Questo vale anche se il `x:Static` riferimento crea una stringa di testo e si verifica una conversione del valore per i valori di attributo basati su stringa di testo in genere per il membro specifico o per i valori di qualsiasi membro del tipo restituito.  

La sintassi per gli attributi è quella più comunemente utilizzata con questa estensione di markup. Il token di stringa fornito dopo la stringa dell'identificatore `x:Static` viene assegnato come valore <xref:System.Windows.Markup.StaticExtension.Member%2A> della classe dell'estensione <xref:System.Windows.Markup.StaticExtension> sottostante.  

Esistono due altri utilizzi XAML che fanno tecnicamente possibili. Tuttavia, questi utilizzi sono meno comuni perché sono inutilmente dettagliati:  

1. Sintassi degli elementi oggetto.

    ```xaml
    <x:Static Member="prefix:typeName.staticMemberName" ... />
    ```

2. Sintassi degli attributi con le proprietà membro esplicito per la stringa di inizializzazione.

    ```xaml
    <object property="{x:Static Member=prefix:typeName.staticMemberName}" ... />
    ```

Nell'implementazione di servizi XAML di .NET Framework, la gestione di questa estensione di markup viene definita per il <xref:System.Windows.Markup.StaticExtension> classe.  

`x:Static` è un'estensione di markup. Tutte le estensioni di markup in uso XAML il `{` e `}` caratteri nella sintassi degli attributi, vale a dire la convenzione per cui un processore XAML riconosce che un'estensione di markup deve fornire un valore. Per ulteriori informazioni sulle estensioni di markup, vedere [Markup Extensions for XAML Overview](markup-extensions-for-xaml-overview.md).  
  
## <a name="wpf-usage-notes"></a>Note sull'utilizzo WPF  
 Spazio dei nomi XAML predefinito utilizzato per la programmazione WPF non contiene molte proprietà statica utili e la maggior parte delle proprietà statiche utile dispongono di supporto, ad esempio i convertitori di tipi che semplificano l'uso senza richiedere `{x:Static}` . Per le proprietà statiche, è necessario eseguire il mapping di un prefisso per uno spazio dei nomi XAML se viene soddisfatta una delle operazioni seguenti:  
  
- Si fa riferimento a un tipo che esiste in WPF, ma non fa parte dello spazio dei nomi XAML predefinito per WPF ([!INCLUDE[TLA#tla_wpfxmlnsv1](../../../includes/tlasharptla-wpfxmlnsv1-md.md)]). Si tratta di uno scenario piuttosto comune per l'uso di `x:Static`. Ad esempio, è possibile utilizzare un `x:Static` riferimento con un mapping dello spazio dei nomi XAML per il <xref:System> assembly mscorlib e dello spazio dei nomi CLR per fare riferimento a proprietà statiche del <xref:System.Environment> classe.  
  
- Si fa riferimento a un tipo da un assembly personalizzato.  
  
- Si fa riferimento a un tipo esistente in un assembly WPF, ma questo tipo è all'interno di uno spazio dei nomi CLR che non è stato eseguito il mapping come parte dello spazio dei nomi XAML WPF predefinito. Viene eseguito il mapping degli spazi dei nomi CLR nello spazio dei nomi XAML predefinito per WPF dalle definizioni in vari assembly WPF (per ulteriori informazioni su questo concetto, vedere [spazi dei nomi XAML e Mapping Namespace per XAML WPF](../wpf/advanced/xaml-namespaces-and-namespace-mapping-for-wpf-xaml.md)). Possono esistere spazi dei nomi CLR non mappati se tale spazio dei nomi CLR è composto principalmente le definizioni delle classi che non sono in genere destinati al XAML, ad esempio <xref:System.Windows.Threading>.  
  
 Per altre informazioni su come usare i prefissi e spazi dei nomi XAML per WPF, vedere [spazi dei nomi XAML e Mapping di Namespace per XAML WPF](../wpf/advanced/xaml-namespaces-and-namespace-mapping-for-wpf-xaml.md).  
  
## <a name="see-also"></a>Vedere anche

- [Estensione di markup x:Type](x-type-markup-extension.md)
- [Tipi migrati da WPF a System.Xaml](types-migrated-from-wpf-to-system-xaml.md)
