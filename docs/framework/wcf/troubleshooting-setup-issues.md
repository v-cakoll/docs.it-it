---
title: Risoluzione dei problemi di installazione
ms.date: 03/30/2017
ms.assetid: 1644f885-c408-4d5f-a5c7-a1a907bc8acd
ms.openlocfilehash: 2cd9ced4f0780b1a6f63e4a5833e20ac91870121
ms.sourcegitcommit: 43cbde34970f5f38f30c43cd63b9c7e2e83717ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/11/2020
ms.locfileid: "81121587"
---
# <a name="troubleshoot-setup-issues"></a>Risolvere i problemi di installazione

In questo articolo viene descritto come risolvere i problemi di impostazione di Windows Communication Foundation (WCF).  
  
## <a name="some-windows-communication-foundation-registry-keys-are-not-repaired-by-performing-an-msi-repair-operation-on-the-net-framework-30"></a>Alcune chiavi del Registro di sistema di Windows Communication Foundation non vengono ripristinate eseguendo un'operazione di ripristino MSI in .NET Framework 3.0  
 Se si elimina una delle chiavi di Registro seguenti:  
  
- HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\ServiceModelService 3.0.0.0  
  
- HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\ServiceModelOperation 3.0.0.0  
  
- HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\ServiceModelEndpoint 3.0.0.0  
  
- HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\SMSvcHost 3.0.0.0  
  
- HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\MSDTC Bridge 3.0.0.0  
  
 Le chiavi non vengono ricreate se si esegue il ripristino utilizzando il programma di installazione di .NET Framework 3.0 avviato dall'applet **Installazione applicazioni** nel Pannello **di controllo.** Per ricreare correttamente queste chiavi, l'utente deve disinstallare e reinstallare .NET Framework 3.0.  
  
## <a name="wmi-service-corruption-blocks-installation-of-the-windows-communication-foundation-wmi-provider-during-installation-of-net-framework-30-package"></a>Il danneggiamento del servizio WMI blocca l'installazione del provider WMI per Windows Communication Foundation durante l'installazione del pacchetto .NET Framework 3.0  
 È possibile che, a causa del danneggiamento del servizio WMI, l'installazione del provider WMI per Windows Communication Foundation venga bloccata. Durante l'installazione il programma di installazione di Windows Communication Foundation non è in grado di registrare il file WCF con estensione mof mediante il componente mofcomp.exe. Di seguito è riportato un elenco di sintomi:  
  
1. L'installazione di .NET Framework 3.0 viene completata correttamente, ma il provider WMI per WCF non viene registrato.  
  
2. Nel registro eventi dell'applicazione viene visualizzato un evento di errore che fa riferimento a problemi durante la registrazione del provider WMI per WCF o l'esecuzione di mofcomp.exe.  
  
3. Il file di log dell'installazione denominato dd_wcf_retCA* nella directory %temp% dell'utente contiene riferimenti all'impossibilità di registrare il provider WMI per WCF.  
  
4. È possibile che nel registro eventi o nel file di log sia elencata un'eccezione simile a una delle seguenti:  
  
     ServiceModelReg [11:09:59:046]: System.ApplicationException: Risultato imprevisto 3 durante l'esecuzione di E:\WINDOWS\system32\wbem\mofcomp.exe con "E:\WINDOWS\Microsoft.NET\Framework\v3.0\Windows Communication Foundation\ServiceModel.mof"  
  
     oppure:  
  
     ServiceModelReg [07:19:33:843]: System.TypeInitializationException: L'inizializzatore di tipo di 'System.Management.ManagementPath' ha generato un'eccezione. ---> System.Runtime.InteropServices.COMException (0x80040154): recupero della class factory COM per il componente con CLSID - CF4CC405-E2C5-4DDD-B3CE-5E7582D8C9FA non riuscito a causa del seguente errore: 80040154.  
  
     oppure:  
  
     ServiceModelReg [07:19:32:750]: System.IO.FileNotFoundException: Impossibile caricare il file o l'assembly 'C:\WINDOWS\system32\wbem\mofcomp.exe' o una delle relative dipendenze. Non è possibile trovare il file specificato.  
  
     Nome file: 'C:\WINDOWS\system32\wbem\mofcomp.exe  
  
 Per risolvere il problema descritto in precedenza, è necessario eseguire la procedura seguente.  
  
1. Eseguire WMI [Diagnosis Utility](https://www.microsoft.com/download/details.aspx?id=7684) per ripristinare il servizio WMI. Per ulteriori informazioni sull'utilizzo di questo strumento, vedere [Utilità di diagnosi WMI](https://docs.microsoft.com/previous-versions/tn-archive/ff404265(v%3dmsdn.10)).  
  
 Ripristinare l'installazione di .NET Framework 3.0 utilizzando l'applet **Installazione applicazioni** disponibile nel Pannello **di controllo**oppure disinstallare/reinstallare .NET Framework 3.0.  
  
## <a name="repairing-net-framework-30-after-net-framework-35-installation-removes-configuration-elements-introduced-by-net-framework-35-in-machineconfig"></a>Il ripristino di .NET Framework 3.0 in seguito all'installazione di .NET Framework 3.5 rimuove gli elementi di configurazione introdotti da .NET Framework 3.5 nel file machine.config  
 Se si esegue un ripristino di .NET Framework 3.0 dopo l'installazione di .NET Framework 3.5, gli elementi di configurazione introdotti da .NET Framework 3.5 in machine.config vengono rimossi. Tuttavia, la config web rimane invariata. La soluzione consiste nel ripristinare .NET Framework 3.5 dopo questo tramite ARP o utilizzare lo `/c` strumento di registrazione del [servizio WorkFlow (WFServicesReg.exe)](workflow-service-registration-tool-wfservicesreg-exe.md) con l'opzione.  
  
 Lo strumento di registrazione del [servizio WorkFlow (WFServicesReg.exe)](workflow-service-registration-tool-wfservicesreg-exe.md) è disponibile in %windir%  
  
## <a name="configure-iis-properly-for-wcfwf-webhost-after-installing-net-framework-35"></a>Configurare IIS correttamente per WCF/WF Webhost dopo aver installato .NET Framework 3.5  
 Quando l'installazione di .NET Framework 3.5 non riesce a configurare ulteriori impostazioni di configurazione di IIS correlate a WCF, registra un errore nel log di installazione e continua. Qualsiasi tentativo di eseguire applicazioni WorkflowServices avrà esito negativo in quanto le impostazioni di configurazione richieste risultano mancanti. Ad esempio, il caricamento di xoml o del servizio regole potrebbe avere esito negativo.  
  
 Per risolvere questo problema, utilizzare lo strumento di registrazione del `/c` servizio [WorkFlow (WFServicesReg.exe)](workflow-service-registration-tool-wfservicesreg-exe.md) con l'opzione per configurare correttamente i mapping di script IIS nel computer. Lo strumento di registrazione del [servizio WorkFlow (WFServicesReg.exe)](workflow-service-registration-tool-wfservicesreg-exe.md) è disponibile in %windir%  
  
## <a name="could-not-load-type-systemservicemodelactivationhttpmodule-from-assembly-systemservicemodel-version-3000-cultureneutral-publickeytokenb77a5c561934e089"></a>Impossibile caricare il tipo 'System.ServiceModel.Activation.HttpModule' dall'assembly 'System.ServiceModel, versione 3.0.0.0, Culture 'neutral, PublicKeyToken'b77a5c561934e089'  
 Questo errore si verifica se è installato .NET Framework 4 e quindi è abilitata l'attivazione HTTP WCF. Per risolvere il problema, eseguire la seguente riga di comando dall'interno del prompt dei comandi per gli sviluppatori per Visual Studio:  
  
```console
aspnet_regiis.exe -i -enable  
```  
  
## <a name="see-also"></a>Vedere anche

- [Istruzioni per la configurazione](./samples/set-up-instructions.md)
