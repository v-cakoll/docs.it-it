---
title: Clrver.exe (strumento della versione CLR)
ms.date: 03/30/2017
helpviewer_keywords:
- Clrver.exe
- CLR Version tool
ms.assetid: cbc2ee86-bdc8-4a65-a8f1-ba23bce3a699
ms.openlocfilehash: bfc612ef5455e1b4a03d15fd99a8a1873d2c7c08
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75715791"
---
# <a name="clrverexe-clr-version-tool"></a>Clrver.exe (strumento della versione CLR)
Lo strumento della versione CLR (Clrver.exe) segnala tutte le versioni di CRL (Common Language Runtime) installate nel computer.  
  
 Viene installato automaticamente con Visual Studio. Per eseguire lo strumento, usare il Prompt dei comandi per gli sviluppatori per Visual Studio (o il prompt dei comandi di Visual Studio in Windows 7). Per altre informazioni, vedere [Prompt dei comandi](developer-command-prompt-for-vs.md).  
  
 Al prompt dei comandi digitare quanto segue:  
  
## <a name="syntax"></a>Sintassi  
  
```console  
clrver [option]  
```  
  
## <a name="options"></a>Options  
  
|Opzione|Descrizione|  
|------------|-----------------|  
|`-all`|Visualizza tutti i processi sul computer che utilizzano CLR.|  
|*pid*|Visualizza le versioni di CLR utilizzate dal processo con l'ID processo (PID) specificato.|  
|`-?`|Visualizza la sintassi e le opzioni di comando dello strumento.|  
  
## <a name="remarks"></a>Note  
 Se si chiama Clrver.exe senza opzioni, vengono visualizzate tutte le versioni CLR installate. Se si specifica un PID per un altro utente, è necessario disporre di autorizzazioni amministrative per ottenere le informazioni sulla versione.  
  
> [!NOTE]
> In Windows Vista e versioni successive i privilegi di un utente sono determinati dalla funzionalità Controllo dell'account utente. Ai membri del gruppo Administrators predefinito vengono assegnati due token di accesso in fase di esecuzione, ovvero un token di accesso utente standard e un token di accesso amministratore. Per impostazione predefinita, viene assegnato il ruolo dell'utente standard. Per eseguire il codice che richiede autorizzazioni amministrative, è innanzitutto necessario elevare i propri privilegi da utente standard ad amministratore. A tale scopo, all'avvio del prompt dei comandi fare clic con il pulsante destro del mouse sull'icona del prompt dei comandi e indicare che si desidera eseguirlo come amministratore.  
  
 Se si tenta di determinare la versione di CLR per i processi SYSTEM, LOCAL SERVICE e NETWORK SERVICE, viene visualizzato un messaggio che indica che il PID non esiste.  
  
## <a name="examples"></a>Esempi  
 Il comando che segue visualizza tutte le versioni di CLR installate nel computer.  
  
 `clrver`  
  
 Il comando che segue visualizza la versione di CLR utilizzata dal processo 128.  
  
 `clrver 128`  
  
 Il comando che segue visualizza tutti i processi gestiti e la versione di CLR utilizzata.  
  
 `Clrver -all`  
  
## <a name="see-also"></a>Vedere anche

- [Strumenti](index.md)
- [Prompt dei comandi](developer-command-prompt-for-vs.md)
