---
title: Panoramica delle applicazioni browser XAML di WPF
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- XBAP [WPF], XAML browser application
- WPF XAML browser applications (XBAP)
- XAML browser applications (XBAP)
- browser-hosted applications [WPF]
ms.assetid: 3a7a86a8-75d5-4898-96b9-73da151e5e16
ms.openlocfilehash: 8121b6e8c5a136f5f89b59636a7cb7f15794164a
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/02/2018
ms.locfileid: "43462479"
---
# <a name="wpf-xaml-browser-applications-overview"></a>Panoramica delle applicazioni browser XAML di WPF
<a name="introduction"></a>
[!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)] Combina le funzionalità delle applicazioni Web e applicazioni rich client. In modo analogo alle applicazioni Web, le applicazioni XBAP possono essere distribuite in un server Web e avviate da Internet Explorer o Firefox. Come le applicazioni rich client, le applicazioni XBAP possono sfruttare i vantaggi delle funzionalità di WPF. Lo sviluppo di applicazioni XBAP è simile allo sviluppo di applicazioni rich client. In questo argomento viene fornita un'introduzione semplice e dettagliata allo sviluppo di applicazioni XBAP e vengono illustrate le differenze esistenti tra lo sviluppo di questo tipo di applicazioni e lo sviluppo di applicazioni rich client standard.  
  
 Di seguito sono elencate le diverse sezioni di questo argomento:  
  
-   [Creazione di una nuova applicazione browser XAML (XBAP)](#creating_a_new_xaml_browser_application_xbap)  
  
-   [Distribuzione di un'applicazione XBAP](#deploying_a_xbap)  
  
-   [Comunicazione con la pagina Web host](#communicating_with_the_host_web_page)  
  
-   [Considerazioni sulla sicurezza delle applicazioni XBAP](#xbap_security_considerations)  
  
-   [Considerazioni sulle prestazioni dei tempi di avvio di XBAP](#xbap_start_time_performance_considerations)  
  
<a name="creating_a_new_xaml_browser_application_xbap"></a>   
## <a name="creating-a-new-xaml-browser-application-xbap"></a>Creazione di una nuova applicazione browser XAML (XBAP)  
 Il modo più semplice per creare un nuovo progetto XBAP è con Microsoft Visual Studio. Quando si crea un nuovo progetto, selezionare **Applicazione browser WPF** nell'elenco di modelli. Per altre informazioni, vedere [Procedura: creare un nuovo progetto di applicazione browser WPF](https://msdn.microsoft.com/library/72ef4d90-e163-42a1-8df0-ea7ccfd1901f).  
  
 Quando viene eseguito, il progetto XBAP viene aperto in una finestra del browser anziché in una finestra autonoma. Quando si esegue il debug del progetto XBAP in Visual Studio, l'applicazione viene eseguita con le autorizzazioni dell'area Internet e pertanto vengono generate eccezioni di sicurezza se tali autorizzazioni non vengono superate. Per ulteriori informazioni, vedere [Sicurezza](../../../../docs/framework/wpf/security-wpf.md) e [Sicurezza con attendibilità parziale in WPF](../../../../docs/framework/wpf/wpf-partial-trust-security.md).  
  
> [!NOTE]
>  Se non si sta sviluppando con Visual Studio o si desidera eseguire altre informazioni sui file di progetto, vedere [compilazione di un'applicazione WPF](../../../../docs/framework/wpf/app-development/building-a-wpf-application-wpf.md).  
  
<a name="deploying_a_xbap"></a>   
## <a name="deploying-an-xbap"></a>Distribuzione di un'applicazione XBAP  
 Quando si compila un'applicazione XBAP, nell'output sono inclusi i tre file seguenti:  
  
|File|Descrizione|  
|----------|-----------------|  
|Eseguibile (con estensione exe)|Contiene il codice compilato e ha un'estensione exe.|  
|Manifesto dell'applicazione (con estensione manifest)|Contiene i metadati associati all'applicazione e ha un'estensione manifest.|  
|Manifesto di distribuzione (con estensione xbap)|Questo file contiene le informazioni da ClickOnce per distribuire l'applicazione e con estensione xbap.|  
  
 Le applicazioni XBAP vengono distribuite in un server Web, ad esempio Microsoft [!INCLUDE[TLA#tla_iis50](../../../../includes/tlasharptla-iis50-md.md)] o versioni successive. Non è necessario installare .NET Framework nel server Web, ma è necessario registrare il [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] [!INCLUDE[TLA#tla_mime](../../../../includes/tlasharptla-mime-md.md)] estensioni dei nomi di tipi e file. Per ulteriori informazioni, vedere [Configurare IIS 5.0 e IIS 6.0 per distribuire applicazioni WPF](../../../../docs/framework/wpf/app-development/how-to-configure-iis-5-0-and-iis-6-0-to-deploy-wpf-applications.md).  
  
 Per preparare l'applicazione XBAP per la distribuzione, copiare il file con estensione exe e i file manifesto associati nel server Web. Creare una pagina HTML contenente un collegamento ipertestuale per aprire il manifesto di distribuzione, ovvero il file con estensione xbap. Quando l'utente fa clic sul collegamento al file con estensione xbap, ClickOnce gestisce automaticamente i meccanismi di download e l'avvio dell'applicazione. Nel codice di esempio seguente viene illustrata una pagina HTML contenente un collegamento ipertestuale che punta a un'applicazione XBAP.  
  
```html
<html>   
    <head></head>  
    <body>   
        <a href="XbapEx.xbap">Click this link to launch the application</a>  
    </body>   
</html>  
```  
  
 È inoltre possibile ospitare un'applicazione XBAP nel frame di una pagina Web. Creare una pagina Web con uno o più frame. Impostare la proprietà di origine di un frame sul file manifesto di distribuzione. Se per la comunicazione tra la pagina Web di hosting e l'applicazione XBAP si desidera utilizzare il meccanismo incorporato, sarà necessario ospitare l'applicazione in un frame. Nel codice di esempio seguente viene illustrata una pagina HTML con due frame in cui l'origine per il secondo frame viene impostata su un'applicazione XBAP.  
  
```html
<html>   
    <head>
        <title>A page with frames</title>
    </head>  
    <frameset cols="50%,50%">   
        <frame src="introduction.htm">   
        <frame src="XbapEx.xbap">   
    </frameset>   
</html>  
```  
  
### <a name="clearing-cached-xbaps"></a>Cancellazione di applicazioni XBAP memorizzate nella cache  
 In alcuni casi, dopo aver ricompilato e avviato l'applicazione XBAP, è possibile che ci accorga che è aperta una versione precedente dell'applicazione XBAP. Questa situazione può ad esempio verificarsi quando il numero di versione dell'assembly XBAP è statico e l'applicazione XBAP viene avviata dalla riga di comando. In questo caso, poiché il numero della versione memorizzata nella cache (quella avviata in precedenza) e quello della nuova versione coincidono, la nuova versione dell'applicazione XBAP non viene scaricata. Al contrario, viene caricata la versione memorizzata nella cache.  
  
 In queste situazioni, è possibile rimuovere la versione memorizzata nella cache usando il **Mage** comando (installato con Visual Studio o il SDK di Windows) al prompt dei comandi. L'esecuzione del comando seguente determina la cancellazione della cache dell'applicazione.  
  
 ```console
 Mage.exe -cc
 ```
  
 L'esecuzione di questo comando garantisce che venga avviata la versione più recente dell'applicazione XBAP. Quando si esegue il debug dell'applicazione in Visual Studio, la versione più recente dell'applicazione XBAP deve essere avviata. In generale, è necessario aggiornare il numero di versione della distribuzione a ogni compilazione. Per ulteriori informazioni sul comando Mage, vedere [Mage.exe (Strumento per la generazione e la modifica di manifesti)](../../../../docs/framework/tools/mage-exe-manifest-generation-and-editing-tool.md).  
  
<a name="communicating_with_the_host_web_page"></a>   
## <a name="communicating-with-the-host-web-page"></a>Comunicazione con la pagina Web host  
 Quando l'applicazione è ospitata in un frame HTML, è possibile comunicare con la pagina Web che contiene l'applicazione XBAP. A tale scopo, recuperare il <xref:System.Windows.Interop.BrowserInteropHelper.HostScript%2A> proprietà di <xref:System.Windows.Interop.BrowserInteropHelper>. Questa proprietà restituisce un oggetto script che rappresenta la finestra HTML. È quindi possibile accedere alle proprietà, ai metodi e agli eventi nell'[oggetto finestra](https://go.microsoft.com/fwlink/?LinkId=160274) utilizzando la normale sintassi del punto. È inoltre possibile accedere a metodi di script e variabili globali. Nell'esempio seguente viene illustrato come recuperare l'oggetto script e chiudere il browser.  
  
 [!code-csharp[XbapBrowserInterop#10](../../../../samples/snippets/csharp/VS_Snippets_Wpf/xbapbrowserinterop/cs/page1.xaml.cs#10)]
 [!code-vb[XbapBrowserInterop#10](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/xbapbrowserinterop/vb/page1.xaml.vb#10)]  
  
### <a name="debugging-xbaps-that-use-hostscript"></a>Debug di applicazioni XBAP che utilizzano HostScript  
 Se l'applicazione XBAP utilizza il <xref:System.Windows.Interop.BrowserInteropHelper.HostScript%2A> oggetto per comunicare con la finestra HTML, sono disponibili due impostazioni che è necessario specificare per l'esecuzione e il debug dell'applicazione in Visual Studio. L'applicazione deve disporre dell'accesso al sito di origine ed è necessario avviare l'applicazione con la pagina HTML che contiene l'applicazione XBAP. Nei passaggi seguenti viene descritto come controllare queste due impostazioni:  
  
1.  In Visual Studio aprire le proprietà del progetto.  
  
2.  Nella scheda **Sicurezza** fare clic su **Avanzate**.  
  
     Verrà visualizzata la finestra di dialogo Impostazioni di sicurezza avanzate.  
  
3.  Verificare che la casella di controllo **Concedi all'applicazione accesso al proprio sito di origine** sia selezionata, quindi fare clic su **OK**.  
  
4.  Nella scheda **Debug** selezionare l'opzione **Avvia il browser con URL** e specificare l'URL della pagina HTML che contiene l'applicazione XBAP.  
  
5.  In Internet Explorer fare clic su **Strumenti**, quindi selezionare **Opzioni Internet**.  
  
     Viene visualizzata la finestra di dialogo Opzioni Internet.  
  
6.  Fare clic sulla scheda **Avanzate**.  
  
7.  Nell'elenco **Impostazioni** in **Sicurezza** selezionare la casella di controllo **Consenti l'esecuzione di contenuto attivo in file in Risorse del computer**.  
  
8.  Fare clic su **OK**.  
  
     Le modifiche avranno effetto dopo il riavvio di Internet Explorer.  
  
> [!CAUTION]
>  L'abilitazione di contenuto attivo in Internet Explorer può esporre il computer a rischi. Se non si desidera modificare le impostazioni di sicurezza di Internet Explorer, è possibile avviare la pagina HTML da un server e collegare il debugger di Visual Studio al processo.  
  
<a name="xbap_security_considerations"></a>   
## <a name="xbap-security-considerations"></a>Considerazioni sulla sicurezza delle applicazioni XBAP  
 Le applicazioni XBAP vengono in genere eseguite in una sandbox di sicurezza con attendibilità parziale limitata al set di autorizzazioni dell'area Internet. Di conseguenza, l'implementazione deve supportare il subset di elementi di WPF sono supportati nell'area Internet oppure è necessario elevare le autorizzazioni dell'applicazione. Per ulteriori informazioni, vedere [Sicurezza](../../../../docs/framework/wpf/security-wpf.md).  
  
 Quando si usa un <xref:System.Windows.Controls.WebBrowser> controllo nell'applicazione WPF crea internamente un'istanza del controllo WebBrowser ActiveX nativo. Quando l'applicazione è un'applicazione XBAP con attendibilità parziale in esecuzione in Internet Explorer, il controllo ActiveX viene eseguito in un thread dedicato del processo Internet Explorer. Vengono pertanto applicate le limitazioni seguenti:  
  
-   Il <xref:System.Windows.Controls.WebBrowser> controllo deve fornire un comportamento simile al browser host, incluse le restrizioni di sicurezza. È possibile controllare alcune di queste restrizioni di sicurezza tramite le impostazioni di sicurezza di Internet Explorer. Per ulteriori informazioni, vedere [Sicurezza](../../../../docs/framework/wpf/security-wpf.md).  
  
-   Viene generata un'eccezione quando un'applicazione XBAP viene caricata tra domini in una pagina HTML.  
  
-   L'input avviene in un thread separato da WPF <xref:System.Windows.Controls.WebBrowser>, pertanto non è possibile intercettare l'input da tastiera e lo stato IME non è condiviso.  
  
-   È possibile che la temporizzazione o l'ordine di navigazione risulti diverso a causa del controllo ActiveX in esecuzione in un altro thread. Ad esempio, la navigazione a una pagina non viene sempre annullata dall'avvio di un'altra richiesta di navigazione.  
  
-   Un controllo ActiveX personalizzato può causare problemi alla comunicazione dal momento che l'applicazione WPF è in esecuzione in un thread separato.  
  
-   <xref:System.Windows.Interop.HwndHost.MessageHook> non viene generato perché <xref:System.Windows.Interop.HwndHost> Impossibile sottoclasse di una finestra in esecuzione in un altro thread o processo.  
  
### <a name="creating-a-full-trust-xbap"></a>Creazione di un'applicazione XBAP con attendibilità totale  
 Se per l'applicazione XBAP è richiesta l'attendibilità totale, è possibile modificare il progetto per abilitare questa autorizzazione. Nei passaggi seguenti viene descritto come abilitare l'attendibilità totale:  
  
1.  In Visual Studio aprire le proprietà del progetto.  
  
2.  Nella scheda **Sicurezza** selezionare l'opzione **È un'applicazione completamente attendibile**.  
  
 Questa impostazione determina le modifiche seguenti:  
  
-   Nel file di progetto il valore dell'elemento `<TargetZone>` viene impostato su `Custom`.  
  
-   Nel manifesto dell'applicazione (app.manifest) un attributo `Unrestricted="true"` viene aggiunto all'elemento `PermissionSet`.  
  
    ```xml
    <PermissionSet class="System.Security.PermissionSet"   
                   version="1"   
                   ID="Custom"   
                   SameSite="site"   
                   Unrestricted="true" />  
    ```  
  
### <a name="deploying-a-full-trust-xbap"></a>Distribuzione di un'applicazione XBAP con attendibilità totale  
 Quando si distribuisce un'applicazione XBAP con attendibilità totale che non segue il modello di distribuzione attendibile di ClickOnce, il comportamento che si ottiene quando l'utente esegue l'applicazione dipenderà dall'area di sicurezza. In alcuni casi, l'utente riceverà un avviso quando tenta di installare il codice. L'utente potrà scegliere se continuare o annullare l'installazione. La tabella seguente descrive il comportamento dell'applicazione per ogni area di sicurezza e le azioni necessarie relative all'applicazione per acquisire attendibilità totale.  
  
|Area di sicurezza|Comportamento|Ottenere l'attendibilità totale|  
|-------------------|--------------|------------------------|  
|Computer locale|Attendibilità totale automatica|Nessuna azione necessaria.|  
|Intranet e siti attendibili|Richiesta di attendibilità totale|Firma dell'applicazione XBAP con un certificato in modo che l'utente veda l'origine nel prompt.|  
|Internet|Esito negativo con "Attendibilità non concessa"|Firma dell'applicazione XBAP con un certificato.|  
  
> [!NOTE]
>  Il comportamento descritto nella tabella precedente è relativo alle applicazioni XBAP con attendibilità totale che non seguono il modello di distribuzione attendibile di ClickOnce.  
  
 Per la distribuzione di un'applicazione XBAP con attendibilità totale, si consiglia di utilizzare il modello di distribuzione attendibile di ClickOnce. Quando si utilizza questo modello, all'applicazione XBAP viene concessa automaticamente l'attendibilità totale indipendentemente dall'area di sicurezza e all'utente non viene visualizzata alcuna richiesta. Come parte di questo modello, è necessario firmare l'applicazione con un certificato di un editore attendibile. Per altre informazioni, vedere [Cenni preliminari sulla distribuzione di applicazioni attendibili](/visualstudio/deployment/trusted-application-deployment-overview) e [Introduzione alla firma del codice](https://go.microsoft.com/fwlink/?LinkId=166327).  
  
<a name="xbap_start_time_performance_considerations"></a>   
## <a name="xbap-start-time-performance-considerations"></a>Considerazioni sulle prestazioni dei tempi di avvio delle applicazioni XBAP  
 Un aspetto importante delle prestazioni di applicazioni XBAP riguarda i tempi di avvio. Se un'applicazione XBAP è la prima applicazione WPF da caricare, i tempi di *avvio a freddo* possono essere pari a dieci o più secondi. Questa situazione si verifica perché il rendering della pagina di avanzamento viene eseguito da WPF e per visualizzare l'applicazione, CLR e WPF devono essere avviati a freddo.  
  
 Quando l'avvio viene eseguito in [!INCLUDE[net_v35SP1_short](../../../../includes/net-v35sp1-short-md.md)], i tempi di avvio a freddo delle applicazioni XBAP vengono ridotti mediante la visualizzazione di una pagina di avanzamento non gestita all'inizio del ciclo di distribuzione. La pagina di avanzamento viene visualizzata subito dopo l'avvio dell'applicazione, in quanto viene visualizzata da codice ospitato in maniera nativa ed eseguendone il rendering in HTML.  
  
 Inoltre, la concorrenza migliorata della sequenza di download ClickOnce migliora l'ora di inizio fino a dieci percento. Dopo aver ClickOnce, download e convalida dei manifesti, vengono avviati il download dell'applicazione e l'indicatore di stato avvia da aggiornare.  
  
## <a name="see-also"></a>Vedere anche  
 [Configurare Visual Studio per eseguire il debug di un'applicazione browser XAML in grado di chiamare un servizio Web](../../../../docs/framework/wpf/app-development/configure-vs-to-debug-a-xaml-browser-to-call-a-web-service.md)  
 [Distribuzione di un'applicazione WPF](../../../../docs/framework/wpf/app-development/deploying-a-wpf-application-wpf.md)
