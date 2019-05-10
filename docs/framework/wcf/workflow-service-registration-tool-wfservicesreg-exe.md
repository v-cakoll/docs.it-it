---
title: Strumento di registrazione dei servizi di Windows Workflow (WFServicesReg.exe)
ms.date: 03/30/2017
ms.assetid: 9e92c87b-99c5-4e8d-9d53-7944cc2b47d3
ms.openlocfilehash: da377e865258169bdca16cfb0db3f8612d4e0f0d
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64613046"
---
# <a name="workflow-service-registration-tool-wfservicesregexe"></a>Strumento di registrazione dei servizi di Windows Workflow (WFServicesReg.exe)
Lo strumento di registrazione dei servizi di Windows Workflow (WFServicesReg.exe) è un strumento autonomo che può essere utilizzato per aggiungere, rimuovere o ripristinare gli elementi di configurazione per i servizi Windows Workflow Foundation (WF).  
  
## <a name="syntax"></a>Sintassi  
  
```  
WFServicesReg.exe [-c | -r | -v | -m | -i]  
```  
  
## <a name="remarks"></a>Note  
 Lo strumento si trova nel percorso di installazione di [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)], in modo specifico, %windir%\Microsoft.NET\Framework\v3.5, o %windir%\Microsoft.NET\Framework64\v3.5 in computer a 64 bit.  
  
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
  
- Assembly di riferimento di [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)].  
  
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
  
 In computer con sistema [!INCLUDE[ws2003](../../../includes/ws2003-md.md)] e [!INCLUDE[wxp](../../../includes/wxp-md.md)] (IIS 5.1 e [!INCLUDE[iis601](../../../includes/iis601-md.md)]), è registrato un set di scriptmap .xoml e .rules.  
  
 In computer a 64 bit lo strumento registra scriptmap di modalità WOW, se l'opzione `Enable32BitAppOnWin64` è abilitata, o scriptmap a 64 bit nativi, se l'opzione `Enable32BitAppOnWin64` è disabilitata.  
  
 In [!INCLUDE[wv](../../../includes/wv-md.md)] e Windows Server 2008 (IIS 7.0 e versioni successive) registrate macchine, due set di gestori xoml e. Rules: uno per la modalità integrata e uno per la modalità classica.  
  
 In computer a 64 bit sono registrati tre set di gestori (indipendentemente dallo stato dell'opzione `Enable32BitAppOnWin64`): uno per la modalità integrata, uno per la modalità classica WOW e uno per la modalità classica a 64 bit nativa.  
  
> [!NOTE]
>  A differenza di ServiceModelreg.exe, WFServicesReg.exe non consente di aggiungere, rimuovere o ripristinare scriptmap o gestori per un particolare sito Web. Per una soluzione alternativa a questo problema, vedere la sezione "Ripristino di scriptmap".  
  
## <a name="usage-scenarios"></a>Utilizzo di scenari  
  
### <a name="installing-iis-after-net-framework-35-is-installed"></a>Installazione di IIS dopo l'installazione di .NET Framework 3.5  
 In un computer con sistema [!INCLUDE[ws2003](../../../includes/ws2003-md.md)], [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)] viene installato prima dell'installazione di IIS. A causa dell'indisponibilità della metabase IIS, l'installazione di [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)] viene completata senza installare scriptmap .xoml e .rules.  
  
 Al termine dell'installazione di IIS, è possibile utilizzare lo strumento WFServicesReg.exe con l'opzione `/c` per installare questi scriptmap specifici.  
  
### <a name="repairing-the-scriptmaps"></a>Ripristino di scriptmap  
  
#### <a name="scriptmap-deleted-under-web-sites-node"></a>Eliminazione di scriptmap nel nodo Siti Web  
 In un computer con sistema [!INCLUDE[ws2003](../../../includes/ws2003-md.md)], .xoml o .rules viene accidentalmente eliminato dal nodo Siti Web. Può essere ripristinato eseguendo lo strumento WFServicesReg.exe con l'opzione `/c`.  
  
#### <a name="scriptmap-deleted-under-a-particular-web-site"></a>Eliminazione di scriptmap in un particolare sito Web  
 In un computer con sistema [!INCLUDE[ws2003](../../../includes/ws2003-md.md)], .xoml o .rules viene accidentalmente eliminato da un particolare sito Web (ad esempio il sito Web predefinito) piuttosto che dal nodo Siti Web.  
  
 Per ripristinare i gestori eliminati per un particolare sito Web, è consigliabile eseguire "WFServicesReg.exe r" per rimuovere i gestori da tutti i siti Web, quindi eseguire "WFServicesReg.exe c" per creare i gestori appropriati per tutti i siti Web.  
  
### <a name="configuring-handlers-after-switching-iis-mode"></a>Configurazione dei gestori dopo il cambio di modalità di IIS  
 Quando IIS è in modalità di configurazione condivisa e [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)] è installato, la metabase IIS viene configurata in un percorso condiviso. Se si passa IIS a una modalità di configurazione non-condivisa, la metabase locale non conterrà i gestori necessari. Per configurare correttamente la metabase locale, è possibile importare la metabase condivisa in locale, o eseguire "WFServicesReg.exe /c" che configura la metabase locale.
