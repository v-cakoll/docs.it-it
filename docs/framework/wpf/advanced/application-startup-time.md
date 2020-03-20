---
title: Tempo di avvio delle applicazioni
ms.date: 03/30/2017
helpviewer_keywords:
- splash screen [WPF], startup time
- WPF [WPF], startup time
- startup time [WPF]
- application startup [WPF]
- performance [WPF], startup time
ms.assetid: f0ec58d8-626f-4d8a-9873-c20f95e08b96
ms.openlocfilehash: 0fae3ac1769163101dcdb183f4c5c2135354b1fc
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79145423"
---
# <a name="application-startup-time"></a>Tempo di avvio delle applicazioni
La quantità di tempo necessaria per avviare un'applicazione WPF può variare notevolmente. In questo argomento vengono descritte varie tecniche per ridurre il tempo di avvio percepito ed effettivo per un'applicazione Windows Presentation Foundation (WPF).  
  
## <a name="understanding-cold-startup-and-warm-startup"></a>Informazioni su avvio a freddo e avvio a caldo  
 L'avvio a freddo si verifica quando un'applicazione viene avviata per la prima volta dopo un riavvio del sistema, o quando si avvia l'applicazione, la si chiude e quindi la si riavvia dopo un lungo periodo di tempo. All'avvio dell'applicazione, se le pagine necessarie (codice, dati statici, registro e così via) non sono presenti nell'elenco di standby del gestore della memoria di Windows, si verificano errori di pagina. L'accesso al disco è necessario per inserire le pagine in memoria.  
  
 L'avvio a caldo si verifica quando la maggior parte delle pagine per i componenti principali di Common Language Runtime (CLR) sono già caricata in memoria, il che consente di risparmiare molto tempo per l'accesso al disco. Ecco perché un'applicazione gestita si avvia più rapidamente quando viene eseguita per la seconda volta.  
  
## <a name="implement-a-splash-screen"></a>Implementare la schermata iniziale  
 Nei casi in cui c'è un ritardo significativo e inevitabili tra l'avvio di un'applicazione e la visualizzazione della prima interfaccia utente, è possibile ottimizzare il tempo di avvio percepito usando una *schermata iniziale*. Questo approccio consente di visualizzare un'immagine quasi immediatamente dopo l'avvio dell'applicazione da parte dell'utente. Quando l'applicazione è pronta per la visualizzazione della prima interfaccia utente, la schermata iniziale si dissolve. A partire da .NET Framework 3.5 SP1, è possibile utilizzare la <xref:System.Windows.SplashScreen> classe per implementare una schermata iniziale. Vedere [Aggiungere una schermata iniziale in un'applicazione WPF](../app-development/how-to-add-a-splash-screen-to-a-wpf-application.md).  
  
 È anche possibile implementare la schermata iniziale con grafica Win32 nativa. Visualizzare l'implementazione prima che venga chiamato il <xref:System.Windows.Application.Run%2A> metodo.  
  
## <a name="analyze-the-startup-code"></a>Analizzare il codice di avvio  
 Determinare il motivo di un avvio a freddo lento. La causa potrebbe essere il disco I/O, ma non sempre. In generale, è necessario ridurre l'uso di risorse esterne, ad esempio rete, servizi Web o disco.  
  
 Prima di eseguire il test, verificare che nessun altra applicazione o servizio in esecuzione usi il codice gestito o WPF.  
  
 Avviare l'applicazione WPF immediatamente dopo un riavvio e determinare il tempo richiesto per la visualizzazione. Se tutti gli avvii successivi dell'applicazione (avvio a caldo) sono molto più veloci, il problema di avvio a freddo probabilmente è causato da I/O.  
  
 Se il problema di avvio a freddo dell'applicazione non è correlato all'I/O, è probabile che l'applicazione esegua una lunga inizializzazione o un calcolo, attenda il completamento di un evento o richieda una notevole quantità di compilazione JIT all'avvio. Le sezioni seguenti descrivono alcune di queste situazioni in maggior dettaglio.  
  
## <a name="optimize-module-loading"></a>Ottimizzare il modulo di caricamento  
 Usare strumenti come Esplora processi (Procexp.exe) e Tlist.exe per determinare quali moduli l'applicazione carica. Il comando `Tlist <pid>` mostra tutti i moduli caricati da un processo.  
  
 Ad esempio, se non ci si sta connettendo al Web e si nota che System.Web.dll è stato caricato, vi è un modulo nell'applicazione che fa riferimento a questo assembly. Verificare che il riferimento sia necessario.  
  
 Se l'applicazione dispone di più moduli, unirli in un unico modulo. Questo approccio richiede un minor sovraccarico di caricamento di assembly del CLR. Un minor numero di assembly significa inoltre che CLR gestisce un minor numero di stati.  
  
## <a name="defer-initialization-operations"></a>Rinviare le operazioni di inizializzazione  
 È consigliabile posticipare il codice di inizializzazione dopo aver eseguito il rendering della finestra principale dell'applicazione.  
  
 Tenere presente che l'inizializzazione può essere eseguita all'interno di un costruttore di classe, e se il codice di inizializzazione fa riferimento ad altre classi, può causare un effetto a catena in cui vengono eseguiti molti costruttori di classi.  
  
## <a name="avoid-application-configuration"></a>Evitare la configurazione dell'applicazione  
 È consigliabile evitare la configurazione dell'applicazione. Ad esempio, se un'applicazione ha requisiti di configurazione semplici e tempi di avvio stretti, le voci del registro o di un semplice file INI potrebbero essere un'alternativa di avvio più veloce.  
  
## <a name="utilize-the-gac"></a>Usare il GAC  
 Se un assembly non è installato nella Global Assembly Cache (GAC), ci sono ritardi causati dalla verifica hash di assembly con nome sicuro e convalida dell'immagine Ngen se un'immagine nativa per tale assembly è disponibile nel computer. La verifica del nome sicuro viene ignorata per tutti gli assembly installati nella GAC. Per altre informazioni, vedere [Gacutil.exe (Global Assembly Cache Tool)](../../tools/gacutil-exe-gac-tool.md) (Strumento Global Assembly Cache, Gacutil.exe).  
  
## <a name="use-ngenexe"></a>Usare Ngen.exe  
 È consigliabile usare il generatore di immagini native (Ngen.exe) nell'applicazione. L'uso di Ngen.exe indica la negoziazione del consumo di CPU per un maggiore accesso al disco perché l'immagine nativa generata da Ngen.exe è probabilmente più grande dell'immagine MSIL.  
  
 Per migliorare il tempo di avvio a caldo, si deve usare sempre Ngen.exe sull'applicazione, poiché ciò consente di evitare il costo della CPU per la compilazione JIT del codice dell'applicazione.  
  
 In alcuni scenari di avvio a freddo, l'uso si Ngen.exe può essere utile, perché il compilatore JIT (mscorjit.dll) non deve essere caricato.  
  
 La presenza di entrambi i moduli Ngen e JIT può avere effetti negativi, perché è necessario caricare mscorjit.dll e quando il compilatore JIT opera sul codice, l'accesso a molte pagine nelle immagini Ngen deve avvenire quando il compilatore JIT legge i metadati degli assembly.  
  
### <a name="ngen-and-clickonce"></a>ClickOnce e Ngen  
 Anche il modo in cui si prevede di distribuire l'applicazione può fare la differenza in fase di caricamento. La distribuzione dell'applicazione ClickOnce non supporta Ngen. Se si decide di usare Ngen.exe per l'applicazione, è necessario usare un altro meccanismo di distribuzione, ad esempio Windows Installer.  
  
 Per altre informazioni, vedere [Ngen.exe (Native Image Generator)](../../tools/ngen-exe-native-image-generator.md).  
  
### <a name="rebasing-and-dll-address-collisions"></a>Riassegnazione e conflitti di indirizzi di DLL  
 Se si usa Ngen.exe, tenere presente che la riassegnazione può verificarsi quando le immagini native vengono caricate in memoria. Se una DLL non viene caricata all'indirizzo di base preferito perché tale intervallo di indirizzi è già stato allocato, il caricatore di Windows lo caricherà in un altro indirizzo. Questa può essere un'operazione impegnativa.  
  
 È possibile usare lo strumento Virtual Address Dump (Vadump.exe) per verificare se sono presenti moduli in cui tutte le pagine sono private. In questo caso, il modulo potrebbe stato riassegnato a un indirizzo diverso. Di conseguenza, le pagine non possono essere condivise.  
  
 Per altre informazioni su come impostare l'indirizzo di base, vedere [Ngen.exe (Native Image Generator)](../../tools/ngen-exe-native-image-generator.md).  
  
## <a name="optimize-authenticode"></a>Ottimizzare Authenticode  
 La verifica di Authenticode si aggiunge al tempo di avvio. Gli assembly con firma Authenticode devono essere verificati con l'autorità di certificazione (CA). Questa verifica può richiedere tempi lunghi, in quanto può essere necessario connettersi alla rete più volte per scaricare gli elenchi di revoca dei certificati attuali. Consente inoltre la presenza di una catena completa di certificati validi nel percorso a una fonte attendibile. Questo può causare molti secondi di ritardo, mentre l'assembly viene caricato.  
  
 Si consiglia di installare il certificato CA nel computer client oppure di evitare di usare Authenticode quando è possibile. Se per l'applicazione non è richiesta la prova del server di pubblicazione, non è necessario pagare il costo della verifica della firma.  
  
 A partire da .NET Framework 3.5.NET Framework 3.5, è disponibile un'opzione di configurazione che consente di bypassare la verifica Authenticode. A tale scopo, aggiungere la seguente impostazione nel file app.exe.config:  
  
```xml  
<configuration>  
    <runtime>  
        <generatePublisherEvidence enabled="false"/>
    </runtime>  
</configuration>  
```  
  
 Per ulteriori informazioni, vedere [ \<generatePublisherEvidence> Element](../../configure-apps/file-schema/runtime/generatepublisherevidence-element.md).  
  
## <a name="compare-performance-on-windows-vista"></a>Confrontare le prestazioni in Windows Vista  
 Il gestore della memoria in Windows Vista è una tecnologia denominata SuperFetch. SuperFetch analizza i modelli di uso della memoria nel tempo per determinare il contenuto della memoria ottimale per un utente specifico. Funziona in modo continuo per garantire la disponibilità del contenuto in qualsiasi momento.  
  
 Questo approccio è diverso dalla tecnica di recupero preliminare usata in Windows XP, che consente di precaricare i dati in memoria senza analisi dei modelli di uso. Nel corso del tempo, se l'utente usa spesso l'applicazione WPF in Windows Vista, il tempo di avvio a freddo dell'applicazione può migliorare.  
  
## <a name="use-appdomains-efficiently"></a>Usare in modo efficiente AppDomain  
 Se possibile, caricare gli assembly in un'area di codice indipendente dal dominio per assicurarsi che l'immagine nativa, se presente, venga usata in tutti gli AppDomain creati nell'applicazione.  
  
 Per prestazioni ottimali, applicare una comunicazione efficiente tra domini, riducendo le chiamate tra domini. Quando possibile, usare le chiamate senza argomenti oppure con argomenti di tipo primitivo.  
  
## <a name="use-the-neutralresourceslanguage-attribute"></a>Usare l'attributo NeutralResourcesLanguage  
 Utilizzare <xref:System.Resources.NeutralResourcesLanguageAttribute> il per specificare <xref:System.Resources.ResourceManager>le impostazioni cultura neutre per il file . Questo approccio impedisce ricerche di assembly non riuscite.  
  
## <a name="use-the-binaryformatter-class-for-serialization"></a>Usare la classe BinaryFormatter per la serializzazione  
 Se è necessario utilizzare <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> la serializzazione, utilizzare la classe anziché la <xref:System.Xml.Serialization.XmlSerializer> classe . La <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> classe viene implementata nella libreria di classi base (BCL) nell'assembly mscorlib.dll. L'oggetto <xref:System.Xml.Serialization.XmlSerializer> viene implementato nell'assembly System.Xml.dll, che potrebbe essere una DLL aggiuntiva da caricare.  
  
 Se è necessario <xref:System.Xml.Serialization.XmlSerializer> utilizzare la classe , è possibile ottenere prestazioni migliori se si pregenera l'assembly di serializzazione.  
  
## <a name="configure-clickonce-to-check-for-updates-after-startup"></a>Configurare ClickOnce per verificare gli aggiornamenti in seguito all'avvio  
 Se l'applicazione utilizza ClickOnceClickOnce, evitare l'accesso alla rete all'avvio configurando ClickOnce per verificare la disponibilità di aggiornamenti nel sito di distribuzione dopo l'avvio dell'applicazione.  
  
 Se si utilizza il modello di applicazione browser XAML (XBAP), tenere presente che ClickOnce controlla il sito di distribuzione per gli aggiornamenti anche se l'applicazione XBAP è già presente nella cache ClickOnce. Per altre informazioni, vedere [ClickOnce Security and Deployment](/visualstudio/deployment/clickonce-security-and-deployment).  
  
## <a name="configure-the-presentationfontcache-service-to-start-automatically"></a>Configurare l'avvio automatico del servizio PresentationFontCache  
 La prima applicazione WPF da eseguire dopo un riavvio è il servizio PresentationFontCache. Il servizio memorizza nella cache i tipi di carattere del sistema, migliora l'accesso al tipo di carattere e le prestazioni complessive. Si verifica un sovraccarico all'avvio del servizio e in alcuni ambienti controllati, si consiglia di configurare l'avvio automatico del servizio al riavvio del sistema.  
  
## <a name="set-data-binding-programmatically"></a>Impostare il data binding a livello di codice  
 Invece di usare <xref:System.Windows.FrameworkElement.DataContext%2A> XAML per impostare il metodo in modo <xref:System.Windows.Application.OnActivated%2A> dichiarativo per la finestra principale, valuta la possibilità di impostarlo a livello di codice nel metodo.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.SplashScreen>
- <xref:System.AppDomain>
- <xref:System.Resources.NeutralResourcesLanguageAttribute>
- <xref:System.Resources.ResourceManager>
- [Aggiungere una schermata iniziale in un'applicazione WPF](../app-development/how-to-add-a-splash-screen-to-a-wpf-application.md)
- [Ngen.exe (generatore di immagini native)](../../tools/ngen-exe-native-image-generator.md)
- [\<elemento> generatePublisherEvidence](../../configure-apps/file-schema/runtime/generatepublisherevidence-element.md)
