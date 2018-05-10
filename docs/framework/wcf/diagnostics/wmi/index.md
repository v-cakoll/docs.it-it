---
title: Uso di Strumentazione gestione Windows (WMI) per la diagnostica
ms.date: 03/30/2017
ms.assetid: fe48738d-e31b-454d-b5ec-24c85c6bf79a
ms.openlocfilehash: 3b06cc61714b3fdc63086d2b79b087540bece698
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/07/2018
---
# <a name="using-windows-management-instrumentation-for-diagnostics"></a>Uso di Strumentazione gestione Windows (WMI) per la diagnostica
Windows Communication Foundation (WCF) espone dati di ispezione di un servizio in fase di esecuzione tramite un provider di Strumentazione gestione Windows (WMI) di WCF.  
  
## <a name="enabling-wmi"></a>Abilitazione di WMI  
 WMI è l'implementazione Microsoft dello standard WBEM (Web-Based Enterprise Management). Per ulteriori informazioni sul SDK di WMI, vedere [Strumentazione gestione Windows](https://msdn.microsoft.com/library/aa394582.aspx). WBEM è uno standard industriale che definisce la modalità in cui le applicazioni espongono la strumentazione della gestione a strumenti di gestione esterni.  
  
 Un provider WMI è un componente che espone la strumentazione in fase di esecuzione attraverso un'interfaccia compatibile con WBEM. È costituito da un set di oggetti WMI che hanno coppie di valore/attributo. Le coppie possono essere costituite da un numero qualsiasi di tipi semplici. Gli strumenti di gestione sono in grado di connettersi ai servizi attraverso l'interfaccia in fase di esecuzione. WCF espone attributi di servizi quali indirizzi, associazioni, comportamenti e listener.  
  
 Il provider WMI incorporato può essere attivato nel file di configurazione dell'applicazione. Questa operazione viene eseguita tramite il `wmiProviderEnabled` attributo del [ \<diagnostica >](../../../../../docs/framework/configure-apps/file-schema/wcf/diagnostics.md) nel [ \<System. ServiceModel >](../../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md) sezione, come illustrato nell'esempio seguente configurazione.  
  
```xml  
<system.serviceModel>  
    …  
    <diagnostics wmiProviderEnabled="true" />  
    …  
</system.serviceModel>  
```  
  
 Questa voce di configurazione espone un'interfaccia WMI. Le applicazioni di gestione possono ora connettersi usando questa interfaccia e accedere la strumentazione di gestione dell'applicazione.  
  
## <a name="accessing-wmi-data"></a>Accesso ai dati WMI  
 L'accesso ai dati WMI può essere eseguito in molti modi diversi. Microsoft fornisce le API di WMI per gli script, le applicazioni Visual Basic, applicazioni C++ e [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)]. Per ulteriori informazioni, vedere [mediante WMI](http://go.microsoft.com/fwlink/?LinkId=95183).  
  
> [!CAUTION]
>  Se si usano i metodi forniti da .NET Framework per accedere ai dati WMI a livello di programmazione, tenere presente che questi metodi possono generare eccezioni nel momento in cui viene stabilita la connessione. La connessione non viene stabilita durante la costruzione dell'istanza <xref:System.Management.ManagementObject>, ma alla prima richiesta che comporta uno scambio di dati effettivo. Per intercettare le possibili eccezioni è pertanto necessario usare un blocco `try..catch`.  
  
 Per l'origine di traccia `System.ServiceModel` in WMI è possibile modificare il livello di registrazione della traccia e del messaggio, nonché le opzioni di registrazione dei messaggi. Questa operazione può essere eseguita accedendo il [AppDomainInfo](../../../../../docs/framework/wcf/diagnostics/wmi/appdomaininfo.md) istanza, che espone le proprietà booleane: `LogMessagesAtServiceLevel`, `LogMessagesAtTransportLevel`, `LogMalformedMessages`, e `TraceLevel`. Pertanto, se si configura un listener di traccia per la registrazione dei messaggi, ma si impostano queste opzioni su `false` nella configurazione, è possibile in seguito modificarle in `true` quando l'applicazione è in esecuzione. In questo modo verrà abilitata la registrazione dei messaggi a runtime. Analogamente, se si abilita la registrazione dei messaggi nel file di configurazione, è possibile disabilitarla al runtime usando WMI.  
  
 Se nel file di configurazione non viene specificato alcun listener di traccia per la registrazione dei messaggi né alcun listener di traccia `System.ServiceModel`, nessuna delle modifiche apportate verrà resa effettiva, anche se accettata da WMI. Per ulteriori informazioni sulla corretta configurazione dei rispettivi listener, vedere [la configurazione di registrazione dei messaggi](../../../../../docs/framework/wcf/diagnostics/configuring-message-logging.md) e [configurazione traccia](../../../../../docs/framework/wcf/diagnostics/tracing/configuring-tracing.md). Il livello di traccia di tutte le altre origini di traccia specificate dalla configurazione viene attivato all'avvio dell'applicazione e non può essere modificato.  
  
 WCF espone un `GetOperationCounterInstanceName` metodo per lo scripting. Se al metodo viene fornito un nome operazione, il metodo restituisce il nome di un'istanza di contatore delle prestazioni. L'input non viene tuttavia convalidato. Pertanto, se si fornisce un nome operazione errato, verrà restituito un nome di contatore errato.  
  
 Il `OutgoingChannel` proprietà del `Service` istanza non conta i canali aperti da un servizio per connettersi a un altro servizio, se il client WCF al servizio di destinazione non viene creato all'interno di `Service` (metodo).  
  
 **Attenzione** WMI supporta soltanto un <xref:System.TimeSpan> valore fino a 3 cifre decimali. Ad esempio, se il servizio imposta una delle proprietà su <xref:System.TimeSpan.MaxValue>, quando viene visualizzato in WMI il valore viene troncato dopo 3 cifre decimali.  
  
## <a name="security"></a>Sicurezza  
 Poiché il provider WMI per WCF consente l'individuazione dei servizi in un ambiente, si deve prestare molta attenzione per concedere l'accesso a esso. Se si consentono deroghe all'accesso al solo amministratore (impostazione predefinita), è possibile che l'accesso a dati sensibili presenti nell'ambiente sia consentito anche a utenti meno attendibili. In particolare, se le autorizzazioni all'accesso WMI remoto vengono concesse indistintamente, possono verificarsi attacchi flood. Se un processo viene sovraccaricato da un numero eccessivo di richieste WMI, è possibile che si verifichi una riduzione delle prestazioni.  
  
 Inoltre, se si concedono liberamente autorizzazioni di accesso al file MOF, utenti meno attendibili potrebbero modificare il comportamento di WMI e alterare gli oggetti caricati nello schema WMI. È possibile ad esempio rimuovere campi in modo che i dati critici vengano nascosti dall'amministratore o che i campi che non contengono o generano eccezioni vengano aggiunti al file.  
  
 Per impostazione predefinita, il provider WMI per WCF concede "Esegui metodo", "Scrittura provider", "Abilita account" autorizzazioni di amministratore e "Abilita account" per ASP.NET, servizio locale e servizio di rete. In particolare, sulle piattaforme diverse da [!INCLUDE[wv](../../../../../includes/wv-md.md)] l'account ASP.NET dispone dell'accesso in lettura allo spazio dei nomi ServiceModel di WMI. Se non si desidera concedere questi privilegi a un particolare gruppo di utenti, è necessario disattivare il provider WMI (è disabilitato per impostazione predefinita) o disabilitare l'accesso per il gruppo di utenti specifico.  
  
 Inoltre, l'abilitazione di WMI mediante la configurazione potrebbe non essere possibile a causa di privilegi utente insufficienti. Per questo errore non viene tuttavia scritto alcun evento nel registro eventi.  
  
 Per modificare i livelli dei privilegi utente, usare la procedura seguente:  
  
1.  Fare clic su Start e quindi Esegui e digitare **compmgmt.msc**.  
  
2.  Fare doppio clic su **servizi e applicazioni/controllo WMI** selezionare **proprietà**.  
  
3.  Selezionare il **sicurezza** scheda e passare al **Root/ServiceModel** dello spazio dei nomi. Fare clic su di **sicurezza** pulsante.  
  
4.  Selezionare il gruppo o utente specifico che si desidera controllare l'accesso e utilizzare il **Consenti** o **Deny** casella di controllo per configurare le autorizzazioni.  
  
## <a name="granting-wcf-wmi-registration-permissions-to-additional-users"></a>Concessione di autorizzazioni di registrazione WMI per WCF a utenti aggiuntivi  
 WCF espone dati di gestione a WMI. Tale scopo, ospita un provider WMI in-process, talvolta denominato "provider disaccoppiato". Per l'esposizione dei dati di gestione, l'account che registra il provider deve disporre di autorizzazioni appropriate. Per impostazione predefinita, in Windows solo un set ridotto di account privilegiati può registrare provider disaccoppiati. Ciò costituisce un problema, in quanto gli utenti desiderano in genere esporre dati WMI da un servizio WCF in esecuzione con un account non incluso nel set predefinito.  
  
 Per fornire tale accesso, un amministratore deve concedere le autorizzazioni seguenti all'account aggiuntivo nell'ordine indicato di seguito:  
  
1.  Autorizzazione per accedere allo spazio dei nomi WMI per WCF.  
  
2.  Autorizzazione per registrare il provider disaccoppiato WMI per WCF.  
  
#### <a name="to-grant-wmi-namespace-access-permission"></a>Per concedere l'autorizzazione di accesso allo spazio dei nomi WMI  
  
1.  Eseguire lo script PowerShell seguente.  
  
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
  
     Questo script di PowerShell Usa definizione linguaggio SDDL (Security Descriptor) per concedere l'accesso al gruppo Users predefinito allo spazio dei nomi WMI "root/servicemodel". Lo script specifica gli ACL seguenti:  
  
    -   Account Administrator predefinito: dispone già di accesso.  
  
    -   Servizio di rete: dispone già di accesso.  
  
    -   Sistema locale: dispone già di accesso.  
  
    -   Gruppo Users predefinito: gruppo a cui concedere l'accesso.  
  
#### <a name="to-grant-provider-registration-access"></a>Per concedere accesso alla registrazione del provider  
  
1.  Eseguire lo script PowerShell seguente.  
  
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
  
### <a name="granting-access-to-arbitrary-users-or-groups"></a>Concessione dell'accesso a utenti o gruppi arbitrari  
 Nell'esempio contenuto in questa sezione vengono concessi privilegi di registrazione del provider WMI a tutti gli utenti locali. Se si desidera concedere l'accesso a un utente o un gruppo non predefinito, è necessario ottenere l'ID di sicurezza (SID) dell'utente o del gruppo. Non è possibile ottenere il SID di un utente arbitrario in modo semplice. Un metodo consiste nell'accedere come utente desiderato e quindi eseguire il comando shell seguente.  
  
```  
Whoami /user  
```  
  
 In questo modo, è possibile ottenere il SID dell'utente corrente, ma non è possibile usare tale metodo per ottenere il SID per utenti arbitrari. Un altro metodo per ottenere il SID consiste nell'utilizzare il [getsid.exe](http://go.microsoft.com/fwlink/?LinkId=186467) dello strumento di [strumenti di Windows 2000 Resource Kit per attività amministrative](http://go.microsoft.com/fwlink/?LinkId=178660). Questo strumento confronta il SID di due utenti (locale o di dominio) e, come conseguenza secondaria, stampa i due SID nella riga di comando. Per altre informazioni, vedere [SID Well Known](http://go.microsoft.com/fwlink/?LinkId=186468).  
  
## <a name="accessing-remote-wmi-object-instances"></a>Accesso a istanze di oggetti WMI remote  
 Se è necessario per accedere a istanze WMI per WCF in un computer remoto, è necessario abilitare riservatezza pacchetto negli strumenti utilizzati per l'accesso. Nella sezione seguente viene descritta la procedura per accedere a istanze WMI usando WMI CIM Studio, Tester di Strumentazione gestione Windows e .NET SDK 2.0.  
  
### <a name="wmi-cim-studio"></a>WMI CIM Studio  
 Se è stato installato [WMI Administrative Tools](http://go.microsoft.com/fwlink/?LinkId=95185), è possibile usare WMI CIM Studio per accedere alle istanze WMI. Gli strumenti si trovano nella cartella seguente:  
  
 **Strumenti Files\WMI %windir%\Programmi\File\\**  
  
1.  Nel **Connetti allo spazio dei nomi:** finestra, digitare **root\ServiceModel** e fare clic su **OK.**  
  
2.  Nel **WMI CIM Studio Login** finestra, fare clic su di **Opzioni >>** pulsante per espandere la finestra. Selezionare **riservatezza pacchetto** per **livello di autenticazione**, fare clic su **OK**.  
  
### <a name="windows-management-instrumentation-tester"></a>Tester di Strumentazione gestione Windows  
 Questo strumento viene installato da Windows. Per eseguirlo, avviare una console dei comandi digitando **cmd.exe** nel **Start/Esegui** la finestra di dialogo e fare clic su **OK**. Digitare quindi **wbemtest.exe** nella finestra di comando. Lo strumento Tester di Strumentazione gestione Windows viene avviato.  
  
1.  Fare clic su di **Connetti** pulsante nell'angolo superiore destro della finestra.  
  
2.  Nella nuova finestra immettere **root\ServiceModel** per il **Namespace** campo e selezionare **riservatezza pacchetto** per **livello di autenticazione**. Fare clic su **Connetti**.  
  
### <a name="using-managed-code"></a>Uso di codice gestito  
 Per accedere a istanze WMI remote a livello di programmazione è anche possibile usare le classi fornite dallo spazio dei nomi <xref:System.Management>. Nell'esempio di codice seguente viene illustrato come eseguire questa procedura.  
  
```  
String wcfNamespace = String.Format(@"\\{0}\Root\ServiceModel",      
   this.serviceMachineName);  
  
ConnectionOptions connection = new ConnectionOptions();  
connection.Authentication = AuthenticationLevel.PacketPrivacy;  
ManagementScope scope = new ManagementScope(this.wcfNamespace, connection);  
```
