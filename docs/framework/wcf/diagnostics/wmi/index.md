---
title: Uso di Strumentazione gestione Windows (WMI) per la diagnostica
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fe48738d-e31b-454d-b5ec-24c85c6bf79a
caps.latest.revision: "24"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 0862f747cb969a6aa2e63d86e842097260e95b56
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="using-windows-management-instrumentation-for-diagnostics"></a><span data-ttu-id="44598-102">Uso di Strumentazione gestione Windows (WMI) per la diagnostica</span><span class="sxs-lookup"><span data-stu-id="44598-102">Using Windows Management Instrumentation for Diagnostics</span></span>
[!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)]<span data-ttu-id="44598-103"> espone dati di ispezione di un servizio in fase di esecuzione tramite un provider WMI di [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="44598-103"> exposes inspection data of a service at runtime through a [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] Windows Management Instrumentation (WMI) provider.</span></span>  
  
## <a name="enabling-wmi"></a><span data-ttu-id="44598-104">Abilitazione di WMI</span><span class="sxs-lookup"><span data-stu-id="44598-104">Enabling WMI</span></span>  
 <span data-ttu-id="44598-105">WMI è l'implementazione Microsoft dello standard WBEM (Web-Based Enterprise Management).</span><span class="sxs-lookup"><span data-stu-id="44598-105">WMI is Microsoft's implementation of the Web-Based Enterprise Management (WBEM) standard.</span></span> [!INCLUDE[crabout](../../../../../includes/crabout-md.md)]<span data-ttu-id="44598-106">il SDK di WMI, vedere [Strumentazione gestione Windows](https://msdn.microsoft.com/library/aa394582.aspx).</span><span class="sxs-lookup"><span data-stu-id="44598-106"> the WMI SDK, see [Windows Management Instrumentation](https://msdn.microsoft.com/library/aa394582.aspx).</span></span> <span data-ttu-id="44598-107">WBEM è uno standard industriale che definisce la modalità in cui le applicazioni espongono la strumentazione della gestione a strumenti di gestione esterni.</span><span class="sxs-lookup"><span data-stu-id="44598-107">WBEM is an industry standard for how applications expose management instrumentation to external management tools.</span></span>  
  
 <span data-ttu-id="44598-108">Un provider WMI è un componente che espone la strumentazione in fase di esecuzione attraverso un'interfaccia compatibile con WBEM.</span><span class="sxs-lookup"><span data-stu-id="44598-108">A WMI provider is a component that exposes instrumentation at runtime through a WBEM-compatible interface.</span></span> <span data-ttu-id="44598-109">È costituito da un set di oggetti WMI che hanno coppie di valore/attributo.</span><span class="sxs-lookup"><span data-stu-id="44598-109">It consists of a set of WMI objects that have attribute/value pairs.</span></span> <span data-ttu-id="44598-110">Le coppie possono essere costituite da un numero qualsiasi di tipi semplici.</span><span class="sxs-lookup"><span data-stu-id="44598-110">Pairs can be of a number of simple types.</span></span> <span data-ttu-id="44598-111">Gli strumenti di gestione sono in grado di connettersi ai servizi attraverso l'interfaccia in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="44598-111">Management tools can connect to the services through the interface at runtime.</span></span> [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)]<span data-ttu-id="44598-112"> espone attributi di servizi quali indirizzi, associazioni, comportamenti e listener.</span><span class="sxs-lookup"><span data-stu-id="44598-112"> exposes attributes of services such as addresses, bindings, behaviors, and listeners.</span></span>  
  
 <span data-ttu-id="44598-113">Il provider WMI incorporato può essere attivato nel file di configurazione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="44598-113">The built-in WMI provider can be activated in the configuration file of the application.</span></span> <span data-ttu-id="44598-114">Questa operazione viene eseguita tramite il `wmiProviderEnabled` attributo del [ \<diagnostica >](../../../../../docs/framework/configure-apps/file-schema/wcf/diagnostics.md) nel [ \<System. ServiceModel >](../../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md) sezione, come illustrato nell'esempio seguente configurazione.</span><span class="sxs-lookup"><span data-stu-id="44598-114">This is done through the `wmiProviderEnabled` attribute of the [\<diagnostics>](../../../../../docs/framework/configure-apps/file-schema/wcf/diagnostics.md) in the [\<system.serviceModel>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md) section, as shown in the following sample configuration.</span></span>  
  
```xml  
<system.serviceModel>  
    …  
    <diagnostics wmiProviderEnabled="true" />  
    …  
</system.serviceModel>  
```  
  
 <span data-ttu-id="44598-115">Questa voce di configurazione espone un'interfaccia WMI.</span><span class="sxs-lookup"><span data-stu-id="44598-115">This configuration entry exposes a WMI interface.</span></span> <span data-ttu-id="44598-116">Le applicazioni di gestione possono ora connettersi usando questa interfaccia e accedere la strumentazione di gestione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="44598-116">Management applications can now connect through this interface and access the management instrumentation of the application.</span></span>  
  
## <a name="accessing-wmi-data"></a><span data-ttu-id="44598-117">Accesso ai dati WMI</span><span class="sxs-lookup"><span data-stu-id="44598-117">Accessing WMI Data</span></span>  
 <span data-ttu-id="44598-118">L'accesso ai dati WMI può essere eseguito in molti modi diversi.</span><span class="sxs-lookup"><span data-stu-id="44598-118">WMI data can be accessed in many different ways.</span></span> <span data-ttu-id="44598-119">Microsoft fornisce API WMI per script, applicazioni [!INCLUDE[vbprvb](../../../../../includes/vbprvb-md.md)], applicazioni C++ e [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="44598-119">Microsoft provides WMI APIs for scripts, [!INCLUDE[vbprvb](../../../../../includes/vbprvb-md.md)] applications, C++ applications, and the [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)].</span></span> <span data-ttu-id="44598-120">Per ulteriori informazioni, vedere [mediante WMI](http://go.microsoft.com/fwlink/?LinkId=95183).</span><span class="sxs-lookup"><span data-stu-id="44598-120">For more information, see [Using WMI](http://go.microsoft.com/fwlink/?LinkId=95183).</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="44598-121">Se si usano i metodi forniti da .NET Framework per accedere ai dati WMI a livello di programmazione, tenere presente che questi metodi possono generare eccezioni nel momento in cui viene stabilita la connessione.</span><span class="sxs-lookup"><span data-stu-id="44598-121">If you use the .NET Framework provided methods to programmatically access WMI data, you should be aware that such methods may throw exceptions when the connection is established.</span></span> <span data-ttu-id="44598-122">La connessione non viene stabilita durante la costruzione dell'istanza <xref:System.Management.ManagementObject>, ma alla prima richiesta che comporta uno scambio di dati effettivo.</span><span class="sxs-lookup"><span data-stu-id="44598-122">The connection is not established during the construction of the <xref:System.Management.ManagementObject> instance, but on the first request involving actual data exchange.</span></span> <span data-ttu-id="44598-123">Per intercettare le possibili eccezioni è pertanto necessario usare un blocco `try..catch`.</span><span class="sxs-lookup"><span data-stu-id="44598-123">Therefore, you should use a `try..catch` block to catch the possible exceptions.</span></span>  
  
 <span data-ttu-id="44598-124">Per l'origine di traccia `System.ServiceModel` in WMI è possibile modificare il livello di registrazione della traccia e del messaggio, nonché le opzioni di registrazione dei messaggi.</span><span class="sxs-lookup"><span data-stu-id="44598-124">You can change the trace and message logging level, as well as message logging options for the `System.ServiceModel` trace source in WMI.</span></span> <span data-ttu-id="44598-125">Questa operazione può essere eseguita accedendo il [AppDomainInfo](../../../../../docs/framework/wcf/diagnostics/wmi/appdomaininfo.md) istanza, che espone le proprietà booleane: `LogMessagesAtServiceLevel`, `LogMessagesAtTransportLevel`, `LogMalformedMessages`, e `TraceLevel`.</span><span class="sxs-lookup"><span data-stu-id="44598-125">This can be done by accessing the [AppDomainInfo](../../../../../docs/framework/wcf/diagnostics/wmi/appdomaininfo.md) instance, which exposes these Boolean properties: `LogMessagesAtServiceLevel`, `LogMessagesAtTransportLevel`, `LogMalformedMessages`, and `TraceLevel`.</span></span> <span data-ttu-id="44598-126">Pertanto, se si configura un listener di traccia per la registrazione dei messaggi, ma si impostano queste opzioni su `false` nella configurazione, è possibile in seguito modificarle in `true` quando l'applicazione è in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="44598-126">Therefore, if you configure a trace listener for message logging, but set these options to `false` in configuration, you can later change them to `true` when the application is running.</span></span> <span data-ttu-id="44598-127">In questo modo verrà abilitata la registrazione dei messaggi a runtime.</span><span class="sxs-lookup"><span data-stu-id="44598-127">This will effectively enable message logging at runtime.</span></span> <span data-ttu-id="44598-128">Analogamente, se si abilita la registrazione dei messaggi nel file di configurazione, è possibile disabilitarla al runtime usando WMI.</span><span class="sxs-lookup"><span data-stu-id="44598-128">Similarly, if you enable message logging in your configuration file, you can disable it at runtime using WMI.</span></span>  
  
 <span data-ttu-id="44598-129">Se nel file di configurazione non viene specificato alcun listener di traccia per la registrazione dei messaggi né alcun listener di traccia `System.ServiceModel`, nessuna delle modifiche apportate verrà resa effettiva, anche se accettata da WMI.</span><span class="sxs-lookup"><span data-stu-id="44598-129">You should be aware that if no message logging trace listeners for message logging, or no `System.ServiceModel` trace listeners for tracing are specified in the configuration file, none of your changes are taken into effect, even though the changes are accepted by WMI.</span></span> <span data-ttu-id="44598-130">Per ulteriori informazioni sulla corretta configurazione dei rispettivi listener, vedere [la configurazione di registrazione dei messaggi](../../../../../docs/framework/wcf/diagnostics/configuring-message-logging.md) e [configurazione traccia](../../../../../docs/framework/wcf/diagnostics/tracing/configuring-tracing.md).</span><span class="sxs-lookup"><span data-stu-id="44598-130">For more information on properly setting up the respective listeners, see [Configuring Message Logging](../../../../../docs/framework/wcf/diagnostics/configuring-message-logging.md) and [Configuring Tracing](../../../../../docs/framework/wcf/diagnostics/tracing/configuring-tracing.md).</span></span> <span data-ttu-id="44598-131">Il livello di traccia di tutte le altre origini di traccia specificate dalla configurazione viene attivato all'avvio dell'applicazione e non può essere modificato.</span><span class="sxs-lookup"><span data-stu-id="44598-131">The trace level of all other trace sources specified by configuration is effective when the application starts, and cannot be changed.</span></span>  
  
 [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)]<span data-ttu-id="44598-132"> espone un metodo `GetOperationCounterInstanceName` per lo scripting.</span><span class="sxs-lookup"><span data-stu-id="44598-132"> exposes a `GetOperationCounterInstanceName` method for scripting.</span></span> <span data-ttu-id="44598-133">Se al metodo viene fornito un nome operazione, il metodo restituisce il nome di un'istanza di contatore delle prestazioni.</span><span class="sxs-lookup"><span data-stu-id="44598-133">This method returns a performance counter instance name if you provide it with an operation name.</span></span> <span data-ttu-id="44598-134">L'input non viene tuttavia convalidato.</span><span class="sxs-lookup"><span data-stu-id="44598-134">However, it does not validate your input.</span></span> <span data-ttu-id="44598-135">Pertanto, se si fornisce un nome operazione errato, verrà restituito un nome di contatore errato.</span><span class="sxs-lookup"><span data-stu-id="44598-135">Therefore, if you provide an incorrect operation name, an incorrect counter name is returned.</span></span>  
  
 <span data-ttu-id="44598-136">La proprietà `OutgoingChannel` dell'istanza `Service` non conta i canali aperti da un servizio per la connessione a un altro servizio se il client [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] nel servizio di destinazione non viene creato all'interno del metodo `Service`.</span><span class="sxs-lookup"><span data-stu-id="44598-136">The `OutgoingChannel` property of the `Service` instance does not count channels opened by a service to connect to another service, if the [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] client to the destination service is not created within the `Service` method.</span></span>  
  
 <span data-ttu-id="44598-137">**Attenzione** WMI supporta solo un <xref:System.TimeSpan> valore fino a 3 cifre decimali.</span><span class="sxs-lookup"><span data-stu-id="44598-137">**Caution** WMI only supports a <xref:System.TimeSpan> value up to 3 decimal points.</span></span> <span data-ttu-id="44598-138">Ad esempio, se il servizio imposta una delle proprietà su <xref:System.TimeSpan.MaxValue>, quando viene visualizzato in WMI il valore viene troncato dopo 3 cifre decimali.</span><span class="sxs-lookup"><span data-stu-id="44598-138">For example, if your service sets one of its properties to <xref:System.TimeSpan.MaxValue>, its value is truncated after 3 decimal points when viewed through WMI.</span></span>  
  
## <a name="security"></a><span data-ttu-id="44598-139">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="44598-139">Security</span></span>  
 <span data-ttu-id="44598-140">Poiché il provider WMI di [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] consente la rilevazione di servizi in un ambiente, nel concedere l'accesso all'ambiente è necessario prestare particolare attenzione.</span><span class="sxs-lookup"><span data-stu-id="44598-140">Because the [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] WMI provider allows the discovery of services in an environment, you should exercise extreme caution for granting access to it.</span></span> <span data-ttu-id="44598-141">Se si consentono deroghe all'accesso al solo amministratore (impostazione predefinita), è possibile che l'accesso a dati sensibili presenti nell'ambiente sia consentito anche a utenti meno attendibili.</span><span class="sxs-lookup"><span data-stu-id="44598-141">If you relax the default administrator-only access, you may allow less-trusted parties access to sensitive data in your environment.</span></span> <span data-ttu-id="44598-142">In particolare, se le autorizzazioni all'accesso WMI remoto vengono concesse indistintamente, possono verificarsi attacchi flood.</span><span class="sxs-lookup"><span data-stu-id="44598-142">Specifically, if you loosen permissions on remote WMI access, flooding attacks can occur.</span></span> <span data-ttu-id="44598-143">Se un processo viene sovraccaricato da un numero eccessivo di richieste WMI, è possibile che si verifichi una riduzione delle prestazioni.</span><span class="sxs-lookup"><span data-stu-id="44598-143">If a process is flooded by excessive WMI requests, its performance can be degraded.</span></span>  
  
 <span data-ttu-id="44598-144">Inoltre, se si concedono liberamente autorizzazioni di accesso al file MOF, utenti meno attendibili potrebbero modificare il comportamento di WMI e alterare gli oggetti caricati nello schema WMI.</span><span class="sxs-lookup"><span data-stu-id="44598-144">In addition, if you relax access permissions for the MOF file, less-trusted parties can manipulate the behavior of WMI and alter the objects that are loaded in the WMI schema.</span></span> <span data-ttu-id="44598-145">È possibile ad esempio rimuovere campi in modo che i dati critici vengano nascosti dall'amministratore o che i campi che non contengono o generano eccezioni vengano aggiunti al file.</span><span class="sxs-lookup"><span data-stu-id="44598-145">For example, fields can be removed such that critical data is concealed from the administrator or that fields that do not populate or cause exceptions are added to the file.</span></span>  
  
 <span data-ttu-id="44598-146">Per impostazione predefinita, il provider WMI di [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] concede le autorizzazioni "esegui metodo", "scrittura provider" e "abilita account" per l'amministratore e l'autorizzazione "abilita account" per ASP.NET, Servizio locale e Servizio di rete.</span><span class="sxs-lookup"><span data-stu-id="44598-146">By default, the [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] WMI provider grants "execute method", "provider write", and "enable account" permission for Administrator, and "enable account" permission for ASP.NET, Local Service and Network Service.</span></span> <span data-ttu-id="44598-147">In particolare, sulle piattaforme diverse da [!INCLUDE[wv](../../../../../includes/wv-md.md)] l'account ASP.NET dispone dell'accesso in lettura allo spazio dei nomi ServiceModel di WMI.</span><span class="sxs-lookup"><span data-stu-id="44598-147">In particular, on non-[!INCLUDE[wv](../../../../../includes/wv-md.md)] platforms, the ASP.NET account has read access to the WMI ServiceModel namespace.</span></span> <span data-ttu-id="44598-148">Se non si desidera concedere questi privilegi a un particolare gruppo di utenti, è necessario disattivare il provider WMI (è disabilitato per impostazione predefinita) o disabilitare l'accesso per il gruppo di utenti specifico.</span><span class="sxs-lookup"><span data-stu-id="44598-148">If you do not want to grant these privileges to a particular user group, you should either deactivate the WMI provider (it is disabled by default), or disable access for the specific user group.</span></span>  
  
 <span data-ttu-id="44598-149">Inoltre, l'abilitazione di WMI mediante la configurazione potrebbe non essere possibile a causa di privilegi utente insufficienti.</span><span class="sxs-lookup"><span data-stu-id="44598-149">In addition, when you attempt to enable WMI through configuration, WMI may not be enabled due to insufficient user privilege.</span></span> <span data-ttu-id="44598-150">Per questo errore non viene tuttavia scritto alcun evento nel registro eventi.</span><span class="sxs-lookup"><span data-stu-id="44598-150">However, no event is written to the event log to record this failure.</span></span>  
  
 <span data-ttu-id="44598-151">Per modificare i livelli dei privilegi utente, usare la procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="44598-151">To modify user privilege levels, use the following steps.</span></span>  
  
1.  <span data-ttu-id="44598-152">Fare clic su Start e quindi Esegui e digitare **compmgmt.msc**.</span><span class="sxs-lookup"><span data-stu-id="44598-152">Click Start and then Run and type **compmgmt.msc**.</span></span>  
  
2.  <span data-ttu-id="44598-153">Fare doppio clic su **servizi e applicazioni/controllo WMI** selezionare **proprietà**.</span><span class="sxs-lookup"><span data-stu-id="44598-153">Right-click **Services and Application/WMI Controls** to select **Properties**.</span></span>  
  
3.  <span data-ttu-id="44598-154">Selezionare il **sicurezza** scheda e passare al **Root/ServiceModel** dello spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="44598-154">Select the **Security** Tab, and navigate to the **Root/ServiceModel** namespace.</span></span> <span data-ttu-id="44598-155">Fare clic su di **sicurezza** pulsante.</span><span class="sxs-lookup"><span data-stu-id="44598-155">Click the **Security** button.</span></span>  
  
4.  <span data-ttu-id="44598-156">Selezionare il gruppo o utente specifico che si desidera controllare l'accesso e utilizzare il **Consenti** o **Deny** casella di controllo per configurare le autorizzazioni.</span><span class="sxs-lookup"><span data-stu-id="44598-156">Select the specific group or user that you want to control access and use the **Allow** or **Deny** checkbox to configure permissions.</span></span>  
  
## <a name="granting-wcf-wmi-registration-permissions-to-additional-users"></a><span data-ttu-id="44598-157">Concessione di autorizzazioni di registrazione WMI per WCF a utenti aggiuntivi</span><span class="sxs-lookup"><span data-stu-id="44598-157">Granting WCF WMI Registration Permissions to Additional Users</span></span>  
 <span data-ttu-id="44598-158">WCF espone dati di gestione a WMI.</span><span class="sxs-lookup"><span data-stu-id="44598-158">WCF exposes management data to WMI.</span></span> <span data-ttu-id="44598-159">Tale scopo, ospita un provider WMI in-process, talvolta denominato "provider disaccoppiato".</span><span class="sxs-lookup"><span data-stu-id="44598-159">It does so by hosting an in-process WMI provider, sometimes called a "decoupled provider".</span></span> <span data-ttu-id="44598-160">Per l'esposizione dei dati di gestione, l'account che registra il provider deve disporre di autorizzazioni appropriate.</span><span class="sxs-lookup"><span data-stu-id="44598-160">For the management data to be exposed, the account that registers this provider must have the appropriate permissions.</span></span> <span data-ttu-id="44598-161">Per impostazione predefinita, in Windows solo un set ridotto di account privilegiati può registrare provider disaccoppiati.</span><span class="sxs-lookup"><span data-stu-id="44598-161">In Windows, only a small set of privileged accounts can register decoupled providers by default.</span></span> <span data-ttu-id="44598-162">Ciò costituisce un problema, in quanto gli utenti desiderano in genere esporre dati WMI da un servizio WCF in esecuzione con un account non incluso nel set predefinito.</span><span class="sxs-lookup"><span data-stu-id="44598-162">This is a problem because users commonly want to expose WMI data from a WCF service running under an account that is not in the default set.</span></span>  
  
 <span data-ttu-id="44598-163">Per fornire tale accesso, un amministratore deve concedere le autorizzazioni seguenti all'account aggiuntivo nell'ordine indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="44598-163">To provide this access, an administrator must grant the following permissions to the additional account in the following order:</span></span>  
  
1.  <span data-ttu-id="44598-164">Autorizzazione per accedere allo spazio dei nomi WMI per WCF.</span><span class="sxs-lookup"><span data-stu-id="44598-164">Permission to access to the WCF WMI Namespace.</span></span>  
  
2.  <span data-ttu-id="44598-165">Autorizzazione per registrare il provider disaccoppiato WMI per WCF.</span><span class="sxs-lookup"><span data-stu-id="44598-165">Permission to register the WCF Decoupled WMI Provider.</span></span>  
  
#### <a name="to-grant-wmi-namespace-access-permission"></a><span data-ttu-id="44598-166">Per concedere l'autorizzazione di accesso allo spazio dei nomi WMI</span><span class="sxs-lookup"><span data-stu-id="44598-166">To grant WMI namespace access permission</span></span>  
  
1.  <span data-ttu-id="44598-167">Eseguire lo script PowerShell seguente.</span><span class="sxs-lookup"><span data-stu-id="44598-167">Run the following PowerShell script.</span></span>  
  
    ```powershell  
    write-host ""  
    write-host "Granting Access to root/servicemodel WMI namespace to built in users group"  
    write-host ""  
  
    # Create the binary representation of the permissions to grant in SDDL  
    $newPermissions = "O:BAG:BAD:P(A;CI;CCDCLCSWRPWPRCWD;;;BA)(A;CI;CC;;;NS)(A;CI;CC;;;LS)(A;CI;CC;;;BU)"  
    $converter = new-object system.management.ManagementClass Win32_SecurityDescriptorHelper  
    $binarySD = $converter.SDDLToBinarySD($newPermissions)  
    $convertedPermissions = ,$binarySD.BinarySD  
  
    # Get the object used to set the permissions  
    $security = gwmi -namespace root/servicemodel -class __SystemSecurity  
  
    # Get and output the current settings  
    $binarySD = @($null)  
    $result = $security.PsBase.InvokeMethod("GetSD",$binarySD)  
  
    $outsddl = $converter.BinarySDToSDDL($binarySD[0])  
    write-host "Previous ACL: "$outsddl.SDDL  
  
    # Change the Access Control List (ACL) using SDDL  
    $result = $security.PsBase.InvokeMethod("SetSD",$convertedPermissions)   
  
    # Get and output the current settings  
    $binarySD = @($null)  
    $result = $security.PsBase.InvokeMethod("GetSD",$binarySD)  
  
    $outsddl = $converter.BinarySDToSDDL($binarySD[0])  
    write-host "New ACL:      "$outsddl.SDDL  
    write-host ""  
    ```  
  
     <span data-ttu-id="44598-168">Questo script di PowerShell Usa definizione linguaggio SDDL (Security Descriptor) per concedere l'accesso al gruppo Users predefinito allo spazio dei nomi WMI "root/servicemodel".</span><span class="sxs-lookup"><span data-stu-id="44598-168">This PowerShell script uses Security Descriptor Definition Language (SDDL) to grant the Built-In Users group access to the "root/servicemodel" WMI namespace.</span></span> <span data-ttu-id="44598-169">Lo script specifica gli ACL seguenti:</span><span class="sxs-lookup"><span data-stu-id="44598-169">It specifies the following ACLs:</span></span>  
  
    -   <span data-ttu-id="44598-170">Account Administrator predefinito: dispone già di accesso.</span><span class="sxs-lookup"><span data-stu-id="44598-170">Built-In Administrator (BA) - Already Had Access.</span></span>  
  
    -   <span data-ttu-id="44598-171">Servizio di rete: dispone già di accesso.</span><span class="sxs-lookup"><span data-stu-id="44598-171">Network Service (NS) - Already Had Access.</span></span>  
  
    -   <span data-ttu-id="44598-172">Sistema locale: dispone già di accesso.</span><span class="sxs-lookup"><span data-stu-id="44598-172">Local System (LS) - Already Had Access.</span></span>  
  
    -   <span data-ttu-id="44598-173">Gruppo Users predefinito: gruppo a cui concedere l'accesso.</span><span class="sxs-lookup"><span data-stu-id="44598-173">Built-In Users - The group to grant access to.</span></span>  
  
#### <a name="to-grant-provider-registration-access"></a><span data-ttu-id="44598-174">Per concedere accesso alla registrazione del provider</span><span class="sxs-lookup"><span data-stu-id="44598-174">To grant provider registration access</span></span>  
  
1.  <span data-ttu-id="44598-175">Eseguire lo script PowerShell seguente.</span><span class="sxs-lookup"><span data-stu-id="44598-175">Run the following PowerShell script.</span></span>  
  
    ```powershell  
    write-host ""  
    write-host "Granting WCF provider registration access to built in users group"  
    write-host ""  
    # Set security on ServiceModel provider  
    $provider = get-WmiObject -namespace "root\servicemodel" __Win32Provider  
  
    write-host "Previous ACL: "$provider.SecurityDescriptor  
    $result = $provider.SecurityDescriptor = "O:BUG:BUD:(A;;0x1;;;BA)(A;;0x1;;;NS)(A;;0x1;;;LS)(A;;0x1;;;BU)"  
  
    # Commit the changes and display it to the console  
    $result = $provider.Put()  
    write-host "New ACL:      "$provider.SecurityDescriptor  
    write-host ""  
    ```  
  
### <a name="granting-access-to-arbitrary-users-or-groups"></a><span data-ttu-id="44598-176">Concessione dell'accesso a utenti o gruppi arbitrari</span><span class="sxs-lookup"><span data-stu-id="44598-176">Granting Access to Arbitrary Users or Groups</span></span>  
 <span data-ttu-id="44598-177">Nell'esempio contenuto in questa sezione vengono concessi privilegi di registrazione del provider WMI a tutti gli utenti locali.</span><span class="sxs-lookup"><span data-stu-id="44598-177">The example in this section grants WMI Provider registration privileges to all local users.</span></span> <span data-ttu-id="44598-178">Se si desidera concedere l'accesso a un utente o un gruppo non predefinito, è necessario ottenere l'ID di sicurezza (SID) dell'utente o del gruppo.</span><span class="sxs-lookup"><span data-stu-id="44598-178">If you want to grant access to a user or group that is not built in, then you must obtain that user or group’s Security Identifier (SID).</span></span> <span data-ttu-id="44598-179">Non è possibile ottenere il SID di un utente arbitrario in modo semplice.</span><span class="sxs-lookup"><span data-stu-id="44598-179">There is no simple way to get the SID for an arbitrary user.</span></span> <span data-ttu-id="44598-180">Un metodo consiste nell'accedere come utente desiderato e quindi eseguire il comando shell seguente.</span><span class="sxs-lookup"><span data-stu-id="44598-180">One method is to log on as the desired user and then issue the following shell command.</span></span>  
  
```  
Whoami /user  
```  
  
 <span data-ttu-id="44598-181">In questo modo, è possibile ottenere il SID dell'utente corrente, ma non è possibile usare tale metodo per ottenere il SID per utenti arbitrari.</span><span class="sxs-lookup"><span data-stu-id="44598-181">This provides the SID of the current user, but this method cannot be used to get the SID on any arbitrary user.</span></span> <span data-ttu-id="44598-182">Un altro metodo per ottenere il SID consiste nell'utilizzare il [getsid.exe](http://go.microsoft.com/fwlink/?LinkId=186467) dello strumento di [strumenti di Windows 2000 Resource Kit per attività amministrative](http://go.microsoft.com/fwlink/?LinkId=178660).</span><span class="sxs-lookup"><span data-stu-id="44598-182">Another method to get the SID is to use the [getsid.exe](http://go.microsoft.com/fwlink/?LinkId=186467) tool from the [Windows 2000 Resource Kit Tools for administrative tasks](http://go.microsoft.com/fwlink/?LinkId=178660).</span></span> <span data-ttu-id="44598-183">Questo strumento confronta il SID di due utenti (locale o di dominio) e, come conseguenza secondaria, stampa i due SID nella riga di comando.</span><span class="sxs-lookup"><span data-stu-id="44598-183">This tool compares the SID of two users (local or domain), and as a side effect prints the two SIDs to the command line.</span></span> [!INCLUDE[crdefault](../../../../../includes/crdefault-md.md)]<span data-ttu-id="44598-184">[SID noto](http://go.microsoft.com/fwlink/?LinkId=186468).</span><span class="sxs-lookup"><span data-stu-id="44598-184"> [Well Known SIDs](http://go.microsoft.com/fwlink/?LinkId=186468).</span></span>  
  
## <a name="accessing-remote-wmi-object-instances"></a><span data-ttu-id="44598-185">Accesso a istanze di oggetti WMI remote</span><span class="sxs-lookup"><span data-stu-id="44598-185">Accessing Remote WMI Object Instances</span></span>  
 <span data-ttu-id="44598-186">Per accedere a istanze WMI di [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] in un computer remoto, è necessario abilitare la riservatezza pacchetto negli strumenti usati per l'accesso.</span><span class="sxs-lookup"><span data-stu-id="44598-186">If you need to access [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] WMI instances on a remote machine, you must enable packet privacy on the tools that you use for access.</span></span> <span data-ttu-id="44598-187">Nella sezione seguente viene descritta la procedura per accedere a istanze WMI usando WMI CIM Studio, Tester di Strumentazione gestione Windows e .NET SDK 2.0.</span><span class="sxs-lookup"><span data-stu-id="44598-187">The following section describes how to achieve these using the WMI CIM Studio, Windows Management Instrumentation Tester, as well as .NET SDK 2.0.</span></span>  
  
### <a name="wmi-cim-studio"></a><span data-ttu-id="44598-188">WMI CIM Studio</span><span class="sxs-lookup"><span data-stu-id="44598-188">WMI CIM Studio</span></span>  
 <span data-ttu-id="44598-189">Se è stato installato [WMI Administrative Tools](http://go.microsoft.com/fwlink/?LinkId=95185), è possibile usare WMI CIM Studio per accedere alle istanze WMI.</span><span class="sxs-lookup"><span data-stu-id="44598-189">If you have installed [WMI Administrative Tools](http://go.microsoft.com/fwlink/?LinkId=95185), you can use the WMI CIM Studio to access WMI instances.</span></span> <span data-ttu-id="44598-190">Gli strumenti si trovano nella cartella seguente:</span><span class="sxs-lookup"><span data-stu-id="44598-190">The tools are in the following folder</span></span>  
  
 <span data-ttu-id="44598-191">**Strumenti Files\WMI %windir%\Programmi\File\\**</span><span class="sxs-lookup"><span data-stu-id="44598-191">**%windir%\Program Files\WMI Tools\\**</span></span>  
  
1.  <span data-ttu-id="44598-192">Nel **Connetti allo spazio dei nomi:** finestra **root\ServiceModel** e fare clic su **OK.**</span><span class="sxs-lookup"><span data-stu-id="44598-192">In the **Connect to namespace:** window, type **root\ServiceModel** and click **OK.**</span></span>  
  
2.  <span data-ttu-id="44598-193">Nel **WMI CIM Studio Login** finestra, fare clic su di **Opzioni >>** pulsante per espandere la finestra.</span><span class="sxs-lookup"><span data-stu-id="44598-193">In the **WMI CIM Studio Login** window, click the **Options >>** button to expand the window.</span></span> <span data-ttu-id="44598-194">Selezionare **riservatezza pacchetto** per **livello di autenticazione**, fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="44598-194">Select **Packet privacy** for **Authentication level**, and click **OK**.</span></span>  
  
### <a name="windows-management-instrumentation-tester"></a><span data-ttu-id="44598-195">Tester di Strumentazione gestione Windows</span><span class="sxs-lookup"><span data-stu-id="44598-195">Windows Management Instrumentation Tester</span></span>  
 <span data-ttu-id="44598-196">Questo strumento viene installato da Windows.</span><span class="sxs-lookup"><span data-stu-id="44598-196">This tool is installed by Windows.</span></span> <span data-ttu-id="44598-197">Per eseguirlo, avviare una console dei comandi digitando **cmd.exe** nel **Start/Esegui** la finestra di dialogo e fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="44598-197">To run it, launch a command console by typing **cmd.exe** in the **Start/Run** dialog box and click **OK**.</span></span> <span data-ttu-id="44598-198">Digitare quindi **wbemtest.exe** nella finestra di comando.</span><span class="sxs-lookup"><span data-stu-id="44598-198">Then, type **wbemtest.exe** in the command window.</span></span> <span data-ttu-id="44598-199">Lo strumento Tester di Strumentazione gestione Windows viene avviato.</span><span class="sxs-lookup"><span data-stu-id="44598-199">The Windows Management Instrumentation Tester tool is then launched.</span></span>  
  
1.  <span data-ttu-id="44598-200">Fare clic su di **Connetti** pulsante nell'angolo superiore destro della finestra.</span><span class="sxs-lookup"><span data-stu-id="44598-200">Click the **Connect** button on the top right corner of the window.</span></span>  
  
2.  <span data-ttu-id="44598-201">Nella nuova finestra immettere **root\ServiceModel** per il **Namespace** campo e selezionare **riservatezza pacchetto** per **livello di autenticazione**.</span><span class="sxs-lookup"><span data-stu-id="44598-201">In the new window, enter **root\ServiceModel** for the **Namespace** field, and select **Packet privacy** for **Authentication level**.</span></span> <span data-ttu-id="44598-202">Fare clic su **Connetti**.</span><span class="sxs-lookup"><span data-stu-id="44598-202">Click **Connect**.</span></span>  
  
### <a name="using-managed-code"></a><span data-ttu-id="44598-203">Uso di codice gestito</span><span class="sxs-lookup"><span data-stu-id="44598-203">Using Managed Code</span></span>  
 <span data-ttu-id="44598-204">Per accedere a istanze WMI remote a livello di programmazione è anche possibile usare le classi fornite dallo spazio dei nomi <xref:System.Management>.</span><span class="sxs-lookup"><span data-stu-id="44598-204">You can also access remote WMI instances programmatically by using classes provided by the <xref:System.Management> namespace.</span></span> <span data-ttu-id="44598-205">Nell'esempio di codice seguente viene illustrato come eseguire questa procedura.</span><span class="sxs-lookup"><span data-stu-id="44598-205">The following code sample demonstrates how to do this.</span></span>  
  
```  
String wcfNamespace = String.Format(@"\\{0}\Root\ServiceModel",      
   this.serviceMachineName);  
  
ConnectionOptions connection = new ConnectionOptions();  
connection.Authentication = AuthenticationLevel.PacketPrivacy;  
ManagementScope scope = new ManagementScope(this.wcfNamespace, connection);  
```
