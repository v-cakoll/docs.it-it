---
title: Globalizzazione per WPF
ms.date: 03/30/2017
helpviewer_keywords:
- XAML [WPF], international user interface
- XAML [WPF], globalization
- international user interface [WPF], XAML
- globalization [WPF]
ms.assetid: 4571ccfe-8a60-4f06-9b37-7ac0b1c2d10f
ms.openlocfilehash: f1147bf090af23c2f27bac14ab895657ccee60e3
ms.sourcegitcommit: 005980b14629dfc193ff6cdc040800bc75e0a5a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/14/2019
ms.locfileid: "70991552"
---
# <a name="globalization-for-wpf"></a>Globalizzazione per WPF
In questo argomento vengono introdotti i problemi che è necessario conoscere [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] quando si scrivono applicazioni per il mercato globale. Gli elementi di programmazione della globalizzazione sono definiti in .NET <xref:System.Globalization> nello spazio dei nomi.

<a name="xaml_globalization"></a>
## <a name="xaml-globalization"></a>Globalizzazione XAML
 [!INCLUDE[TLA#tla_xaml#initcap](../../../../includes/tlasharptla-xamlsharpinitcap-md.md)]si basa su [!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)] e sfrutta il supporto [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] per la globalizzazione definito nella specifica. Le sezioni seguenti descrivono [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] alcune funzionalità di cui è necessario essere a conoscenza.

<a name="char_reference"></a>
### <a name="character-references"></a>Riferimenti ai caratteri
Un riferimento a un carattere fornisce l'unità di codice UTF16 [!INCLUDE[TLA#tla_unicode](../../../../includes/tlasharptla-unicode-md.md)] del carattere particolare che rappresenta, in formato decimale o esadecimale. Nell'esempio seguente viene illustrato un riferimento a un carattere decimale per la lettera MAIUSCOLa copto o ' Ϩ ':

```
&#1000;
```

Nell'esempio seguente viene illustrato un riferimento a un carattere esadecimale. Si noti che ha una **x** davanti al numero esadecimale.

```
&#x3E8;
```

<a name="encoding"></a>
### <a name="encoding"></a>Codifica
 La codifica supportata da [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] sono ASCII, [!INCLUDE[TLA2#tla_unicode](../../../../includes/tla2sharptla-unicode-md.md)] UTF-16 e UTF-8. L'istruzione Encoding si trova all'inizio del [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] documento. Se non esiste alcun attributo di codifica né un ordine dei byte, il parser userà il valore predefinito UTF-8. UTF-8 e UTF-16 sono i tipi di codifica preferiti. UTF-7 non è supportato. Nell'esempio seguente viene illustrato come specificare una codifica UTF-8 in un [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] file.

```xaml
?xml encoding="UTF-8"?
```

<a name="lang_attrib"></a>
### <a name="language-attribute"></a>Attributo Language
 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]USA [XML: lang](../../xaml-services/xml-lang-handling-in-xaml.md) per rappresentare l'attributo Language di un elemento.  Per sfruttare i <xref:System.Globalization.CultureInfo> vantaggi della classe, il valore dell'attributo Language deve essere uno dei nomi di impostazioni cultura predefiniti da <xref:System.Globalization.CultureInfo>. [xml:lang](../../xaml-services/xml-lang-handling-in-xaml.md) è ereditabile nell'albero di elementi (in base alle regole XML, non necessariamente a causa dell'ereditarietà della proprietà di dipendenza) e il valore predefinito è una stringa vuota se non viene assegnato in modo esplicito.

 L'attributo language è molto utile per specificare le lingue regionali. Il francese, ad esempio, ha ortografia, vocabolario e pronuncia diversi in Francia, Quebec, Belgio e Svizzera. Inoltre, il cinese, il giapponese e il coreano condividono [!INCLUDE[TLA2#tla_unicode](../../../../includes/tla2sharptla-unicode-md.md)]punti di codice in, ma le forme ideogrammi sono diverse e utilizzano tipi di carattere completamente diversi.

 Nell'esempio [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] seguente viene usato `fr-CA` l'attributo Language per specificare il francese canadese.

```xaml
<TextBlock xml:lang="fr-CA">Découvrir la France</TextBlock>
```

<a name="unicode"></a>
### <a name="unicode"></a>Unicode
 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]supporta tutte [!INCLUDE[TLA2#tla_unicode](../../../../includes/tla2sharptla-unicode-md.md)] le funzionalità di, inclusi i surrogati. Fino a quando il set di caratteri può essere mappato a [!INCLUDE[TLA2#tla_unicode](../../../../includes/tla2sharptla-unicode-md.md)], è supportato. GB18030, ad esempio, introduce alcuni caratteri con mapping all'estensione A e B per cinese, giapponese e coreano e le coppie di surrogati, quindi è completamente supportato. Un' [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] applicazione può usare <xref:System.Globalization.StringInfo> per modificare le stringhe senza comprendere se hanno coppie di surrogati o caratteri combinati.

<a name="design_intl_ui_with_xaml"></a>
## <a name="designing-an-international-user-interface-with-xaml"></a>Progettazione di un'interfaccia utente internazionale con XAML
 In questa sezione [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] vengono descritte le funzionalità da tenere in considerazione durante la scrittura di un'applicazione.

<a name="intl_text"></a>
### <a name="international-text"></a>Testo internazionale
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]include l'elaborazione incorporata per tutti i sistemi di scrittura di Microsoft .NET Framework supportati.

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

 I tipi di carattere OpenType consentono la gestione di set [!INCLUDE[TLA2#tla_unicode](../../../../includes/tla2sharptla-unicode-md.md)] di glifi di grandi dimensioni tramite la codifica. Tale codifica consente un esteso supporto internazionale, oltre alle varianti dei glifi tipografici.

 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]il rendering del testo è basato sulla tecnologia Microsoft ClearType dei sottopixel che supporta l'indipendenza della risoluzione. Questo migliora considerevolmente la leggibilità e consente di supportare documenti in stile rivista di qualità elevata per tutti gli script.

<a name="intl_layout"></a>
### <a name="international-layout"></a>Layout internazionale
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] offre un modo molto pratico per supportare layout orizzontali, bidirezionale e verticali. Nel Framework di presentazione <xref:System.Windows.FrameworkElement.FlowDirection%2A> la proprietà può essere usata per definire il layout. I modelli di direzione del flusso sono:

- *LeftToRight*: layout orizzontale per latino, lingue dell'Asia orientale e così via.

- *RightToLeft*: bidirezionale per arabo, ebraico e così via.

<a name="developing_localizable_apps"></a>
## <a name="developing-localizable-applications"></a>Sviluppo di applicazioni localizzabili
 Quando si scrive un'applicazione per il consumo globale, è opportuno ricordare che l'applicazione deve essere localizzabile. Gli argomenti seguenti illustrano alcune importanti considerazioni.

<a name="mui"></a>
### <a name="multilingual-user-interface"></a>Interfaccia utente multilingue
 MUI (Multilingual User Interfaces) è un supporto Microsoft per [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)] passare da una lingua a un'altra. Un' [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] applicazione utilizza il modello di assembly per supportare MUI. Un'applicazione contiene assembly indipendenti dalla lingua, ma anche assembly di risorse satellite dipendenti dalla lingua. Il punto di ingresso è un file EXE gestito nell'assembly principale.  [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]il caricatore di risorse sfrutta il [!INCLUDE[TLA2#tla_netframewk](../../../../includes/tla2sharptla-netframewk-md.md)]Resource Manager di per supportare la ricerca e il fallback delle risorse. Gli assembly satellite di più lingue usano lo stesso assembly principale. L'assembly di risorse caricato dipende dall'oggetto <xref:System.Globalization.CultureInfo.CurrentUICulture%2A> del thread corrente.

<a name="localizable_ui"></a>
### <a name="localizable-user-interface"></a>Interfaccia utente localizzabile
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]le applicazioni [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] utilizzano per definire [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]la relativa. [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] consente agli sviluppatori di specificare una gerarchia di oggetti con un set di proprietà e una logica. L'utilizzo principale di [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] è lo sviluppo [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] di applicazioni, ma può essere utilizzato per specificare una gerarchia di tutti gli oggetti di Common Language Runtime (CLR). La maggior parte [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] degli sviluppatori USA per specificare [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] le applicazioni e usare un linguaggio di C# programmazione come per rispondere all'interazione dell'utente.

 Da un punto di vista delle risorse, [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] un file progettato per descrivere un dipendente dalla [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] lingua è un elemento di risorsa e pertanto il formato di distribuzione finale deve essere localizzabile per supportare le lingue internazionali. Poiché [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] non è in grado [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] di gestire gli eventi, molte applicazioni contengono blocchi di codice per eseguire questa operazione. Per ulteriori informazioni, vedere [Cenni preliminari su XAML (WPF)](xaml-overview-wpf.md). Il codice viene rimosso e compilato in file binari diversi quando un [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] file viene suddiviso in token nel formato BAML di XAML. Il formato BAML dei file XAML, le immagini e altri tipi di oggetti risorsa gestita vengono incorporati nell'assembly di risorse satellite, che può essere localizzato in altre lingue, o nell'assembly principale quando la localizzazione non è necessaria.

> [!NOTE]
> [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]le applicazioni supportano tutte [!INCLUDE[TLA2#tla_netframewk](../../../../includes/tla2sharptla-netframewk-md.md)]le risorse CLR, incluse le tabelle di stringhe, le immagini e così via.

<a name="building_localizable_apps"></a>
### <a name="building-localizable-applications"></a>Compilazione di applicazioni localizzabili
 La localizzazione consente di adattare [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] un a impostazioni cultura diverse. Per rendere localizzabile un' [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] applicazione, gli sviluppatori devono compilare tutte le risorse localizzabili in un assembly di risorse. L'assembly di risorse viene localizzato in lingue diverse e il code-behind usa l'API di gestione delle risorse per il caricamento. Uno dei file necessari per un' [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] applicazione è un file di progetto (con estensione proj). Tutte le risorse usate nell'applicazione devono essere incluse nel file di progetto. L'esempio seguente da un file con estensione csproj illustra come effettuare questa operazione.

```xml
<Resource Include="data\picture1.jpg"/>
<EmbeddedResource Include="data\stringtable.en-US.restext"/>
```

 Per usare una risorsa nell'applicazione <xref:System.Resources.ResourceManager> , creare un'istanza di e caricare la risorsa che si vuole usare. Nell'esempio riportato di seguito viene illustrato come procedere.

 [!code-csharp[LocalizationResources#2](~/samples/snippets/csharp/VS_Snippets_Wpf/LocalizationResources/CSharp/page1.xaml.cs#2)]

<a name="using_clickonce"></a>
## <a name="using-clickonce-with-localized-applications"></a>Uso di ClickOnce con applicazioni localizzate
 ClickOnce è una nuova tecnologia di distribuzione Windows Forms che verrà fornita con Visual Studio 2005. che consente l'installazione e l'aggiornamento di applicazioni Web. Quando un'applicazione distribuita con ClickOnce è localizzata, può essere visualizzata solo nelle impostazioni cultura localizzate. Se, ad esempio, un'applicazione distribuita è localizzata in giapponese, può essere visualizzata [!INCLUDE[TLA#tla_win](../../../../includes/tlasharptla-win-md.md)] solo in giapponese e non in lingua inglese. Questo problema si presenta perché si tratta di uno scenario comune per gli utenti giapponesi di eseguire una versione in lingua inglese di Windows.

 Per risolvere il problema, è necessario impostare l'attributo di fallback su una lingua neutra. Uno sviluppatore di applicazioni può facoltativamente rimuovere risorse dall'assembly principale e specificare che le risorse sono disponibili in un assembly satellite corrispondente a impostazioni cultura specifiche. Per controllare questo processo <xref:System.Resources.NeutralResourcesLanguageAttribute>, usare. Il costruttore della <xref:System.Resources.NeutralResourcesLanguageAttribute> classe dispone di due firme, una che accetta un <xref:System.Resources.UltimateResourceFallbackLocation> parametro per <xref:System.Resources.ResourceManager> specificare il percorso in cui deve estrarre le risorse di fallback: assembly principale o assembly satellite. L'esempio seguente mostra come usare l'attributo. Per il percorso di fallback finale, il codice fa <xref:System.Resources.ResourceManager> in modo che l'oggetto cerchi le risorse nella sottodirectory "de" della directory dell'assembly attualmente in esecuzione.

```csharp
[assembly: NeutralResourcesLanguageAttribute(
    "de" , UltimateResourceFallbackLocation.Satellite)]
```

## <a name="see-also"></a>Vedere anche

- [Panoramica della globalizzazione e localizzazione WPF](wpf-globalization-and-localization-overview.md)
