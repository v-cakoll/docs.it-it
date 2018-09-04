---
title: Configurazione delle funzionalità di traccia
ms.date: 03/30/2017
helpviewer_keywords:
- tracing [WCF]
ms.assetid: 82922010-e8b3-40eb-98c4-10fc05c6d65d
ms.openlocfilehash: c5064d90c8601ee44be593446b0fd5ad483e57f2
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2018
ms.locfileid: "43542297"
---
# <a name="configuring-tracing"></a>Configurazione delle funzionalità di traccia
In questo argomento viene illustrato come attivare la funzionalità di traccia, configurare origini di traccia affinché vengano create tracce e impostati livelli di traccia, impostare traccia e propagazione di attività per supportare la correlazione tra tracce end-to-end e configurare i listener di traccia affinché accedano alle tracce.  
  
 Per consigli sulle impostazioni di traccia nell'ambiente di produzione o debug, fare riferimento alla [impostazioni consigliate per la traccia e registrazione dei messaggi](../../../../../docs/framework/wcf/diagnostics/tracing/recommended-settings-for-tracing-and-message-logging.md).  
  
> [!IMPORTANT]
>  In Windows 8 è necessario eseguire l'applicazione con privilegi elevati (Esegui come amministratore) affinché l'applicazione generi i log di traccia.  
  
## <a name="enabling-tracing"></a>Abilitazione della traccia  
 Windows Communication Foundation (WCF) restituisce i dati seguenti per l'analisi diagnostica:  
  
-   Tracce per le attività cardine dei processi in tutti i componenti delle applicazioni, ad esempio chiamate dell'operazione, eccezioni del codice, avvisi e altri eventi di elaborazione significativi.  
  
-   Eventi di errore di Windows quando la funzionalità di traccia non viene eseguita correttamente. Visualizzare [la registrazione degli eventi](../../../../../docs/framework/wcf/diagnostics/event-logging/index.md).  
  
 Traccia di WCF si basa su <xref:System.Diagnostics>. Per utilizzare la funzionalità di traccia, è necessario definire le origini di traccia nel file di configurazione o nel codice. WCF definisce un'origine di traccia per ogni assembly WCF. Il `System.ServiceModel` origine di traccia è l'origine di traccia WCF più generale e Registra attività cardine di elaborazione attraverso lo stack di comunicazione WCF, dall'immissione/abbandono del trasporto all'immissione/abbandono di codice utente. L'origine della traccia `System.ServiceModel.MessageLogging` registra tutti i messaggi che vengono propagati nel sistema.  
  
 Per impostazione predefinita, la traccia non è attivata. Per attivare la traccia, è necessario creare un listener di traccia e impostare un livello di traccia diverso da "Off" per l'origine di traccia selezionata nella configurazione. in caso contrario, WCF genera tracce. Se non si specifica un listener, la traccia verrà disattivata automaticamente. Se viene definito un listener ma non è specificato alcun livello, per impostazione predefinita viene selezionato il livello "Disattivo", ovvero non viene generata alcuna traccia.  
  
 Se si usano punti di estendibilità WCF, ad esempio invoker di operazioni personalizzati, è necessario generare tracce proprie. Infatti, se si implementa un punto di estendibilità, WCF non è più possibile creare tracce standard nel percorso predefinito. Se non si implementa il supporto della traccia manuale creando tracce, è possibile che le tracce previste non vengano visualizzate.  
  
 È possibile configurare la funzionalità di traccia modificando il file di configurazione dell'applicazione, Web.config per applicazioni di tipo host Web o Appname.exe.config per applicazioni indipendenti. Di seguito è riportato un esempio di modifica applicabile. Per altre informazioni su queste impostazioni, vedere la sezione "Configurazione di traccia nei listener per l'utilizzo di tracce".  
  
```xml  
<configuration>  
   <system.diagnostics>  
      <sources>  
            <source name="System.ServiceModel"   
                    switchValue="Information, ActivityTracing"  
                    propagateActivity="true">  
            <listeners>  
               <add name="traceListener"   
                   type="System.Diagnostics.XmlWriterTraceListener"   
                   initializeData= "c:\log\Traces.svclog" />  
            </listeners>  
         </source>  
      </sources>  
   </system.diagnostics>  
</configuration>  
```  
  
> [!NOTE]
>  Per modificare il file di configurazione di un progetto di servizio WCF in Visual Studio, con il pulsante destro fare clic sul file di configurazione dell'applicazione, ovvero Web. config per le applicazioni ospitate sul Web o appname per applicazione self-hosted in **Esplora soluzioni** . Quindi scegliere il **Modifica configurazione WCF** menu di scelta rapida. Verrà avviata il [dello strumento Editor di configurazione (SvcConfigEditor.exe)](../../../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md), che consente di modificare le impostazioni di configurazione dei servizi WCF tramite un'interfaccia utente grafica.  
  
## <a name="configuring-trace-sources-to-emit-traces"></a>Configurazione delle origini di traccia per la generazione di tracce  
 WCF definisce un'origine di traccia per ogni assembly. I listener definiti per tale origine accedono alle tracce generate all'interno di un assembly. Vengono definite le origini di traccia seguenti:  
  
-   System. ServiceModel: Registra tutte le fasi dell'elaborazione di WCF, ogni volta che la configurazione viene letta, viene elaborato un messaggio nel trasporto, sicurezza, l'elaborazione di un messaggio viene inviata nel codice utente e così via.  
  
-   System.ServiceModel.MessageLogging: registra tutti i messaggi propagati nel sistema.  
  
-   System.IdentityModel.  
  
-   System.ServiceModel.Activation.  
  
-   System.IO.Log: registrazione per l'interfaccia .NET Framework nel Common Log File System (CLFS).  
  
-   System.Runtime.Serialization: registra quando gli oggetti vengono letti o scritti.  
  
-   CardSpace.  
  
 È possibile configurare ogni origine di traccia per l'utilizzo dello stesso listener (condiviso), come indicato nell'esempio di configurazione seguente.  
  
```xml  
<configuration>  
    <system.diagnostics>  
        <sources>  
            <source name="System.ServiceModel"   
                    switchValue="Information, ActivityTracing"  
                    propagateActivity="true">  
                <listeners>  
                    <add name="xml" />  
                </listeners>  
            </source>  
            <source name="CardSpace">  
                <listeners>  
                    <add name="xml" />  
                </listeners>  
            </source>  
            <source name="System.IO.Log">  
                <listeners>  
                    <add name="xml" />  
                </listeners>  
            </source>  
            <source name="System.Runtime.Serialization">  
                <listeners>  
                    <add name="xml" />  
                </listeners>  
            </source>  
            <source name="System.IdentityModel">  
                <listeners>  
                    <add name="xml" />  
                </listeners>  
            </source>  
        </sources>  
  
        <sharedListeners>  
            <add name="xml"  
                 type="System.Diagnostics.XmlWriterTraceListener"  
                 initializeData="c:\log\Traces.svclog" />  
        </sharedListeners>  
    </system.diagnostics>  
</configuration>  
```  
  
 È inoltre possibile aggiungere origini di traccia definite dall'utente, come dimostrato nell'esempio seguente, in modo che vengano create tracce di codice utente.  
  
```xml  
<system.diagnostics>  
   <sources>  
       <source name="UserTraceSource" switchValue="Warning, ActivityTracing" >  
          <listeners>  
              <add name="xml"  
                 type="System.Diagnostics.XmlWriterTraceListener"  
                 initializeData="C:\logs\UserTraces.svclog" />  
          </listeners>  
       </source>  
   </sources>  
   <trace autoflush="true" />   
</system.diagnostics>  
```  
  
 Per altre informazioni sulla creazione di origini di traccia definite dall'utente, vedere [estendendo Tracing](../../../../../docs/framework/wcf/samples/extending-tracing.md).  
  
## <a name="configuring-trace-listeners-to-consume-traces"></a>Configurazione dei listener di traccia per l'utilizzo di tracce  
 In fase di esecuzione, WCF feed di dati di traccia ai listener che elaborano i dati. WCF fornisce vari listener predefiniti per <xref:System.Diagnostics>, diversi a livello del formato utilizzato per l'output. È inoltre possibile aggiungere tipi di listener personalizzati.  
  
 È possibile utilizzare l'istruzione `add` per specificare il nome e il tipo del listener di traccia che si desidera utilizzare. Nella configurazione di esempio, il listener viene denominato `traceListener` e viene aggiunto il listener di traccia standard di .NET Framework, ovvero `System.Diagnostics.XmlWriterTraceListener`, come tipo da utilizzare. Per ogni origine di traccia è possibile aggiungere il numero desiderato di listener. Se il listener di traccia genera la traccia in un file, nel file di configurazione è necessario specificare il percorso e il nome del file di output. A tal fine impostare `initializeData` sul nome del file per quel listener. Se non si specifica un nome file, viene generato un nome file a caso in base al tipo di listener utilizzato. Se viene utilizzato <xref:System.Diagnostics.XmlWriterTraceListener>, viene generato un nome file senza estensione. Se si implementa un listener personalizzato, è inoltre possibile utilizzare questo attributo per ricevere dati di inizializzazione diversi dal nome file. È ad esempio possibile specificare un identificatore di database per questo attributo.  
  
 È possibile configurare un listener di traccia personalizzato per l'invio di tracce in transito, ad esempio a un database remoto. I distributori di applicazioni devono applicare un apposito controllo di accesso nei log di traccia del computer remoto.  
  
 È inoltre possibile configurare un listener di traccia a livello di programmazione. Per altre informazioni, vedere [procedura: creare e inizializzare listener di traccia](https://go.microsoft.com/fwlink/?LinkId=94648) e [creazione di un TraceListener personalizzato](https://go.microsoft.com/fwlink/?LinkId=96239).  
  
> [!CAUTION]
>  Poiché `System.Diagnostics.XmlWriterTraceListener` non è thread-safe, è possibile che l'origine di traccia blocchi le risorse in modo esclusivo durante la restituzione di tracce. Quando molti thread restituiscono tracce a un'origine configurata per l'utilizzo di questo listener, può verificarsi un conflitto di risorse con conseguente calo delle prestazioni. Per risolvere il problema, è necessario implementare un listener personalizzato di tipo thread-safe.  
  
## <a name="trace-level"></a>Livello di traccia  
 Il livello di traccia viene controllato in base all'impostazione `switchValue` dell'origine di traccia. Nella tabella seguente viene fornita una descrizione dei livelli di traccia disponibili.  
  
|Livello di traccia|Natura degli eventi registrati|Contenuto degli eventi registrati|Eventi registrati|Destinazione utente|  
|-----------------|----------------------------------|-----------------------------------|--------------------|-----------------|  
|Disattivato|N/D|N/D|Non vengono create tracce.|N/D|  
|Critico|Eventi "negativi": eventi che indicano un'elaborazione imprevista o una condizione di errore.||Vengono registrate eccezioni non gestite comprese le seguenti:<br /><br /> -OutOfMemoryException<br />-ThreadAbortException (il CLR richiama qualsiasi ThreadAbortExceptionHandler)<br />-StackOverflowException (non intercettabile)<br />-ConfigurationErrorsException<br />-SEHException<br />-Errori di avvio applicazione<br />-Eventi Failfast<br />-Il sistema si blocca<br />-Messaggi non elaborabili: tracce di messaggi che l'applicazione avrà esito negativo.|Amministratori<br /><br /> Sviluppatori di applicazioni|  
|Error|Eventi "negativi": eventi che indicano un'elaborazione imprevista o una condizione di errore.|Si è verificata un'elaborazione imprevista. L'applicazione non è stata in grado di eseguire un'attività come previsto. L'applicazione, tuttavia, è ancora in esecuzione.|Vengono registrate tutte le eccezioni.|Amministratori<br /><br /> Sviluppatori di applicazioni|  
|Avviso|Eventi "negativi": eventi che indicano un'elaborazione imprevista o una condizione di errore.|Un possibile problema si è verificato o potrebbe verificarsi, ma l'applicazione funziona ancora correttamente. Tuttavia, potrebbe smettere di farlo.|-L'applicazione riceve più richieste superiore a quello consentiranno dalle impostazioni di limitazione.<br />-La coda di ricezione è prossimo alla capacità massima configurata.<br />-Tempo scaduto.<br />-Le credenziali sono rifiutate.|Amministratori<br /><br /> Sviluppatori di applicazioni|  
|Informazioni|Eventi "Positivi": eventi che contrassegnano attività cardine eseguite correttamente|Attività cardine importanti e corrette di esecuzione dell'applicazione, indipendentemente dal funzionamento corretto o non corretto dell'applicazione.|In generale il sistema genera messaggi informativi utili per il monitoraggio e la diagnosi dello stato di sistema, la valutazione delle prestazioni o il profiling. È possibile utilizzare queste informazioni per la pianificazione della capacità e la gestione delle prestazioni:<br /><br /> -I canali vengono creati.<br />-Vengono creati i listener endpoint.<br />-Messaggio entra o abbandona il trasporto.<br />-Token di sicurezza viene recuperato.<br />-L'impostazione configurazione viene letta.|Amministratori<br /><br /> Sviluppatori di applicazioni<br /><br /> Sviluppatori di prodotti|  
|Dettagliato|Eventi "Positivi": eventi che contrassegnano attività cardine eseguite correttamente.|Vengono generati eventi di basso livello per codice utente e manutenzione.|In genere è possibile utilizzare questo livello per il debug o l'ottimizzazione dell'applicazione.<br /><br /> -Intestazione del messaggio comprensibile.|Amministratori<br /><br /> Sviluppatori di applicazioni<br /><br /> Sviluppatori di prodotti|  
|ActivityTracing||Eventi di flusso tra attività di elaborazione e componenti.|Questo livello consente ad amministratori e sviluppatori di mettere in correlazione applicazioni nello stesso dominio applicazione:<br /><br /> -Le tracce per limiti di attività, ad esempio avviare o arrestare.<br />-Le tracce per trasferimenti.|Tutti|  
|Tutti||L'applicazione può funzionare correttamente. Vengono generati tutti gli eventi.|Tutti gli eventi precedenti.|Tutti|  
  
 I livelli da Dettagliato a Critico sono inclusi l'uno dentro l'altro, ovvero ogni livello di traccia comprende tutti i livelli che lo precedono ad eccezione del livello Disattivo. Un listener in ascolto al livello Avviso, ad esempio, riceve le tracce Critico, Errore e Avviso. Il livello Tutto comprende gli eventi da Dettagliato a Critico ed eventi di Traccia attività.  
  
> [!CAUTION]
>  I livelli Informazioni, Dettagliato e ActivityTracing generano molte tracce che possono influire negativamente sulla velocità effettiva dei messaggi se tutte le risorse disponibili nel computer sono esaurite.  
  
## <a name="configuring-activity-tracing-and-propagation-for-correlation"></a>Configurazione della traccia e della propagazione di attività a fini di correlazione  
 Il valore `activityTracing` specificato per l'attributo `switchValue` consente di attivare la traccia di attività, che genera tracce per limiti e trasferimenti di attività all'interno di endpoint.  
  
> [!NOTE]
>  Quando si usa alcune funzionalità di estendibilità in WCF, potrebbe ottenere un <xref:System.NullReferenceException> quando è abilitata la traccia di attività. Per risolvere questo problema, controllare il file di configurazione dell'applicazione e verificare che l'attributo `switchValue` per l'origine di traccia non sia impostato su `activityTracing`.  
  
 L'attributo `propagateActivity` indica se l'attività deve essere propagata ad altri endpoint che partecipano nello scambio di messaggi. Impostando questo valore su `true`, è possibile osservare file di traccia generati da due endpoint qualsiasi e notare come un set di tracce in un endpoint venga propagato a un set di tracce in un altro endpoint.  
  
 Per altre informazioni sulla traccia di attività e la propagazione, vedere [propagazione](../../../../../docs/framework/wcf/diagnostics/tracing/propagation.md).  
  
 Entrambe `propagateActivity` e `ActivityTracing` valori booleani si applicano a System. ServiceModel TraceSource. Il `ActivityTracing` valore si applica anche a qualsiasi origine di traccia, tra cui WCF o quelle definite dall'utente.  
  
 Non è possibile utilizzare l'attributo `propagateActivity` con le origini di traccia definite dall'utente. Per la propagazione di ID attività di codice utente, accertarsi di non impostare l'attributo `ActivityTracing` di ServiceModel, mantenendo l'attributo `propagateActivity` di ServiceModel impostato su `true`.  
  
## <a name="see-also"></a>Vedere anche  
 [Traccia](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [Amministrazione e diagnostica](../../../../../docs/framework/wcf/diagnostics/index.md)  
 [Procedura: creare e inizializzare listener di traccia](https://go.microsoft.com/fwlink/?LinkId=94648)  
 [Creazione di un TraceListener personalizzato](https://go.microsoft.com/fwlink/?LinkId=96239)
