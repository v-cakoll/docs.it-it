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
ms.openlocfilehash: 980bf6a1bdb19afd5c8d3c798d31037ab8cd7086
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33565577"
---
# <a name="xstatic-markup-extension"></a>Estensione del markup x:Static
Fa riferimento a qualsiasi entità del codice statico in base al valore definito in un [!INCLUDE[TLA#tla_cls](../../../includes/tlasharptla-cls-md.md)]: modalità conforme. Per fornire il valore di una proprietà in XAML, è possibile utilizzare la proprietà statica a cui fa riferimento.  
  
## <a name="xaml-attribute-usage"></a>Uso della sintassi XAML per gli attributi  
  
```xaml  
<object property="{x:Static prefix:typeName.staticMemberName}" .../>  
```  
  
## <a name="xaml-values"></a>Valori XAML  
  
|||  
|-|-|  
|`prefix`|Facoltativo. Un prefisso che fa riferimento a uno spazio dei nomi XAML con mapping non predefinito. `prefix` viene visualizzato in modo esplicito nell'utilizzo perché è raramente fare riferimento a proprietà statiche che provengono da uno spazio dei nomi XAML predefinito. Vedere la sezione Osservazioni.|  
|`typeName`|Obbligatorio. Il nome del tipo che definisce il membro statico desiderato.|  
|`staticMemberName`|Obbligatorio. Il nome del membro valore statico desiderato (una costante, una proprietà statica, un campo o un valore di enumerazione).|  
  
## <a name="remarks"></a>Note  
 L'entità di codice a cui fa riferimento deve essere uno dei valori seguenti:  
  
-   Una costante  
  
-   Una proprietà statica  
  
-   Un campo  
  
-   Un valore di enumerazione  
  
 Qualsiasi altra entità di codice, ad esempio una proprietà non statica, restituiranno un errore in fase di compilazione se il codice XAML viene compilata o un'eccezione di analisi in fase di caricamento XAML.  
  
 È possibile apportare `x:Static` riferimenti a campi statici o proprietà che non si trovano nello spazio dei nomi XAML predefinito per il documento XAML corrente; tuttavia, ciò richiede un mapping del prefisso. Spazi dei nomi XAML sono quasi sempre definiti per l'elemento radice del documento XAML.  
  
 Le operazioni di ricerca per le proprietà statiche possono essere eseguite dai servizi XAML di .NET Framework e i relativi reader XAML e writer XAML, quando sono in esecuzione con il contesto dello schema XAML predefinito. In questo contesto dello schema XAML è possibile utilizzare la reflection CLR per fornire i valori statici necessari per la costruzione dell'oggetto grafico. Il `typeName` specificare è effettivamente un nome di tipo XAML, non un nome di tipo CLR, anche se si tratta essenzialmente lo stesso nome quando si utilizza il contesto dello schema XAML predefinito o quando si utilizza tutti i framework basato su CLR che implementa XAML esistenti.  
  
 Prestare attenzione quando si apportano `x:Static` i riferimenti che non sono direttamente il tipo del valore di una proprietà. Nel codice XAML l'elaborazione di sequenza di valori fornito da un'estensione di markup non richiamare conversione del valore aggiuntive. Questo vale anche se il `x:Static` riferimento crea una stringa di testo e si verifica una conversione da un valore per i valori di attributo basato su stringa di testo, in genere per il membro specifico o per i valori dei membri del tipo restituito.  
  
 La sintassi per gli attributi è quella più comunemente utilizzata con questa estensione di markup. Il token di stringa fornito dopo la stringa dell'identificatore `x:Static` viene assegnato come valore <xref:System.Windows.Markup.StaticExtension.Member%2A> della classe dell'estensione <xref:System.Windows.Markup.StaticExtension> sottostante.  
  
 Esistono due altri utilizzi XAML che sono tecnicamente possibili. Tuttavia, questi utilizzi sono meno comuni perché sono inutilmente dettagliati:  
  
 **Sintassi dell'elemento oggetto:** `<x:Static Member="` `prefix` `:` `typeName` `.` `staticMemberName` `" .../>`  
  
 **Sintassi degli attributi con le proprietà membro esplicito per la stringa di inizializzazione:** `<` `object` `` `property` `="{x:Static Member=` `prefix` `:` `typeName` `.` `staticMemberName` `}" .../>`  
  
 Nell'implementazione dei servizi XAML di .NET Framework, la gestione di questa estensione di markup viene definita per la <xref:System.Windows.Markup.StaticExtension> classe.  
  
 `x:Static` è un'estensione di markup. Tutte le estensioni di markup in XAML utilizzano il `{` e `}` caratteri nella relativa sintassi degli attributi, che corrisponde alla convenzione mediante il quale il processore XAML riconosce che un'estensione di markup deve fornire un valore. Per ulteriori informazioni sulle estensioni di markup, vedere [Markup Extensions for XAML Overview](../../../docs/framework/xaml-services/markup-extensions-for-xaml-overview.md).  
  
## <a name="wpf-usage-notes"></a>Note sull'utilizzo WPF  
 Spazio dei nomi XAML predefinito utilizzato per la programmazione WPF non contiene molte proprietà statiche utili e la maggior parte delle proprietà statiche utili dispongono di supporto, ad esempio i convertitori di tipi che semplificano l'utilizzo senza `{x:Static}` . Per le proprietà statiche, è necessario mappare un prefisso per uno spazio dei nomi XAML, se viene soddisfatta una delle operazioni seguenti:  
  
-   Si fa riferimento a un tipo che esiste in WPF, ma non fa parte di spazio dei nomi XAML predefinito per WPF ([!INCLUDE[TLA#tla_wpfxmlnsv1](../../../includes/tlasharptla-wpfxmlnsv1-md.md)]). Si tratta di uno scenario abbastanza comune per l'utilizzo di `x:Static`. Ad esempio, è possibile utilizzare un `x:Static` riferimento con un mapping dello spazio dei nomi XAML per la <xref:System> CLR dello spazio dei nomi e assembly mscorlib per fare riferimento a proprietà statiche della <xref:System.Environment> classe.  
  
-   Si fa riferimento a un tipo da un assembly personalizzato.  
  
-   Si fa riferimento a un tipo esistente in un assembly WPF, ma questo tipo è all'interno di uno spazio dei nomi CLR che non è stato mappato a far parte dello spazio dei nomi XAML di WPF predefinito. Viene eseguito il mapping degli spazi dei nomi CLR nello spazio dei nomi XAML predefinito per WPF dalle definizioni nei vari assembly WPF (per ulteriori informazioni su questo concetto, vedere [spazi dei nomi XAML e Mapping Namespace per XAML WPF](../../../docs/framework/wpf/advanced/xaml-namespaces-and-namespace-mapping-for-wpf-xaml.md)). Gli spazi dei nomi CLR non mappati possono essere presenti se tale spazio dei nomi CLR è composto principalmente le definizioni di classe che non sono in genere progettate per XAML, ad esempio <xref:System.Windows.Threading>.  
  
 Per ulteriori informazioni su come utilizzare i prefissi e spazi dei nomi XAML per WPF, vedere [spazi dei nomi XAML e Namespace Mapping per XAML di WPF](../../../docs/framework/wpf/advanced/xaml-namespaces-and-namespace-mapping-for-wpf-xaml.md).  
  
## <a name="see-also"></a>Vedere anche  
 [Estensione di markup x:Type](../../../docs/framework/xaml-services/x-type-markup-extension.md)  
 [Tipi migrati da WPF a System.Xaml](../../../docs/framework/xaml-services/types-migrated-from-wpf-to-system-xaml.md)
