---
title: Strumento di registrazione dei servizi di Windows Workflow (WFServicesReg.exe)
ms.date: 03/30/2017
ms.assetid: 9e92c87b-99c5-4e8d-9d53-7944cc2b47d3
ms.openlocfilehash: cf5ea345c900dec0e4859d81fcb272c1ba3d3df6
ms.sourcegitcommit: a4f9b754059f0210e29ae0578363a27b9ba84b64
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/05/2019
ms.locfileid: "74837753"
---
# <a name="workflow-service-registration-tool-wfservicesregexe"></a>Strumento di registrazione dei servizi di Windows Workflow (WFServicesReg.exe)
Lo strumento di registrazione dei servizi di Windows Workflow (WFServicesReg.exe) è un strumento autonomo che può essere utilizzato per aggiungere, rimuovere o ripristinare gli elementi di configurazione per i servizi Windows Workflow Foundation (WF).  
  
## <a name="syntax"></a>Sintassi  
  
```console  
WFServicesReg.exe [-c | -r | -v | -m | -i]  
```  
  
## <a name="remarks"></a>Note  
 Lo strumento si trova nel percorso di installazione di .NET Framework 3,5, in particolare%windir%\Microsoft.NET\Framework\v3.5 o in%windir%\Microsoft.NET\Framework64\v3.5 in computer a 64 bit.  
  
 Nelle tabelle riportate di seguito vengono illustrate le opzioni che è possibile utilizzare con lo strumento di registrazione dei servizi di Windows Workflow.  
  
|Opzione|Descrizione|  
|------------|-----------------|  
|`/c`|Configura i servizi di Windows Workflow. Utilizzato in scenari di installazione e ripristino.|  
|`/r`|Rimuove la configurazione dei servizi di Windows Workflow.|  
|`/v`|Stampare informazioni dettagliate (per configurazione o rimozione).|  
|`/m`|Abilita formato di registrazione di MSI.|  
|`/i`|Riduce a icona la finestra durante l' esecuzione dell'applicazione.|  
  
## <a name="registration"></a>Registrazione  
 Lo strumento controlla il file Web.config e registra gli elementi seguenti:  
  
- .NET Framework 3,5 assembly di riferimento.  
  
- Provider di compilazione per i file .xoml.  
  
- Gestori HTTP per .xoml e file .rules.  
  
 Lo strumento controlla il file Machine.config e registra le estensioni seguenti:  
  
- behaviorExtensions  
  
- bindingElementExtensions  
  
- bindingExtensions  
  
 Lo strumento regista inoltre le utilità di importazione dei metadati client seguenti:  
  
- policyImporters  
  
- wsdlImporters  
  
 Lo strumento registra inoltre scriptmap e gestori .xoml e .rules nella metabase IIS.  
  
 Nei computer [!INCLUDE[ws2003](../../../includes/ws2003-md.md)] e [!INCLUDE[wxp](../../../includes/wxp-md.md)] (IIS 5,1 e IIS 6,0), viene registrato un set di scriptmap. xoml e. Rules.  
  
 In computer a 64 bit lo strumento registra scriptmap di modalità WOW, se l'opzione `Enable32BitAppOnWin64` è abilitata, o scriptmap a 64 bit nativi, se l'opzione `Enable32BitAppOnWin64` è disabilitata.  
  
 Nei computer con Windows Vista e Windows Server 2008 (IIS 7,0 e versioni successive) sono registrati due set di gestori xoml e Rules: uno per la modalità integrata e uno per la modalità classica.  
  
 In computer a 64 bit sono registrati tre set di gestori (indipendentemente dallo stato dell'opzione `Enable32BitAppOnWin64`): uno per la modalità integrata, uno per la modalità classica WOW e uno per la modalità classica a 64 bit nativa.  
  
> [!NOTE]
> A differenza di ServiceModelreg.exe, WFServicesReg.exe non consente di aggiungere, rimuovere o ripristinare scriptmap o gestori per un particolare sito Web. Per una soluzione alternativa a questo problema, vedere la sezione "Ripristino di scriptmap".  
  
## <a name="usage-scenarios"></a>Utilizzo di scenari  
  
### <a name="installing-iis-after-net-framework-35-is-installed"></a>Installazione di IIS dopo l'installazione di .NET Framework 3.5  
 In un computer [!INCLUDE[ws2003](../../../includes/ws2003-md.md)], .NET Framework 3,5 viene installato prima dell'installazione di IIS. A causa dell'indisponibilità della metabase IIS, l'installazione di .NET Framework 3,5 riesce senza installare gli scriptmap. xoml e. Rules.  
  
 Al termine dell'installazione di IIS, è possibile utilizzare lo strumento WFServicesReg.exe con l'opzione `/c` per installare questi scriptmap specifici.  
  
### <a name="repairing-the-scriptmaps"></a>Ripristino di scriptmap  
  
#### <a name="scriptmap-deleted-under-web-sites-node"></a>Eliminazione di scriptmap nel nodo Siti Web  
 In un computer con sistema [!INCLUDE[ws2003](../../../includes/ws2003-md.md)], .xoml o .rules viene accidentalmente eliminato dal nodo Siti Web. Può essere ripristinato eseguendo lo strumento WFServicesReg.exe con l'opzione `/c`.  
  
#### <a name="scriptmap-deleted-under-a-particular-web-site"></a>Eliminazione di scriptmap in un particolare sito Web  
 In un computer con sistema [!INCLUDE[ws2003](../../../includes/ws2003-md.md)], .xoml o .rules viene accidentalmente eliminato da un particolare sito Web (ad esempio il sito Web predefinito) piuttosto che dal nodo Siti Web.  
  
 Per ripristinare i gestori eliminati per un particolare sito Web, è necessario eseguire "WFServicesReg. exe/r" per rimuovere i gestori da tutti i siti Web, quindi eseguire "WFServicesReg. exe/c" per creare i gestori appropriati per tutti i siti Web.  
  
### <a name="configuring-handlers-after-switching-iis-mode"></a>Configurazione dei gestori dopo il cambio di modalità di IIS  
 Quando IIS è in modalità di configurazione condivisa e viene installato .NET Framework 3,5, la metabase IIS viene configurata in un percorso condiviso. Se si passa IIS a una modalità di configurazione non-condivisa, la metabase locale non conterrà i gestori necessari. Per configurare correttamente la metabase locale, è possibile importare la metabase condivisa in locale oppure eseguire "WFServicesReg. exe/c", che configura la metabase locale.
