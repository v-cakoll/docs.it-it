---
title: Globalizzazione per WPF
ms.date: 03/30/2017
ms.prod: .net-framework
ms.technology: dotnet-wpf
ms.topic: article
helpviewer_keywords:
- XAML [WPF], international user interface
- XAML [WPF], globalization
- international user interface [WPF], XAML
- globalization [WPF]
ms.assetid: 4571ccfe-8a60-4f06-9b37-7ac0b1c2d10f
caps.latest.revision: "35"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 418a1b6d2033b8bc84a18578cfc227c5f227ad91
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/22/2017
---
# <a name="globalization-for-wpf"></a>Globalizzazione per WPF
In questo argomento vengono presentati i problemi da prendere in considerazione quando si scrive [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] applicazioni per il mercato globale. Gli elementi di programmazione di globalizzazione sono definiti [!INCLUDE[TLA#tla_net](../../../../includes/tlasharptla-net-md.md)] in `System.Globalization`.  
  

  
<a name="xaml_globalization"></a>   
## <a name="xaml-globalization"></a>Globalizzazione XAML  
 [!INCLUDE[TLA#tla_xaml#initcap](../../../../includes/tlasharptla-xamlsharpinitcap-md.md)]si basa sul [!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)] e consente di sfruttare il supporto di globalizzazione definito nel [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] specifica. Nelle sezioni seguenti vengono descritte alcune [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] funzionalità che è necessario essere consapevoli di.  
  
<a name="char_reference"></a>   
### <a name="character-references"></a>Riferimenti ai caratteri  
Un riferimento a carattere fornisce l'unità di codice UTF16 dello specifico [!INCLUDE[TLA#tla_unicode](../../../../includes/tlasharptla-unicode-md.md)] di caratteri rappresenta, decimale o esadecimale. Nell'esempio seguente viene mostrato un riferimento di carattere decimale per COPTO ALFABETO COPTO oppure 'Ϩ':

```
&#1000;
```

Nell'esempio seguente viene illustrato un riferimento a carattere esadecimale. Si noti che ha un **x** davanti a numero esadecimale.

```
&#x3E8;
```

<a name="encoding"></a>   
### <a name="encoding"></a>Codifica  
 Le codifiche supportate da [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] sono [!INCLUDE[TLA#tla_ascii](../../../../includes/tlasharptla-ascii-md.md)], [!INCLUDE[TLA2#tla_unicode](../../../../includes/tla2sharptla-unicode-md.md)] UTF-16 e UTF-8. L'istruzione di codifica si trova all'inizio di [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] documento. Se non esiste alcun attributo di codifica né un ordine dei byte, il parser userà il valore predefinito UTF-8. UTF-8 e UTF-16 sono i tipi di codifica preferiti. UTF-7 non è supportato. Nell'esempio seguente viene illustrato come specificare una codifica UTF-8 in un [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] file.  
  
```  
?xml encoding="UTF-8"?  
```  
  
<a name="lang_attrib"></a>   
### <a name="language-attribute"></a>Attributo Language  
 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]Usa [XML: lang](../../../../docs/framework/xaml-services/xml-lang-handling-in-xaml.md) per rappresentare l'attributo language dell'elemento.  Per sfruttare il <xref:System.Globalization.CultureInfo> (classe), il valore dell'attributo lingua deve essere uno dei nomi di impostazioni cultura predefiniti da <xref:System.Globalization.CultureInfo>. [xml:lang](../../../../docs/framework/xaml-services/xml-lang-handling-in-xaml.md) è ereditabile nell'albero di elementi (in base alle regole XML, non necessariamente a causa dell'ereditarietà della proprietà di dipendenza) e il valore predefinito è una stringa vuota se non viene assegnato in modo esplicito.  
  
 L'attributo language è molto utile per specificare i dialetti. Il francese, ad esempio, ha ortografia, vocabolario e pronuncia diversi in Francia, Quebec, Belgio e Svizzera. Anche il cinese, giapponese e coreano condividere i punti di codice nella [!INCLUDE[TLA2#tla_unicode](../../../../includes/tla2sharptla-unicode-md.md)], ma le forme ideografiche sono diverse e che utilizzano diversi tipi di carattere.  
  
 Nell'esempio [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] esempio Usa il `fr-CA` attributo language per specificare la lingua francese canadese.  
  
```xml  
<TextBlock xml:lang="fr-CA">Découvrir la France</TextBlock>  
```  
  
<a name="unicode"></a>   
### <a name="unicode"></a>Unicode  
 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]supporta tutti [!INCLUDE[TLA2#tla_unicode](../../../../includes/tla2sharptla-unicode-md.md)] funzionalità tra cui surrogati. Fino a quando il set di caratteri può essere mappato a [!INCLUDE[TLA2#tla_unicode](../../../../includes/tla2sharptla-unicode-md.md)], è supportato. GB18030, ad esempio, introduce alcuni caratteri con mapping all'estensione A e B per cinese, giapponese e coreano e le coppie di surrogati, quindi è completamente supportato. Oggetto [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] applicazione può utilizzare <xref:System.Globalization.StringInfo> per modificare le stringhe senza capire se dispongono delle coppie di surrogati o combinazione di caratteri.  
  
<a name="design_intl_ui_with_xaml"></a>   
## <a name="designing-an-international-user-interface-with-xaml"></a>Progettazione di un'interfaccia utente internazionale con XAML  
 In questa sezione descrive [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] funzionalità che è necessario considerare quando si scrive un'applicazione.  
  
<a name="intl_text"></a>   
### <a name="international-text"></a>Testo internazionale  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]include l'elaborazione predefinita per tutti i [!INCLUDE[TLA#tla_winfx](../../../../includes/tlasharptla-winfx-md.md)] sistemi di scrittura è supportata.  
  
 Sono attualmente supportati gli script seguenti:  
  
-   Arabo  
  
-   Bengali  
  
-   Devanagari  
  
-   Cirillico  
  
-   Greco  
  
-   Gujarati  
  
-   Gurmukhi  
  
-   Ebraico  
  
-   Script ideografici  
  
-   Kannada  
  
-   Lao  
  
-   Latino  
  
-   Malayalam  
  
-   Mongolo  
  
-   Odia  
  
-   Siriaco  
  
-   Tamil  
  
-   Telugu  
  
-   Thaana  
  
-   Thailandese*  
  
-   Tibetano  
  
 *In questa versione sono supportate la visualizzazione e la modifica del testo in thailandese. L'interruzione parole non è supportata.  
  
 Non sono attualmente supportati gli script seguenti:  
  
-   Khmer  
  
-   Antico hangul coreano  
  
-   Myanmar  
  
-   Singalese  
  
 Il sistema di scrittura motori supporto [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] tipi di carattere. [!INCLUDE[TLA2#tla_opentype](../../../../includes/tla2sharptla-opentype-md.md)]tipi di carattere possono includere il [!INCLUDE[TLA2#tla_opentype](../../../../includes/tla2sharptla-opentype-md.md)] tabelle layout che consentono ai creatori di tipo di carattere progettare meglio ottimale caratteri tipografici internazionali e di fascia alta. Il [!INCLUDE[TLA2#tla_opentype](../../../../includes/tla2sharptla-opentype-md.md)] carattere layout che contengono informazioni sulle sostituzioni, il posizionamento del glifo, giustificazione e sul posizionamento di base, consentendo alle applicazioni di elaborazione del testo migliorare il layout del testo.  
  
 [!INCLUDE[TLA2#tla_opentype](../../../../includes/tla2sharptla-opentype-md.md)]tipi di carattere consentono la gestione di grandi dimensioni glifo imposta utilizzando [!INCLUDE[TLA2#tla_unicode](../../../../includes/tla2sharptla-unicode-md.md)] codifica. Tale codifica consente un esteso supporto internazionale, oltre alle varianti dei glifi tipografici.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]il rendering del testo [!INCLUDE[TLA#tla_ct](../../../../includes/tlasharptla-ct-md.md)] tecnologia pixel secondaria che supporta l'indipendenza dalla risoluzione. Questo migliora considerevolmente la leggibilità e consente di supportare documenti in stile rivista di qualità elevata per tutti gli script.  
  
<a name="intl_layout"></a>   
### <a name="international-layout"></a>Layout internazionale  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] offre un modo molto pratico per supportare layout orizzontali, bidirezionale e verticali. Nel framework di presentazione di <xref:System.Windows.FrameworkElement.FlowDirection%2A> proprietà può essere utilizzata per definire il layout. I modelli di direzione del flusso sono:  
  
-   *LeftToRight*: layout orizzontale per latino, lingue dell'Asia orientale e così via.  
  
-   *RightToLeft*: bidirezionale per arabo, ebraico e così via.  
  
<a name="developing_localizable_apps"></a>   
## <a name="developing-localizable-applications"></a>Sviluppo di applicazioni localizzabili  
 Quando si scrive un'applicazione per il consumo globale, è opportuno ricordare che l'applicazione deve essere localizzabile. Gli argomenti seguenti illustrano alcune importanti considerazioni.  
  
<a name="mui"></a>   
### <a name="multilingual-user-interface"></a>Interfaccia utente multilingue  
 Interfacce utente multilingue (MUI) è un [!INCLUDE[TLA#tla_ms](../../../../includes/tlasharptla-ms-md.md)] il supporto per il cambio [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)] da una lingua a altra. Oggetto [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] applicazione utilizza il modello di assembly per supportare l'interfaccia MUI. Un'applicazione contiene assembly indipendenti dalla lingua, ma anche assembly di risorse satellite dipendenti dalla lingua. Il punto di ingresso è un file EXE gestito nell'assembly principale.  [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]caricatore di risorse consente di sfruttare il [!INCLUDE[TLA2#tla_netframewk](../../../../includes/tla2sharptla-netframewk-md.md)]del gestore delle risorse per supportare la ricerca di risorse e del fallback. Gli assembly satellite di più lingue usano lo stesso assembly principale. Dipende da assembly di risorse che viene caricato il <xref:System.Globalization.CultureInfo.CurrentUICulture%2A> del thread corrente.  
  
<a name="localizable_ui"></a>   
### <a name="localizable-user-interface"></a>Interfaccia utente localizzabile  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]le applicazioni utilizzano [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] per definire i relativi [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]. [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] consente agli sviluppatori di specificare una gerarchia di oggetti con un set di proprietà e una logica. L'utilizzo principale di [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] è necessario sviluppare [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] applicazioni ma può essere utilizzata per specificare una gerarchia di [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] oggetti. Maggior parte degli sviluppatori [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] per specificare le applicazioni [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] e usare un linguaggio di programmazione, ad esempio [!INCLUDE[TLA#tla_cshrp](../../../../includes/tlasharptla-cshrp-md.md)] per rispondere all'interazione dell'utente.  
  
 Dal punto di vista della risorsa, una [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] file progettato per descrivere un dipendenti dalla lingua [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] è un elemento di risorsa, pertanto il formato di distribuzione finale deve essere localizzabile per supportare lingue internazionali. Poiché [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] non può gestire eventi molti [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] applicazioni contengono blocchi di codice per eseguire questa operazione. Per ulteriori informazioni, vedere [Panoramica di XAML (WPF)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md). Codice viene rimosso e compilato in diversi file binari quando un [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] file è suddiviso in token nel modulo BAML di XAML. Il formato BAML dei file XAML, le immagini e altri tipi di oggetti risorsa gestita vengono incorporati nell'assembly di risorse satellite, che può essere localizzato in altre lingue, o nell'assembly principale quando la localizzazione non è necessaria.  
  
> [!NOTE]
>  [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]applicazioni supportano tutte le [!INCLUDE[TLA2#tla_netframewk](../../../../includes/tla2sharptla-netframewk-md.md)] [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] risorse tra le tabelle di stringhe, immagini e così via.  
  
<a name="building_localizable_apps"></a>   
### <a name="building-localizable-applications"></a>Compilazione di applicazioni localizzabili  
 Localizzazione si intende l'adattamento un [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] a impostazioni cultura diverse. Per rendere un [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] localizzabili, gli sviluppatori devono compilare tutte le risorse localizzabili in un assembly di risorse dell'applicazione. Assembly di risorse è localizzato in diverse lingue e il code-behind utilizza la gestione delle risorse [!INCLUDE[TLA#tla_api](../../../../includes/tlasharptla-api-md.md)] da caricare. Uno dei file necessari per un [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] applicazione è un file di progetto (proj). Tutte le risorse usate nell'applicazione devono essere incluse nel file di progetto. L'esempio seguente da un file con estensione csproj illustra come effettuare questa operazione.  
  
```xml  
<Resource Include="data\picture1.jpg"/>  
<EmbeddedResource Include="data\stringtable.en-US.restext"/>  
```  
  
 Per utilizzare una risorsa nell'applicazione creare un'istanza di un <xref:System.Resources.ResourceManager> e caricare la risorsa a cui si desidera utilizzare. Nell'esempio riportato di seguito viene illustrato come procedere.  
  
 [!code-csharp[LocalizationResources#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LocalizationResources/CSharp/page1.xaml.cs#2)]  
  
<a name="using_clickonce"></a>   
## <a name="using-clickonce-with-localized-applications"></a>Uso di ClickOnce con applicazioni localizzate  
 ClickOnce è una nuova tecnologia di distribuzione di Windows Form che verrà forniti [!INCLUDE[TLA#tla_visualstu2005](../../../../includes/tlasharptla-visualstu2005-md.md)]. che consente l'installazione e l'aggiornamento di applicazioni Web. Quando un'applicazione distribuita con ClickOnce è localizzata, può essere visualizzata solo nelle impostazioni cultura localizzate. Ad esempio, se un'applicazione distribuita è localizzata in giapponese, può essere visualizzato solo nella versione giapponese [!INCLUDE[TLA#tla_win](../../../../includes/tlasharptla-win-md.md)] non in lingua inglese [!INCLUDE[TLA2#tla_win](../../../../includes/tla2sharptla-win-md.md)]. Ciò costituisce un problema perché è uno scenario comune per gli utenti giapponesi eseguire una versione inglese di [!INCLUDE[TLA2#tla_win](../../../../includes/tla2sharptla-win-md.md)].  
  
 Per risolvere il problema, è necessario impostare l'attributo di fallback su una lingua neutra. Uno sviluppatore di applicazioni può facoltativamente rimuovere risorse dall'assembly principale e specificare che le risorse sono disponibili in un assembly satellite corrispondente a impostazioni cultura specifiche. A questo scopo, utilizzare il <xref:System.Resources.NeutralResourcesLanguageAttribute>. Il costruttore del <xref:System.Resources.NeutralResourcesLanguageAttribute> classe presenta due firme, uno che accetta un <xref:System.Resources.UltimateResourceFallbackLocation> parametro per specificare il percorso in cui il <xref:System.Resources.ResourceManager> deve estrarre le risorse di fallback: assembly principale o un assembly satellite. L'esempio seguente mostra come usare l'attributo. Per il percorso di fallback finale, il codice provoca il <xref:System.Resources.ResourceManager> per cercare le risorse nella sottodirectory "de" della directory dell'assembly attualmente in esecuzione.  
  
```  
[assembly: NeutralResourcesLanguageAttribute(  
    "de" , UltimateResourceFallbackLocation.Satellite)]  
```  
  
## <a name="see-also"></a>Vedere anche  
 [Cenni preliminari sulla globalizzazione e localizzazione WPF](../../../../docs/framework/wpf/advanced/wpf-globalization-and-localization-overview.md)
