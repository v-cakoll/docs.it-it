---
title: Storeadm.exe (strumento per lo spazio di memorizzazione isolato)
ms.date: 03/30/2017
helpviewer_keywords:
- Storeadm.exe
- listing stores for current user
- Isolated Storage tool
- stores, current user
- removing stores
ms.assetid: b81202b8-d91d-4b23-9c53-4a112f74a44a
ms.openlocfilehash: 46e846eaf92835fb2a9130b85ed20749934ca5a1
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75715721"
---
# <a name="storeadmexe-isolated-storage-tool"></a>Storeadm.exe (strumento per lo spazio di memorizzazione isolato)
Lo strumento per lo spazio di memorizzazione isolato elenca o rimuove tutti gli archivi esistenti dell'utente attualmente connesso.  
  
 Viene installato automaticamente con Visual Studio. Per eseguire lo strumento, usare il Prompt dei comandi per gli sviluppatori per Visual Studio (o il prompt dei comandi di Visual Studio in Windows 7). Per altre informazioni, vedere [Prompt dei comandi](developer-command-prompt-for-vs.md).  
  
 Al prompt dei comandi digitare quanto segue:  
  
## <a name="syntax"></a>Sintassi  
  
```console  
storeadm [/list][/machine][/remove][/roaming][/quiet]  
```  
  
## <a name="parameters"></a>Parametri  
  
|Opzione|Descrizione|  
|------------|-----------------|  
|**/h**[**elp**]|Visualizza la sintassi e le opzioni di comando dello strumento.|  
|**/list**|Visualizza tutti gli archivi esistenti dell'utente attualmente connesso, inclusi gli archivi di tutte le applicazioni e di tutti gli assembly eseguiti da tale utente.|  
|**/machine**|Seleziona l'archivio computer. Usare questa opzione con l'opzione **/list** o **/remove** per specificare che l'operazione deve essere applicata all'archivio computer.<br /><br /> Questa è una nuova opzione di .NET Framework versione 2.0.|  
|**/quiet**|Specifica la modalità non interattiva. Evita la visualizzazione dell'output informativo, in modo che vengano visualizzati solo i messaggi di errore.|  
|**/remove**|Rimuove definitivamente tutti gli archivi esistenti dell'utente attualmente connesso.|  
|**/roaming**|Seleziona l'archivio roaming. Usare questa opzione con l'opzione **/list** o **/remove** per specificare che l'operazione deve essere applicata all'archivio roaming.|  
|**/?**|Visualizza la sintassi e le opzioni di comando dello strumento.|  
  
## <a name="remarks"></a>Note  
 Se si esegue Storeadm.exe dalla riga di comando senza specificare alcuna opzione, verranno visualizzate la sintassi e le opzioni dello strumento.  
  
 Le opzioni **/list** e **/remove** sono in genere usate singolarmente. Se tuttavia vengono specificate due o più opzioni, queste verranno eseguite nell'ordine in cui sono state immesse sulla riga di comando.  
  
 Le applicazioni possono scegliere di salvare i dati in uno di due archivi relativi a un utente o nell'archivio computer:  
  
- L'archivio locale si trova in un percorso per cui è escluso il roaming (in Windows 2000 e versioni successive) anche se per l'utente è abilitato il roaming dei dati.  
  
- L'archivio roaming si trova in un percorso in cui il roaming è consentito, ma solo se è abilitato anche per l'utente attraverso l'amministrazione di Windows NT.  
  
- L'archivio computer è comune a tutti gli utenti di un computer e quindi si trova in una directory comune del computer.  
  
    > [!NOTE]
    > L'archivio computer è stato introdotto con .NET Framework versione 2.0.  
  
 L'eventuale abilitazione del roaming per l'utente non ha alcun effetto sull'amministrazione di Storeadm.exe. Se lo strumento viene eseguito senza opzioni, tutte le operazioni verranno applicate all'archivio locale. Se lo strumento viene eseguito con l'opzione **/roaming**, tutte le operazioni verranno applicate all'archivio abilitato al roaming. Se lo strumento viene eseguito con l'opzione **/machine**, tutte le operazioni verranno applicate all'archivio computer.  
  
## <a name="see-also"></a>Vedere anche

- [Strumenti](index.md)
- [Spazio di memorizzazione isolato](../../standard/io/isolated-storage.md)
- [Prompt dei comandi](developer-command-prompt-for-vs.md)
