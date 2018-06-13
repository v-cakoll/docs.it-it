---
title: Risoluzione dei problemi di installazione
ms.date: 03/30/2017
ms.assetid: 1644f885-c408-4d5f-a5c7-a1a907bc8acd
ms.openlocfilehash: 3c750aa4f9a4ec4750aa24ffcd685c9c349a45a7
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/07/2018
ms.locfileid: "33806513"
---
# <a name="troubleshooting-setup-issues"></a>Risoluzione dei problemi di installazione
In questo argomento viene descritto come risolvere i problemi di installazione Windows Communication Foundation (WCF).  
  
## <a name="some-windows-communication-foundation-registry-keys-are-not-repaired-by-performing-an-msi-repair-operation-on-the-net-framework-30"></a>Alcune chiavi del Registro di sistema di Windows Communication Foundation non vengono ripristinate eseguendo un'operazione di ripristino MSI in .NET Framework 3.0  
 Se si elimina una delle chiavi di Registro seguenti:  
  
-   HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\ServiceModelService 3.0.0.0  
  
-   HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\ServiceModelOperation 3.0.0.0  
  
-   HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\ServiceModelEndpoint 3.0.0.0  
  
-   HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\SMSvcHost 3.0.0.0  
  
-   HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\MSDTC Bridge 3.0.0.0  
  
 Le chiavi non vengono ricreate se il ripristino viene eseguito tramite il programma di installazione di .NET Framework 3.0 avviato dal **Aggiungi/Rimuovi programmi** applet **Pannello di controllo**. Per ricreare correttamente queste chiavi, l'utente deve disinstallare e reinstallare .NET Framework 3.0.  
  
## <a name="wmi-service-corruption-blocks-installation-of-the-windows-communication-foundation-wmi-provider-during-installation-of-net-framework-30-package"></a>Il danneggiamento del servizio WMI blocca l'installazione del provider WMI per Windows Communication Foundation durante l'installazione del pacchetto .NET Framework 3.0  
 È possibile che, a causa del danneggiamento del servizio WMI, l'installazione del provider WMI per Windows Communication Foundation venga bloccata. Durante l'installazione il programma di installazione di Windows Communication Foundation non è in grado di registrare il file WCF con estensione mof mediante il componente mofcomp.exe. Di seguito è riportato un elenco di sintomi:  
  
1.  L'installazione di .NET Framework 3.0 viene completata correttamente, ma il provider WMI per WCF non viene registrato.  
  
2.  Nel registro eventi dell'applicazione viene visualizzato un evento di errore che fa riferimento a problemi durante la registrazione del provider WMI per WCF o l'esecuzione di mofcomp.exe.  
  
3.  Il file di log dell'installazione denominato dd_wcf_retCA* nella directory %temp% dell'utente contiene riferimenti all'impossibilità di registrare il provider WMI per WCF.  
  
4.  È possibile che nel registro eventi o nel file di log sia elencata un'eccezione simile a una delle seguenti:  
  
     ServiceModelReg [11:09:59:046]: System.ApplicationException: Risultato imprevisto 3 durante l'esecuzione di E:\WINDOWS\system32\wbem\mofcomp.exe con "E:\WINDOWS\Microsoft.NET\Framework\v3.0\Windows Communication Foundation\ServiceModel.mof"  
  
     oppure:  
  
     ServiceModelReg [07:19:33:843]: System.TypeInitializationException: L'inizializzatore di tipo di 'System.Management.ManagementPath' ha generato un'eccezione. ---> System.Runtime.InteropServices.COMException (0x80040154): Recupero della class factory COM per il componente con CLSID {CF4CC405-E2C5-4DDD-B3CE-5E7582D8C9FA} non riuscito a causa del seguente errore: 80040154.  
  
     oppure:  
  
     ServiceModelReg [07:19:32:750]: System.IO.FileNotFoundException: Impossibile caricare il file o l'assembly 'C:\WINDOWS\system32\wbem\mofcomp.exe' o una delle relative dipendenze. Impossibile trovare il file specificato.  
  
     Nome file: 'C:\WINDOWS\system32\wbem\mofcomp.exe  
  
 Per risolvere il problema descritto in precedenza, è necessario eseguire la procedura seguente.  
  
1.  Eseguire [WMI Diagnosis Utility, versione 2.0](http://go.microsoft.com/fwlink/?LinkId=94685) per ripristinare il servizio WMI. Per ulteriori informazioni sull'utilizzo di questo strumento, vedere la [utilità WMI Diagnosis Utility](http://go.microsoft.com/fwlink/?LinkId=94686) argomento.  
  
 Ripristinare l'installazione di .NET Framework 3.0 utilizzando il **Aggiungi/Rimuovi programmi** applet si trova **Pannello di controllo**, o disinstallare/reinstallare .NET Framework 3.0.  
  
## <a name="repairing-net-framework-30-after-net-framework-35-installation-removes-configuration-elements-introduced-by-net-framework-35-in-machineconfig"></a>Il ripristino di .NET Framework 3.0 in seguito all'installazione di .NET Framework 3.5 rimuove gli elementi di configurazione introdotti da .NET Framework 3.5 nel file machine.config  
 Il ripristino di .NET Framework 3.0 in seguito all'installazione di [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)], gli elementi di configurazione introdotti da [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)] nel file machine.config vengono rimossi. Tuttavia, la config web rimane invariata. La soluzione consiste nel ripristinare [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)] in seguito tramite ARP, oppure utilizzare il [strumento di registrazione del servizio di WorkFlow (WFServicesReg.exe)](../../../docs/framework/wcf/workflow-service-registration-tool-wfservicesreg-exe.md) con il `/c` passare.  
  
 [Strumento di registrazione del servizio del flusso di lavoro (WFServicesReg.exe)](../../../docs/framework/wcf/workflow-service-registration-tool-wfservicesreg-exe.md) è reperibile in %windir%\Microsoft.NET\framework\v3.5\ o %windir%\Microsoft.NET\framework64\v3.5\  
  
## <a name="configure-iis-properly-for-wcfwf-webhost-after-installing-net-framework-35"></a>Configurare IIS correttamente per WCF/WF Webhost dopo aver installato .NET Framework 3.5  
 Quando [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)] installazione non riesce a configurare le impostazioni di configurazione aggiuntive di IIS correlate a WCF, registra un errore nel log di installazione e continua. Qualsiasi tentativo di eseguire applicazioni WorkflowServices avrà esito negativo in quanto le impostazioni di configurazione richieste risultano mancanti. Ad esempio, il caricamento di xoml o del servizio regole potrebbe avere esito negativo.  
  
 Per risolvere questo problema, utilizzare il [strumento di registrazione del servizio di WorkFlow (WFServicesReg.exe)](../../../docs/framework/wcf/workflow-service-registration-tool-wfservicesreg-exe.md) con il `/c` commutatore per configurare correttamente il mapping di script IIS nel computer. [Strumento di registrazione del servizio del flusso di lavoro (WFServicesReg.exe)](../../../docs/framework/wcf/workflow-service-registration-tool-wfservicesreg-exe.md) è reperibile in %windir%\Microsoft.NET\framework\v3.5\ o %windir%\Microsoft.NET\framework64\v3.5\  
  
## <a name="could-not-load-type-systemservicemodelactivationhttpmodule-from-assembly-systemservicemodel-version-3000-cultureneutral-publickeytokenb77a5c561934e089"></a>Impossibile caricare il tipo ‘System.ServiceModel.Activation.HttpModule’ dall'assembly ‘System.ServiceModel, Version 3.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089’  
 Questo errore si verifica se [!INCLUDE[netfx40_short](../../../includes/netfx40-short-md.md)] sia installato e quindi Attivazione HTTP WCF è abilitata. Per risolvere il problema eseguire la riga di comando seguente dal prompt dei comandi di [!INCLUDE[vs2010](../../../includes/vs2010-md.md)]:  
  
```Output  
aspnet_regiis.exe -i -enable  
```  
  
## <a name="see-also"></a>Vedere anche  
 [Istruzioni di configurazione](../../../docs/framework/wcf/samples/set-up-instructions.md)
