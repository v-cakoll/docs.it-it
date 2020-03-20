---
title: Problemi di sicurezza e suggerimenti utili per la traccia
ms.date: 03/30/2017
ms.assetid: 88bc2880-ecb9-47cd-9816-39016a07076f
ms.openlocfilehash: 5ced4f3a3a5e83564703db88b28ee2b3c6eeb1a0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79185713"
---
# <a name="security-concerns-and-useful-tips-for-tracing"></a><span data-ttu-id="902f4-102">Problemi di sicurezza e suggerimenti utili per la traccia</span><span class="sxs-lookup"><span data-stu-id="902f4-102">Security Concerns and Useful Tips for Tracing</span></span>
<span data-ttu-id="902f4-103">In questo argomento viene descritto come proteggere informazioni riservate e vengono elencati suggerimenti utili durante l'utilizzo di WebHost.</span><span class="sxs-lookup"><span data-stu-id="902f4-103">This topic describes how you can protect sensitive information from being exposed, as well as useful tips when using WebHost.</span></span>  
  
## <a name="using-a-custom-trace-listener-with-webhost"></a><span data-ttu-id="902f4-104">Utilizzo di un listener di traccia personalizzato con WebHost</span><span class="sxs-lookup"><span data-stu-id="902f4-104">Using a Custom Trace Listener with WebHost</span></span>  
 <span data-ttu-id="902f4-105">Nello scrivere listener di traccia personalizzati, tenere presente la possibilità che le tracce vadano perse nel caso di un servizio Host Web.</span><span class="sxs-lookup"><span data-stu-id="902f4-105">If you are writing your own trace listener, you should be aware of the possibility that traces might be lost in the case of a Web-hosted service.</span></span> <span data-ttu-id="902f4-106">Durante il riciclo, WebHost arresta il processo reale e subentra un duplicato.</span><span class="sxs-lookup"><span data-stu-id="902f4-106">When WebHost recycles, it shuts down the live process while a duplicate takes over.</span></span> <span data-ttu-id="902f4-107">È necessario, tuttavia, che i due processi possano ancora accedere alla stessa risorsa, a seconda del tipo di listener.</span><span class="sxs-lookup"><span data-stu-id="902f4-107">However, the two processes must still have access to the same resource for some time, which is dependent on the listener type.</span></span> <span data-ttu-id="902f4-108">In questo caso, `XmlWriterTraceListener` crea un nuovo file di traccia per il secondo processo mentre Traccia eventi di Windows gestisce più processi nella stessa sessione e dà accesso allo stesso file.</span><span class="sxs-lookup"><span data-stu-id="902f4-108">In this case, , `XmlWriterTraceListener` creates a new trace file for the second process; while Windows event tracing manages multiple processes within the same session and gives access to the same file.</span></span> <span data-ttu-id="902f4-109">Se il listener personalizzato non fornisce funzionalità analoghe, è possibile che le tracce vadano perse quando il file è bloccato dai due processi.</span><span class="sxs-lookup"><span data-stu-id="902f4-109">If your own listener does not provide similar functionalities, traces can be lost when the file is locked up by the two processes.</span></span>  
  
 <span data-ttu-id="902f4-110">È inoltre importante tenere presente che un listener di traccia personalizzato può inviare tracce e messaggi in transito, ad esempio, a un database remoto.</span><span class="sxs-lookup"><span data-stu-id="902f4-110">You should also be aware that a custom trace listener can send traces and messages on the wire, for example, to a remote database.</span></span> <span data-ttu-id="902f4-111">Il distributore di applicazioni deve configurare listener personalizzati con il controllo di accesso appropriato.</span><span class="sxs-lookup"><span data-stu-id="902f4-111">As an application deployer, you should configure custom listeners with appropriate access control.</span></span> <span data-ttu-id="902f4-112">È inoltre necessario applicare un controllo di sicurezza a qualsiasi informazione personale potenzialmente esposta nel percorso remoto.</span><span class="sxs-lookup"><span data-stu-id="902f4-112">You should also apply security control on any personal information that can be exposed at the remote location.</span></span>  
  
## <a name="logging-sensitive-information"></a><span data-ttu-id="902f4-113">Registrazione di informazioni riservate</span><span class="sxs-lookup"><span data-stu-id="902f4-113">Logging Sensitive Information</span></span>  
 <span data-ttu-id="902f4-114">Le tracce contengono intestazioni di messaggio quando un messaggio è nell'ambito.</span><span class="sxs-lookup"><span data-stu-id="902f4-114">Traces contain message headers when a message is in scope.</span></span> <span data-ttu-id="902f4-115">Quando la funzionalità di traccia è abilitata, le informazioni personali contenute nelle intestazioni specifiche dell'applicazione, ad esempio una stringa di query, e le informazioni contenute nel corpo, ad esempio un numero di carta di credito, possono divenire visibili nei log.</span><span class="sxs-lookup"><span data-stu-id="902f4-115">When tracing is enabled, personal information in application-specific headers, such as, a query string; and body information, such as, a credit card number, can become visible in the logs.</span></span> <span data-ttu-id="902f4-116">Il distributore dell'applicazione è responsabile dell'attivazione del controllo di accesso nei file di configurazione e di traccia.</span><span class="sxs-lookup"><span data-stu-id="902f4-116">The application deployer is responsible for enforcing access control on the configuration and trace files.</span></span> <span data-ttu-id="902f4-117">Se non si desidera che questo tipo di informazioni sia visibile, è necessario disabilitare la traccia oppure filtrare parte dei dati se si intende condividere i log di traccia.</span><span class="sxs-lookup"><span data-stu-id="902f4-117">If you do not want this kind of information to be visible, you should disable tracing, or filter out part of the data if you want to share the trace logs.</span></span>  
  
 <span data-ttu-id="902f4-118">I suggerimenti seguenti consentono di impedire che il contenuto di un file di traccia venga esposto per errore:</span><span class="sxs-lookup"><span data-stu-id="902f4-118">The following tips can help you to prevent the content of a trace file from being exposed unintentionally:</span></span>  
  
- <span data-ttu-id="902f4-119">Accertarsi che i file di log siano protetti da elenchi di controllo di accesso (ACL, Access Control Lists) in scenari sia WebHost che indipendenti.</span><span class="sxs-lookup"><span data-stu-id="902f4-119">Ensure that the log files are protected by Access Control Lists (ACL) both in WebHost and self-host scenarios.</span></span>  
  
- <span data-ttu-id="902f4-120">Scegliere un'estensione di file che non sia troppo facilmente disponibile quando si utilizza una richiesta Web.</span><span class="sxs-lookup"><span data-stu-id="902f4-120">Choose a file extension that cannot be easily served using a Web request.</span></span> <span data-ttu-id="902f4-121">L'estensione xml, ad esempio, non è una scelta sicura.</span><span class="sxs-lookup"><span data-stu-id="902f4-121">For example, the .xml file extension is not a safe choice.</span></span> <span data-ttu-id="902f4-122">Per un elenco di estensioni disponibili, consultare il manuale dell'amministratore di IIS.</span><span class="sxs-lookup"><span data-stu-id="902f4-122">You can check the IIS administration guide to see a list of extensions that can be served.</span></span>  
  
- <span data-ttu-id="902f4-123">Specificare un percorso assoluto per il file di log, che non deve essere contenuto nella directory pubblica della radice virtuale di WebHost, per evitare che venga consultato da un interessato esterno mediante un browser Web.</span><span class="sxs-lookup"><span data-stu-id="902f4-123">Specify an absolute path for the log file location, which should be outside of the WebHost vroot public directory to prevent it from being accessed by an external party using a Web browser.</span></span>  
  
 <span data-ttu-id="902f4-124">Per impostazione predefinita, le chiavi e le informazioni personali, ad esempio nome utente e password, non sono registrate in tracce e messaggi registrati.</span><span class="sxs-lookup"><span data-stu-id="902f4-124">By default, keys and personally identifiable information (PII) such as username and password are not logged in traces and logged messages.</span></span> <span data-ttu-id="902f4-125">Un amministratore del computer, tuttavia, può utilizzare l'attributo `enableLoggingKnownPII` nell'elemento `machineSettings` del file Machine.config per consentire alle applicazioni in esecuzione sul computer di registrare informazioni personali note come segue:</span><span class="sxs-lookup"><span data-stu-id="902f4-125">A machine administrator, however, can use the `enableLoggingKnownPII` attribute in the `machineSettings` element of the Machine.config file to permit applications running on the machine to log known personally identifiable information (PII) as follows:</span></span>  
  
```xml  
<configuration>  
   <system.ServiceModel>  
      <machineSettings enableLoggingKnownPii="Boolean"/>  
   </system.ServiceModel>  
</configuration>
```  
  
 <span data-ttu-id="902f4-126">I distributori di applicazioni possono quindi utilizzare l'attributo `logKnownPii` nel file App.config o Web.config per abilitare la registrazione di informazioni personali come segue:</span><span class="sxs-lookup"><span data-stu-id="902f4-126">An application deployer can then use the `logKnownPii` attribute in either the App.config or Web.config file to enable PII logging as follows:</span></span>  
  
```xml  
<system.diagnostics>  
  <sources>  
      <source name="System.ServiceModel.MessageLogging"  
        logKnownPii="true">  
        <listeners>  
                 <add name="messages"  
                 type="System.Diagnostics.XmlWriterTraceListener"  
                 initializeData="c:\logs\messages.svclog" />  
          </listeners>  
      </source>  
  </sources>  
</system.diagnostics>  
```  
  
 <span data-ttu-id="902f4-127">La registrazione di informazioni personali viene abilitata solo quando entrambe le impostazioni sono `true`.</span><span class="sxs-lookup"><span data-stu-id="902f4-127">Only when both settings are `true` is PII logging enabled.</span></span> <span data-ttu-id="902f4-128">La combinazione di due opzioni consente la registrazione di informazioni personali note per ogni applicazione.</span><span class="sxs-lookup"><span data-stu-id="902f4-128">The combination of two switches allows the flexibility to log known PII for each application.</span></span>  
  
 <span data-ttu-id="902f4-129">Tenere presente che se si specificano due o più origini personalizzate in un file di configurazione, solo gli attributi della prima origine vengono letti.</span><span class="sxs-lookup"><span data-stu-id="902f4-129">You should be aware that if you specify two or more custom sources in a configuration file, only the attributes of the first source are read.</span></span> <span data-ttu-id="902f4-130">Gli altri vengono ignorati.</span><span class="sxs-lookup"><span data-stu-id="902f4-130">The others are ignored.</span></span> <span data-ttu-id="902f4-131">Questo implica che, per il file App.config seguente, le informazioni personali non vengono registrate per entrambe le origini anche se la registrazione di informazioni personali è abilitata in modo esplicito per la seconda origine.</span><span class="sxs-lookup"><span data-stu-id="902f4-131">This means that, for the following App.config, file, PII is not logged for both sources even though PII logging is explicitly enabled for the second source.</span></span>  
  
```xml  
<system.diagnostics>  
  <sources>  
      <source name="System.ServiceModel.MessageLogging"  
        logKnownPii="false">  
        <listeners>  
           <add name="messages"  
                type="System.Diagnostics.XmlWriterTraceListener"  
                initializeData="c:\logs\messages.svclog" />  
          </listeners>  
      </source>  
      <source name="System.ServiceModel"
         logKnownPii="true">  
         <listeners>  
            <add name="xml" />  
         </listeners>  
      </source>  
  </sources>  
</system.diagnostics>  
```  
  
 <span data-ttu-id="902f4-132">Se l'elemento `<machineSettings enableLoggingKnownPii="Boolean"/>` esiste al di fuori del file Machine.config, il sistema genera un'eccezione <xref:System.Configuration.ConfigurationErrorsException>.</span><span class="sxs-lookup"><span data-stu-id="902f4-132">If the `<machineSettings enableLoggingKnownPii="Boolean"/>` element exists outside the Machine.config file, the system throws a <xref:System.Configuration.ConfigurationErrorsException>.</span></span>  
  
 <span data-ttu-id="902f4-133">Le modifiche diventano effettive solo dopo l'avvio o il riavvio dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="902f4-133">The changes are effective only when the application starts or restarts.</span></span> <span data-ttu-id="902f4-134">Un evento viene registrato all'avvio quando entrambi gli attributi sono impostati su `true`.</span><span class="sxs-lookup"><span data-stu-id="902f4-134">An event is logged at startup when both attributes are set to `true`.</span></span> <span data-ttu-id="902f4-135">Un evento viene inoltre registrato se `logKnownPii` è impostato su `true` ma `enableLoggingKnownPii` è `false`.</span><span class="sxs-lookup"><span data-stu-id="902f4-135">An event is also logged if `logKnownPii` is set to `true` but `enableLoggingKnownPii` is `false`.</span></span>  
  
 <span data-ttu-id="902f4-136">Per altre informazioni sulla registrazione delle informazioni personali, vedere Esempio di [blocco di sicurezza delle informazioni personali.](../../../../../docs/framework/wcf/samples/pii-security-lockdown.md)</span><span class="sxs-lookup"><span data-stu-id="902f4-136">For more information on PII logging, see [PII Security Lockdown](../../../../../docs/framework/wcf/samples/pii-security-lockdown.md) sample.</span></span>  
  
 <span data-ttu-id="902f4-137">L'amministratore del computer e il distributore di applicazioni devono prestare molta attenzione durante l'utilizzo di queste due opzioni.</span><span class="sxs-lookup"><span data-stu-id="902f4-137">The machine administrator and application deployer should exercise extreme caution when using these two switches.</span></span> <span data-ttu-id="902f4-138">Se la registrazione di informazioni personali è abilitata, vengono registrate chiavi di sicurezza e informazioni personali.</span><span class="sxs-lookup"><span data-stu-id="902f4-138">If PII logging is enabled, security keys and PII are logged.</span></span> <span data-ttu-id="902f4-139">Se è disabilitata, i dati riservati e le informazioni specifiche dell'applicazione vengono comunque registrati nell'intestazione e nel corpo dei messaggi.</span><span class="sxs-lookup"><span data-stu-id="902f4-139">If it is disabled, sensitive and application-specific data is still logged in message headers and bodies.</span></span> <span data-ttu-id="902f4-140">Per una discussione più approfondita sulla privacy e sulla protezione delle informazioni personali dall'esposizione, vedere [Privacy degli](https://docs.microsoft.com/previous-versions/dotnet/articles/aa480490(v=msdn.10))utenti .</span><span class="sxs-lookup"><span data-stu-id="902f4-140">For a more thorough discussion on privacy and protecting PII from being exposed, see [User Privacy](https://docs.microsoft.com/previous-versions/dotnet/articles/aa480490(v=msdn.10)).</span></span>  
  
 <span data-ttu-id="902f4-141">L'indirizzo IP del mittente del messaggio, inoltre, viene registrato una volta per ogni connessione per trasporti orientati alla connessione e una volta per ogni messaggio inviato diversamente.</span><span class="sxs-lookup"><span data-stu-id="902f4-141">In addition, the IP address of the message sender is logged once per connection for connection-oriented transports, and once per message sent otherwise.</span></span> <span data-ttu-id="902f4-142">Ciò avviene senza il consenso del mittente.</span><span class="sxs-lookup"><span data-stu-id="902f4-142">This is done without the consent of the sender.</span></span> <span data-ttu-id="902f4-143">Questa registrazione, tuttavia, avviene solo ai livelli di traccia Informazioni o Dettagliato, ovvero i livelli non predefiniti né consigliati in produzione, tranne che per il debug attivo.</span><span class="sxs-lookup"><span data-stu-id="902f4-143">However, this logging only occurs at the Information or Verbose tracing levels, which are not the default or recommended tracing levels in production, except for live debugging.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="902f4-144">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="902f4-144">See also</span></span>

- [<span data-ttu-id="902f4-145">Traccia</span><span class="sxs-lookup"><span data-stu-id="902f4-145">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
