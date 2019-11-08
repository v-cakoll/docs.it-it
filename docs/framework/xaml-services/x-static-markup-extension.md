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
ms.openlocfilehash: bf94f1d61ee3080c9d3582e55e0695b269801c80
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/07/2019
ms.locfileid: "73733365"
---
# <a name="xstatic-markup-extension"></a>Estensione del markup x:Static
Fa riferimento a qualsiasi entità di codice statica per valore definita in un modo conforme a Common Language Specification (CLS). È possibile utilizzare la proprietà statica a cui viene fatto riferimento per fornire il valore di una proprietà in XAML.  
  
## <a name="xaml-attribute-usage"></a>Uso della sintassi XAML per gli attributi  
  
```xaml  
<object property="{x:Static prefix:typeName.staticMemberName}" .../>  
```  
  
## <a name="xaml-values"></a>Valori XAML  
  
| | |  
|-|-|  
|`prefix`|Parametro facoltativo. Prefisso che fa riferimento a uno spazio dei nomi XAML non predefinito mappato. `prefix` viene visualizzato in modo esplicito nell'utilizzo perché raramente fanno riferimento a proprietà statiche che provengono da uno spazio dei nomi XAML predefinito. Vedere la sezione Osservazioni.|  
|`typeName`|Obbligatorio. Nome del tipo che definisce il membro statico desiderato.|  
|`staticMemberName`|Obbligatorio. Nome del membro del valore statico desiderato, ovvero una costante, una proprietà statica, un campo o un valore di enumerazione.|  
  
## <a name="remarks"></a>Note  

L'entità di codice a cui viene fatto riferimento deve essere una delle seguenti:  
  
- Una costante  
- Una proprietà statica  
- Un campo  
- Valore di enumerazione

Se si specifica un'altra entità di codice, ad esempio una proprietà non statica, si verificherà un errore in fase di compilazione se il codice XAML è compilato o un'eccezione di analisi della fase di caricamento XAML.  

È possibile creare riferimenti `x:Static` a proprietà o campi statici che non si trovano nello spazio dei nomi XAML predefinito per il documento XAML corrente. Questa operazione richiede tuttavia un mapping del prefisso. Gli spazi dei nomi XAML sono quasi sempre definiti sull'elemento radice del documento XAML.  

Le operazioni di ricerca per le proprietà statiche possono essere eseguite da .NET Framework servizi XAML e dai relativi reader XAML e writer XAML, quando sono in esecuzione con il contesto dello schema XAML predefinito. Questo contesto dello schema XAML può utilizzare la reflection CLR per fornire i valori statici necessari per la costruzione di oggetti grafici. Il `typeName` specificato è in realtà un nome di tipo XAML, non un nome di tipo CLR, anche se si tratta essenzialmente dello stesso nome quando si usa il contesto dello schema XAML predefinito o quando si usano tutti i Framework di implementazione XAML basati su CLR esistenti.  

Prestare attenzione quando si effettuano `x:Static` riferimenti che non sono direttamente il tipo del valore di una proprietà. Nella sequenza di elaborazione XAML, i valori forniti da un'estensione di markup non richiamano la conversione di valori aggiuntiva. Questo vale anche se il riferimento `x:Static` crea una stringa di testo e una conversione di valore per i valori di attributo basati su una stringa di testo si verifica in genere per quel membro specifico o per i valori dei membri del tipo restituito.  

La sintassi per gli attributi è quella più comunemente utilizzata con questa estensione di markup. Il token di stringa fornito dopo la stringa dell'identificatore `x:Static` viene assegnato come valore <xref:System.Windows.Markup.StaticExtension.Member%2A> della classe dell'estensione <xref:System.Windows.Markup.StaticExtension> sottostante.  

Sono tecnicamente possibili altri due utilizzi di XAML. Tuttavia, questi utilizzi sono meno comuni perché sono inutilmente dettagliati:  

1. Sintassi dell'elemento oggetto.

    ```xaml
    <x:Static Member="prefix:typeName.staticMemberName" ... />
    ```

2. Sintassi degli attributi con proprietà esplicita del membro per la stringa di inizializzazione.

    ```xaml
    <object property="{x:Static Member=prefix:typeName.staticMemberName}" ... />
    ```

Nell'.NET Framework implementazione dei servizi XAML, la gestione di questa estensione di markup viene definita dalla classe <xref:System.Windows.Markup.StaticExtension>.  

`x:Static` è un'estensione di markup. Tutte le estensioni di markup in XAML usano i caratteri `{` e `}` nella sintassi degli attributi, ovvero la convenzione con cui un processore XAML riconosce che un'estensione di markup deve fornire un valore. Per ulteriori informazioni sulle estensioni di markup, vedere [Markup Extensions for XAML Overview](markup-extensions-for-xaml-overview.md).  
  
## <a name="wpf-usage-notes"></a>Note sull'utilizzo di WPF  
 Lo spazio dei nomi XAML predefinito utilizzato per la programmazione WPF non contiene molte proprietà statiche utili e la maggior parte delle proprietà statiche utili è supportata, ad esempio convertitori di tipi, che facilitano l'utilizzo senza richiedere `{x:Static}`. Per le proprietà statiche, è necessario eseguire il mapping di un prefisso per uno spazio dei nomi XAML se si verifica una delle condizioni seguenti:  
  
- Si fa riferimento a un tipo esistente in WPF, ma che non fa parte dello spazio dei nomi XAML predefinito per WPF (`http://schemas.microsoft.com/winfx/2006/xaml/presentation`). Si tratta di uno scenario abbastanza comune per l'uso di `x:Static`. È ad esempio possibile utilizzare un riferimento `x:Static` con un mapping dello spazio dei nomi XAML allo spazio dei nomi CLR <xref:System> e l'assembly mscorlib per fare riferimento alle proprietà statiche della classe <xref:System.Environment>.  
  
- Si fa riferimento a un tipo da un assembly personalizzato.  
  
- Si fa riferimento a un tipo esistente in un assembly WPF, ma tale tipo è incluso in uno spazio dei nomi CLR di cui non è stato eseguito il mapping per far parte dello spazio dei nomi XAML predefinito WPF. Il mapping degli spazi dei nomi CLR nello spazio dei nomi XAML predefinito per WPF viene eseguito dalle definizioni nei vari assembly WPF (per altre informazioni su questo concetto, vedere [spazi dei nomi XAML e mapping dello spazio dei nomi per XAML WPF](../wpf/advanced/xaml-namespaces-and-namespace-mapping-for-wpf-xaml.md)). Gli spazi dei nomi CLR non mappati possono esistere se lo spazio dei nomi CLR è costituito principalmente da definizioni di classe che in genere non sono destinate a XAML, ad esempio <xref:System.Windows.Threading>.  
  
 Per altre informazioni su come usare i prefissi e gli spazi dei nomi XAML per WPF, vedere [spazi dei nomi XAML e mapping dello spazio dei nomi per XAML WPF](../wpf/advanced/xaml-namespaces-and-namespace-mapping-for-wpf-xaml.md).  
  
## <a name="see-also"></a>Vedere anche

- [Estensione di markup x:Type](x-type-markup-extension.md)
- [Tipi migrati da WPF a System.Xaml](types-migrated-from-wpf-to-system-xaml.md)
