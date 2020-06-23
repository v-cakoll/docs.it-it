---
title: Strumento di registrazione ServiceModel (ServiceModelReg.exe)
description: Utilizzare questo strumento da riga di comando per gestire la registrazione dei componenti WCF e WF in un singolo computer se si verificano problemi con l'attivazione del servizio.
ms.date: 03/30/2017
ms.assetid: 396ec5ae-e34f-4c64-a164-fcf50e86b6ac
ms.openlocfilehash: 347b1b8071abe7d8eb7e16ffd879c1fdb9825bc7
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/23/2020
ms.locfileid: "85245895"
---
# <a name="servicemodel-registration-tool-servicemodelregexe"></a>Strumento di registrazione ServiceModel (ServiceModelReg.exe)
Questo strumento da riga di comando offre la possibilità di gestire la registrazione di componenti WCF e WF in un singolo computer. In condizioni normali l'utilizzo di questo strumento non è consigliabile perché i componenti WCF e WF vengono configurati quando installati. Tuttavia, se si verificano problemi con l'attivazione del servizio, si può tentare la registrazione dei componenti tramite questo strumento.  
  
## <a name="syntax"></a>Sintassi  
  
```console  
ServiceModelReg.exe[(-ia|-ua|-r)|((-i|-u) -c:<command>)] [-v|-q] [-nologo] [-?]  
```  
  
## <a name="remarks"></a>Osservazioni  
 Lo strumento si trova nel percorso seguente:  
  
 %SystemRoot%\Microsoft.Net\Framework\v3.0\Windows Communication Foundation\  
  
> [!NOTE]
> Quando lo strumento di registrazione ServiceModel viene eseguito in Windows Vista, la finestra di dialogo **funzionalità Windows** potrebbe non riflettere che l'opzione di **attivazione Windows Communication Foundation http** in **Microsoft .NET Framework 3,0** è attivata. È possibile accedere alla finestra di dialogo **funzionalità Windows** facendo clic sul pulsante **Start**, quindi su **Esegui** e digitando **OptionalFeatures**.  
  
 Nella tabella riportata di seguito sono descritte le opzioni che possono essere utilizzate con ServiceModelReg.exe.  
  
|Opzione|Descrizione|  
|------------|-----------------|  
|`-ia`|Installa tutti i componenti WCF e WF.|  
|`-ua`|Disinstalla tutti i componenti WCF e WF.|  
|`-r`|Ripristina tutti i componenti WCF e WF.|  
|`-i`|Installa tutti i componenti WCF e WF specificati con -c.|  
|`-u`|Disinstalla tutti i componenti WCF e WF specificati con -c.|  
|`-c`|Installa o disinstalla un componente:<br /><br /> -httpnamespace – prenotazione dello spazio dei nomi HTTP<br />-tcpportsharing-servizio di condivisione porte TCP<br />-tcpactivation-servizio di attivazione TCP (non supportato in .NET 4 Client Profile)<br />-namedpipeactivation-servizio di attivazione named pipe (non supportato in .NET 4 Client Profile<br />-msmqactivation-servizio di attivazione MSMQ (non supportato in .NET 4 Client Profile<br />-ETW-manifesti di traccia eventi ETW (Windows Vista o versioni successive)|  
|`-q`|Modalità non interattiva (solo registrazione errori visualizzata)|  
|`-v`|Modalità dettagliata.|  
|`-nologo`|Elimina le informazioni di copyright e il messaggio di avvio.|  
|`-?`|Visualizza il testo della Guida|  
  
## <a name="fixing-the-fileloadexception-error"></a>Correzione dell’errore FileLoadException   
 Se sono state installate versioni precedenti di WCF nel computer, è possibile che venga ricevuto un `FileLoadFoundException` errore quando si esegue lo strumento ServiceModelReg per registrare una nuova installazione. Ciò può verificarsi anche se sono stati rimossi manualmente file dall’installazione precedente, ma sono state mantenute intatte le impostazioni machine.config.  
  
 Verrà visualizzato un messaggio di errore simile al seguente:  
  
```console  
Error: System.IO.FileLoadException: Could not load file or assembly 'System.ServiceModel, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089' or one of its dependencies. The located assembly's manifest definition does not match the assembly reference. (Exception from HRESULT: 0x80131040)  
File name: 'System.ServiceModel, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089'  
```  
  
 È necessario notare dal messaggio di errore che è stato installato l’assembly System.ServiceModel Versione 2.0.0.0 di una precedente versione di Customer Technology Preview (CTP). La versione corrente dell'assembly System.ServiceModel rilasciata è invece 3.0.0.0. Questo problema si verifica quindi quando si desidera installare la versione ufficiale di WCF in un computer in cui è stata installata una versione CTP iniziale di WCF, ma non completamente disinstallata.  
  
 ServiceModelReg.exe non può eseguire la pulizia di voci della versione precedente, né può registrare voci della versione nuova. L'unica soluzione alternativa consiste nel modificare manualmente machine.config. È possibile individuare il file nel percorso seguente.  
  
```console  
%windir%\Microsoft.NET\Framework\v2.0.50727\config\machine.config
```  
  
 Se si esegue WCF in un computer a 64 bit, è necessario modificare anche lo stesso file in questa posizione.  
  
```console  
%windir%\Microsoft.NET\Framework64\v2.0.50727\config\machine.config
```  
  
 Individuare tutti i nodi XML in questo file che fanno riferimento a "System. ServiceModel, Version = 2.0.0.0", eliminarli e tutti i nodi figlio. Per risolvere il problema, salvare il file e ripetere l'esecuzione di ServiceModelReg.exe.  
  
## <a name="examples"></a>Esempi  
 Negli esempi seguenti viene illustrato come utilizzare le opzioni più comuni dello strumento ServiceModelReg.exe.  
  
```console  
ServiceModelReg.exe -ia  
  Installs all components  
ServiceModelReg.exe -i -c:httpnamespace -c:etw  
  Installs HTTP namespace reservation and ETW manifests  
ServiceModelReg.exe -u -c:etw  
  Uninstalls ETW manifests  
ServiceModelReg.exe -r  
  Repairs an extended install  
```
