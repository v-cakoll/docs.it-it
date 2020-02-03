---
title: Globalizzazione
ms.date: 03/30/2017
helpviewer_keywords:
- XAML [WPF], international user interface
- XAML [WPF], globalization
- international user interface [WPF], XAML
- globalization [WPF]
ms.assetid: 4571ccfe-8a60-4f06-9b37-7ac0b1c2d10f
ms.openlocfilehash: 95c0368889dfa4e69b5e40b32ea19ba845aa5c30
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76747048"
---
# <a name="globalization-for-wpf"></a>Globalizzazione per WPF
In questo argomento vengono introdotti i problemi che è necessario conoscere quando si scrive [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] applicazioni per il mercato globale. Gli elementi di programmazione della globalizzazione sono definiti in .NET nello spazio dei nomi <xref:System.Globalization>.

<a name="xaml_globalization"></a>
## <a name="xaml-globalization"></a>Globalizzazione XAML
 Extensible Application Markup Language (XAML) si basa su XML e sfrutta il supporto per la globalizzazione definito nella specifica XML. Le sezioni seguenti descrivono alcune funzionalità di [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] di cui è necessario essere a conoscenza.

<a name="char_reference"></a>
### <a name="character-references"></a>Riferimenti ai caratteri
Un riferimento a un carattere fornisce l'unità di codice UTF16 del carattere Unicode particolare che rappresenta, in formato decimale o esadecimale. Nell'esempio seguente viene illustrato un riferimento a un carattere decimale per la lettera MAIUSCOLa copto o ' Ϩ ':

```
&#1000;
```

Nell'esempio seguente viene illustrato un riferimento a un carattere esadecimale. Si noti che ha una **x** davanti al numero esadecimale.

```
&#x3E8;
```

<a name="encoding"></a>
### <a name="encoding"></a>Codifica
 La codifica supportata da [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] sono ASCII, Unicode UTF-16 e UTF-8. L'istruzione Encoding si trova all'inizio del documento [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]. Se non esiste alcun attributo di codifica né un ordine dei byte, il parser userà il valore predefinito UTF-8. UTF-8 e UTF-16 sono i tipi di codifica preferiti. UTF-7 non è supportato. Nell'esempio seguente viene illustrato come specificare una codifica UTF-8 in un file di [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].

```xaml
?xml encoding="UTF-8"?
```

<a name="lang_attrib"></a>
### <a name="language-attribute"></a>Attributo Language
 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] USA [XML: lang](../../../desktop-wpf/xaml-services/xml-language-handling.md) per rappresentare l'attributo Language di un elemento.  Per sfruttare i vantaggi della classe <xref:System.Globalization.CultureInfo>, il valore dell'attributo Language deve essere uno dei nomi di impostazioni cultura predefiniti da <xref:System.Globalization.CultureInfo>. [xml:lang](../../../desktop-wpf/xaml-services/xml-language-handling.md) è ereditabile nell'albero di elementi (in base alle regole XML, non necessariamente a causa dell'ereditarietà della proprietà di dipendenza) e il valore predefinito è una stringa vuota se non viene assegnato in modo esplicito.

 L'attributo language è molto utile per specificare i dialetti. Il francese, ad esempio, ha ortografia, vocabolario e pronuncia diversi in Francia, Quebec, Belgio e Svizzera. Inoltre, il cinese, il giapponese e il coreano condividono punti di codice in Unicode, ma le forme ideogrammi sono diverse e utilizzano tipi di carattere completamente diversi.

 Nell'esempio di [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] seguente viene usato l'attributo Language `fr-CA` per specificare il francese canadese.

```xaml
<TextBlock xml:lang="fr-CA">Découvrir la France</TextBlock>
```

<a name="unicode"></a>
### <a name="unicode"></a>Unicode
 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] supporta tutte le funzionalità Unicode, inclusi i surrogati. Se il set di caratteri può essere mappato a Unicode, è supportato. GB18030, ad esempio, introduce alcuni caratteri con mapping all'estensione A e B per cinese, giapponese e coreano e le coppie di surrogati, quindi è completamente supportato. Un'applicazione [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] può usare <xref:System.Globalization.StringInfo> per modificare le stringhe senza comprendere se hanno coppie di surrogati o caratteri di combinazione.

<a name="design_intl_ui_with_xaml"></a>
## <a name="designing-an-international-user-interface-with-xaml"></a>Progettazione di un'interfaccia utente internazionale con XAML
 In questa sezione vengono descritte [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] funzionalità da tenere in considerazione durante la scrittura di un'applicazione.

<a name="intl_text"></a>
### <a name="international-text"></a>Testo internazionale
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] include l'elaborazione incorporata per tutti i sistemi di scrittura supportati da Microsoft .NET Framework.

 Sono attualmente supportati gli script seguenti:

- Arabo

- Bengali

- Devanagari

- Cirillico

- Greco

- Gujarati

- Gurmukhi

- Ebraico

- Script ideografici

- Kannada

- Lao

- Latino

- Malayalam

- Mongolo

- Odia

- Siriaco

- Tamil

- Telugu

- Thaana

- Thailandese*

- Tibetano

 *In questa versione sono supportate la visualizzazione e la modifica del testo in thailandese. L'interruzione parole non è supportata.

 Non sono attualmente supportati gli script seguenti:

- Khmer

- Antico hangul coreano

- Myanmar

- Singalese

 Tutti i motori di sistema di scrittura supportano i tipi di carattere OpenType. I tipi di carattere OpenType possono includere le tabelle di layout OpenType che consentono agli autori di tipi di carattere di progettare migliori tipi di carattere tipografici internazionali e di fascia alta. Le tabelle di layout del tipo di carattere OpenType contengono informazioni sulle sostituzioni dei glifi, il posizionamento del glifo, la giustificazione e il posizionamento della linea di base, consentendo alle applicazioni di elaborazione del testo di migliorare il layout

 I tipi di carattere OpenType consentono la gestione di set di glifi di grandi dimensioni utilizzando la codifica Unicode. Tale codifica consente un esteso supporto internazionale, oltre alle varianti dei glifi tipografici.

 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] rendering del testo è basato sulla tecnologia Microsoft ClearType dei sottopixel che supporta l'indipendenza dalla risoluzione. Questo migliora considerevolmente la leggibilità e consente di supportare documenti in stile rivista di qualità elevata per tutti gli script.

<a name="intl_layout"></a>
### <a name="international-layout"></a>Layout internazionale
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] offre un modo molto pratico per supportare layout orizzontali, bidirezionale e verticali. Nel Framework di presentazione è possibile utilizzare la proprietà <xref:System.Windows.FrameworkElement.FlowDirection%2A> per definire il layout. I modelli di direzione del flusso sono:

- *LeftToRight*: layout orizzontale per latino, lingue dell'Asia orientale e così via.

- *RightToLeft*: bidirezionale per arabo, ebraico e così via.

<a name="developing_localizable_apps"></a>
## <a name="developing-localizable-applications"></a>Sviluppo di applicazioni localizzabili
 Quando si scrive un'applicazione per il consumo globale, è opportuno ricordare che l'applicazione deve essere localizzabile. Gli argomenti seguenti illustrano alcune importanti considerazioni.

<a name="mui"></a>
### <a name="multilingual-user-interface"></a>Interfaccia utente multilingue
 MUI (Multilingual User Interfaces) è un supporto Microsoft per il cambio di interfacce utente da una lingua a un'altra. Un'applicazione [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] utilizza il modello di assembly per supportare MUI. Un'applicazione contiene assembly indipendenti dalla lingua, ma anche assembly di risorse satellite dipendenti dalla lingua. Il punto di ingresso è un file EXE gestito nell'assembly principale.  [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] caricatore di risorse sfrutta il Resource Manager del Framework per supportare la ricerca e il fallback delle risorse. Gli assembly satellite di più lingue usano lo stesso assembly principale. L'assembly di risorse caricato dipende dalla <xref:System.Globalization.CultureInfo.CurrentUICulture%2A> del thread corrente.

<a name="localizable_ui"></a>
### <a name="localizable-user-interface"></a>Interfaccia utente localizzabile
 le applicazioni [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] utilizzano [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] per definire la loro [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]. [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] consente agli sviluppatori di specificare una gerarchia di oggetti con un set di proprietà e una logica. L'utilizzo principale del [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] consiste nello sviluppo di applicazioni [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], ma può essere utilizzato per specificare una gerarchia di tutti gli oggetti Common Language Runtime (CLR). La maggior parte degli sviluppatori USA [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] per specificare il [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] dell'applicazione e usare un linguaggio C# di programmazione come per rispondere all'interazione dell'utente.

 Da un punto di vista delle risorse, un file di [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] progettato per descrivere una [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] dipendente dalla lingua è un elemento di risorsa e pertanto il formato di distribuzione finale deve essere localizzabile per supportare le lingue internazionali. Poiché [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] non è in grado di gestire gli eventi, molte applicazioni [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] contengono blocchi di codice per eseguire questa operazione. Per ulteriori informazioni, vedere [Cenni preliminari su XAML (WPF)](../../../desktop-wpf/fundamentals/xaml.md). Il codice viene rimosso e compilato in file binari diversi quando un file di [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] viene suddiviso in token nel formato BAML di XAML. Il formato BAML dei file XAML, le immagini e altri tipi di oggetti risorsa gestita vengono incorporati nell'assembly di risorse satellite, che può essere localizzato in altre lingue, o nell'assembly principale quando la localizzazione non è necessaria.

> [!NOTE]
> [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] applicazioni supportano tutte le risorse di FrameworkCLR, tra cui tabelle di stringhe, immagini e così via.

<a name="building_localizable_apps"></a>
### <a name="building-localizable-applications"></a>Compilazione di applicazioni localizzabili
 La localizzazione consente di adattare un [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] a impostazioni cultura diverse. Per rendere localizzabile un'applicazione [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], gli sviluppatori devono compilare tutte le risorse localizzabili in un assembly di risorse. L'assembly di risorse viene localizzato in lingue diverse e il code-behind usa l'API di gestione delle risorse per il caricamento. Uno dei file necessari per un'applicazione [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] è un file di progetto (con estensione proj). Tutte le risorse usate nell'applicazione devono essere incluse nel file di progetto. L'esempio seguente da un file con estensione csproj illustra come effettuare questa operazione.

```xml
<Resource Include="data\picture1.jpg"/>
<EmbeddedResource Include="data\stringtable.en-US.restext"/>
```

 Per usare una risorsa nell'applicazione, creare un'istanza di un <xref:System.Resources.ResourceManager> e caricare la risorsa che si vuole usare. Nell'esempio riportato di seguito viene illustrato come procedere.

 [!code-csharp[LocalizationResources#2](~/samples/snippets/csharp/VS_Snippets_Wpf/LocalizationResources/CSharp/page1.xaml.cs#2)]

<a name="using_clickonce"></a>
## <a name="using-clickonce-with-localized-applications"></a>Uso di ClickOnce con applicazioni localizzate
 ClickOnce è una nuova tecnologia di distribuzione Windows Forms che verrà fornita con Visual Studio 2005. che consente l'installazione e l'aggiornamento di applicazioni Web. Quando un'applicazione distribuita con ClickOnce è localizzata, può essere visualizzata solo nelle impostazioni cultura localizzate. Se, ad esempio, un'applicazione distribuita è localizzata in giapponese, può essere visualizzata solo in Windows giapponese non in lingua inglese. Questo problema si presenta perché si tratta di uno scenario comune per gli utenti giapponesi di eseguire una versione in lingua inglese di Windows.

 Per risolvere il problema, è necessario impostare l'attributo di fallback su una lingua neutra. Uno sviluppatore di applicazioni può facoltativamente rimuovere risorse dall'assembly principale e specificare che le risorse sono disponibili in un assembly satellite corrispondente a impostazioni cultura specifiche. Per controllare questo processo, usare il <xref:System.Resources.NeutralResourcesLanguageAttribute>. Il costruttore della classe <xref:System.Resources.NeutralResourcesLanguageAttribute> dispone di due firme, una che accetta un parametro di <xref:System.Resources.UltimateResourceFallbackLocation> per specificare il percorso in cui il <xref:System.Resources.ResourceManager> deve estrarre le risorse di fallback: assembly principale o assembly satellite. L'esempio seguente mostra come usare l'attributo. Per il percorso di fallback finale, il codice fa in modo che il <xref:System.Resources.ResourceManager> cerchi le risorse nella sottodirectory "de" della directory dell'assembly attualmente in esecuzione.

```csharp
[assembly: NeutralResourcesLanguageAttribute(
    "de" , UltimateResourceFallbackLocation.Satellite)]
```

## <a name="see-also"></a>Vedere anche

- [Cenni preliminari sulla globalizzazione e localizzazione WPF](wpf-globalization-and-localization-overview.md)
