---
title: XAML Namespaces and Namespace Mapping
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- custom classes [WPF], mapping namespaces to
- XAML [WPF], namespaces
- namespace mapping [WPF]
- assemblies [WPF], mapping namespaces to
- mapping namespaces [WPF]
- XAML [WPF], namespace mapping
- classes [WPF], mapping namespaces to
- namespaces [WPF]
ms.assetid: 5c0854e3-7470-435d-9fe2-93eec9d3634e
ms.openlocfilehash: 9b01643e8f8d77073595253580ebea60fabfd23b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186241"
---
# <a name="xaml-namespaces-and-namespace-mapping-for-wpf-xaml"></a>Spazi dei nomi XAML e mapping dello spazio dei nomi per XAML WPF
Questo argomento approfondisce la presenza e lo scopo dei due mapping dello spazio dei nomi XAML nel tag radice di ogni file XAML WPF. L'argomento descrive anche come produrre mapping simili per l'uso di elementi definiti nel codice e/o all'interno di assembly separati.  

## <a name="what-is-a-xaml-namespace"></a>Definizione di spazio dei nomi XAML  
 Uno spazio dei nomi XAML è in realtà un'estensione del concetto di spazio dei nomi XML. Le tecniche di specifica di uno spazio dei nomi XAML si basano sulla sintassi dello spazio dei nomi XML, sulla convenzione dell'uso di URI come identificatori dello spazio dei nomi, sull'uso di prefissi per fare riferimento a più spazi dei nomi dalla stessa origine del markup e così via. Il concetto principale aggiunto alla definizione XAML rispetto allo spazio dei nomi XML consiste nel fatto che uno spazio dei nomi XAML implica un ambito di univocità per gli utilizzi del markup e influenza il modo in cui le entità del markup possono essere supportate da spazi dei nomi e da assembly di riferimento CLR specifici. Questa seconda considerazione è influenzata anche dal concetto di contesto dello schema XAML. Tuttavia, per quanto riguarda il funzionamento di WPF rispetto agli spazi dei nomi XAML, è possibile considerare gli spazi dei nomi XAML in termini di mapping diretto da parte del markup XAML di uno spazio dei nomi XAML predefinito, dello spazio dei nomi del linguaggio XAML e di qualsiasi altro spazio dei nomi XAML agli spazi dei nomi e agli assembly di riferimento CLR di supporto specifici.  
  
<a name="The_WPF_and_XAML_Namespace_Declarations"></a>
## <a name="the-wpf-and-xaml-namespace-declarations"></a>Dichiarazioni dello spazio dei nomi XAML e WPF  
 All'interno delle dichiarazioni dello spazio dei nomi nel tag radice di molti file XAML sono in genere presenti due dichiarazioni di spazi dei nomi XML. La prima dichiarazione esegue il mapping dello spazio dei nomi del client WPF complessivo o del framework XAML come predefinito:  
  
 `xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"`  
  
 La seconda dichiarazione esegue il mapping di uno spazio dei nomi XAML separato, in genere al prefisso `x:`.  
  
 `xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"`  
  
 La relazione tra queste dichiarazioni consiste nel fatto che il mapping del prefisso `x:` supporta gli intrinseci che fanno parte della definizione del linguaggio XAML e [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] è un'implementazione che usa XAML come linguaggio e ne definisce un vocabolario degli oggetti per XAML. Poiché l'utilizzo del vocabolario WPF è in genere molto più frequente dell'utilizzo degli intrinseci XAML, il vocabolario WPF viene mappato come predefinito.  
  
 La `x:` convenzione del prefisso per il mapping del supporto delle funzioni intrinseche del linguaggio XAML è seguita dai modelli di progetto, dal codice di esempio e dalla documentazione delle funzionalità del linguaggio all'interno di questo SDK. Lo spazio dei nomi XAML definisce molte funzionalità di uso comune, necessarie anche per le applicazioni WPF di base. Ad esempio, per unire code-behind a un file XAML tramite una classe parziale, è necessario denominare la classe come attributo `x:Class` nell'elemento radice del file XAML corrispondente. In alternativa, per qualsiasi elemento definito in una pagina XAML a cui si desidera accedere come risorsa con chiave è necessario che l'attributo `x:Key` sia impostato sull'elemento in questione. Per altre informazioni su questi e altri aspetti di XAML, vedere [Cenni preliminari su XAML (WPF)](../../../desktop-wpf/fundamentals/xaml.md) o [Descrizione dettagliata della sintassi XAML](xaml-syntax-in-detail.md).  
  
<a name="Mapping_To_Custom_Classes_and_Assemblies"></a>
## <a name="mapping-to-custom-classes-and-assemblies"></a>Mapping a classi e assembly personalizzati  
 È possibile eseguire il mapping di spazi dei nomi XML ad assembly tramite una serie di token all'interno di una dichiarazione di prefisso `xmlns` eseguendo una procedura analoga a quella del mapping degli spazi dei nomi WPF e XAML degli intrinseci XAML standard ai prefissi.  
  
 La sintassi accetta i token denominati e i valori riportati di seguito:  
  
 `clr-namespace:` lo spazio dei nomi CLR dichiarato nell'assembly che contiene i tipi pubblici da esporre come elementi.  
  
 `assembly=`Assembly che contiene parte o tutto lo spazio dei nomi CLR a cui si fa riferimento. Il valore è dato in genere dal nome dell'assembly, non dal percorso, e non include l'estensione (ad esempio, dll o exe). Il percorso dell'assembly deve essere stabilito come riferimento al progetto nel file di progetto che contiene il codice XAML di cui si sta tentando di eseguire il mapping. Per incorporare il controllo delle versioni `assembly` e la firma con <xref:System.Reflection.AssemblyName>nome sicuro, il valore può essere una stringa definita da , anziché il nome di stringa semplice.  
  
 Si noti che il carattere che separa il token `clr-namespace` dal valore è il segno di due punti (:), mentre il carattere che separa il token `assembly` dal valore è un segno di uguale (=). Il carattere da usare tra i due token è il segno di punto e virgola. Inoltre, non includere spazi vuoti in qualsiasi punto della dichiarazione.  
  
### <a name="a-basic-custom-mapping-example"></a>Esempio di base di mapping personalizzato  
 Il codice seguente definisce una classe personalizzata di esempio:  
  
```csharp  
namespace SDKSample {  
    public class ExampleClass : ContentControl {  
        public ExampleClass() {  
        ...  
        }  
    }  
}  
```  
  
```vb  
Namespace SDKSample  
    Public Class ExampleClass  
        Inherits ContentControl  
         ...  
        Public Sub New()  
        End Sub  
    End Class  
End Namespace  
```  
  
 Questa classe personalizzata viene quindi compilata in una libreria che, in base alle impostazioni del progetto (non visualizzate), è denominata `SDKSampleLibrary`.  
  
 Per fare riferimento a tale classe personalizzata, è anche necessario includerla come riferimento per il progetto corrente, operazione in genere effettuata tramite l'interfaccia utente di Esplora soluzioni in Visual Studio.  
  
 Ora che si dispone di una libreria contenente una classe e di un riferimento a questa nelle impostazioni del progetto, è possibile aggiungere il mapping del prefisso seguente come parte dell'elemento radice in XAML:  
  
 `xmlns:custom="clr-namespace:SDKSample;assembly=SDKSampleLibrary"`  
  
 Riepilogando, il codice XAML seguente include il mapping personalizzato insieme al mapping predefinito e al mapping del prefisso x: consueti nel tag radice, quindi usa un riferimento con prefisso per creare un'istanza di `ExampleClass` in tale interfaccia utente:  
  
```xaml  
<Page x:Class="WPFApplication1.MainPage"  
    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
    xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"  
    xmlns:custom="clr-namespace:SDKSample;assembly=SDKSampleLibrary">  
  ...  
  <custom:ExampleClass/>  
...  
</Page>  
```  
  
### <a name="mapping-to-current-assemblies"></a>Mapping ad assembly correnti  
 È possibile omettere `assembly` se `clr-namespace` a cui si fa riferimento è definito all'interno dello stesso assembly del codice dell'applicazione che fa riferimento alle classi personalizzate. In alternativa, una sintassi equivalente appropriata consiste nello specificare `assembly=` senza token di stringa dopo il segno di uguale.  
  
 Non è possibile usare le classi personalizzate come elemento radice di una pagina se definite nello stesso assembly. Non è necessario eseguire il mapping delle classi parziali, ma solo di quelle che non costituiscono la classe parziale di una pagina dell'applicazione, se si intende fare riferimento a esse come elementi in XAML.  
  
<a name="Mapping_CLR_Namespaces_to_XML_Namespaces_in_an"></a>
## <a name="mapping-clr-namespaces-to-xml-namespaces-in-an-assembly"></a>Mapping di spazi dei nomi CLR a spazi dei nomi XML in un assembly  
 WPF definisce un attributo CLR che viene usato dai processori XAML per eseguire il mapping di più spazi dei nomi CLR a un unico spazio dei nomi XAML. Questo attributo, <xref:System.Windows.Markup.XmlnsDefinitionAttribute>, viene inserito a livello di assembly nel codice sorgente che produce l'assembly. Il codice sorgente dell'assembly WPFWPF usa questo attributo <xref:System.Windows.Controls>per `http://schemas.microsoft.com/winfx/2006/xaml/presentation` eseguire il mapping dei vari spazi dei nomi comuni, ad esempio <xref:System.Windows> e , allo spazio dei nomi .  
  
 Accetta <xref:System.Windows.Markup.XmlnsDefinitionAttribute> due parametri: il nome dello spazio dei nomi XML/XAML e il nome dello spazio dei nomi CLR. Più di <xref:System.Windows.Markup.XmlnsDefinitionAttribute> uno può esistere per eseguire il mapping di più spazi dei nomi CLR allo stesso spazio dei nomi XML. Dopo avere eseguito il mapping, è possibile fare riferimento ai membri degli spazi dei nomi senza nome completo specificando l'istruzione `using` appropriata nella pagina code-behind della classe parziale. Per altri dettagli, vedere <xref:System.Windows.Markup.XmlnsDefinitionAttribute>.  
  
## <a name="designer-namespaces-and-other-prefixes-from-xaml-templates"></a>Spazi dei nomi della finestra di progettazione e altri prefissi di modelli XAML  
 Se si lavora con ambienti di sviluppo e/o con strumenti di progettazione per XAML WPF, si può notare che all'interno del markup XAML esistono altri spazi dei nomi XAML definiti o altri prefissi.  
  
 WPF Designer per Visual Studio usa uno spazio dei `d:`nomi della finestra di progettazione che viene in genere mappato al prefisso . Modelli di progetto più recenti per WPF potrebbero eseguire il mapping preliminare di questo spazio dei nomi XAML per supportare l'interscambio del codice XAML tra WPF Designer per Visual Studio e altri ambienti di progettazione. Questo spazio dei nomi XAML di progettazione è usato per trasmettere lo stato di progettazione durante la sequenza di andata e ritorno dell'interfaccia utente basata su XAML nella finestra di progettazione. Questo spazio dei nomi viene usato anche per funzionalità quali `d:IsDataSource`, che abilitano origini dati di runtime in una finestra di progettazione.  
  
 Un altro prefisso che è possibile vedere mappato è `mc:`. `mc:` è finalizzato alla compatibilità dei markup e usa un modello di compatibilità dei markup non necessariamente specifico di XAML. In alcuni casi, è possibile usare le funzionalità di compatibilità dei markup per scambiare XAML tra framework o tra altri limiti di implementazione di supporto, per lavorare tra contesti di schemi XAML, per garantire la compatibilità per modalità limitate nelle finestre di progettazione e così via. Per altre informazioni sui concetti di compatibilità dei markup e sulla relazione con WPF, vedere [Funzionalità del linguaggio per la compatibilità dei markup (mc:)](markup-compatibility-mc-language-features.md).  
  
## <a name="wpf-and-assembly-loading"></a>WPF e caricamento di assembly  
 Il contesto dello schema XAML per WPF si integra con il <xref:System.AppDomain>modello di applicazione WPFWPF, che a sua volta utilizza il concetto definito da CLR di . La sequenza seguente descrive come il contesto dello schema XAML interpreta come caricare assembly o <xref:System.AppDomain> trovare tipi in fase di esecuzione o di progettazione, in base all'uso di WPFe e ad altri fattori.  
  
1. Scorrere il <xref:System.AppDomain>, cercando un assembly già caricato che corrisponda a tutti gli aspetti del nome, a partire dall'assembly caricato più di recente.  
  
2. Se il nome è <xref:System.Reflection.Assembly.Load%28System.String%29?displayProperty=nameWithType> qualificato, chiamare il nome completo.  
  
3. Se la combinazione nome breve e token di chiave pubblica di un nome qualificato corrisponde all'assembly da cui è stato caricato il markup, restituire tale assembly.  
  
4. Utilizzare il nome breve, ovvero <xref:System.Reflection.Assembly.Load%28System.String%29?displayProperty=nameWithType>il token di chiave pubblica, per chiamare .  
  
5. Se il nome non <xref:System.Reflection.Assembly.LoadWithPartialName%2A?displayProperty=nameWithType>è qualificato, chiamare .  
  
 Per il codice XAML loose il passaggio 3 non viene eseguito. Non è infatti presente alcun assembly da cui effettuare il caricamento.  
  
 XAML compilato per WPF (generato tramite XamlBuildTask) non <xref:System.AppDomain> usa gli assembly già caricati da (passaggio 1). Dall'output di XamlBuildTask,poi, il nome non può mai essere non qualificato, pertanto il passaggio 5 non viene applicato.  
  
 Il codice BAML (generato tramite PresentationBuildTask) usa tutti i passaggi, anche se non deve contenere nomi di assembly non qualificati.  
  
## <a name="see-also"></a>Vedere anche

- [Understanding XML Namespaces](https://docs.microsoft.com/previous-versions/aa468565(v=msdn.10)) (Informazioni sugli spazi dei nomi XML)
- [Panoramica di XAML (WPF)](../../../desktop-wpf/fundamentals/xaml.md)
