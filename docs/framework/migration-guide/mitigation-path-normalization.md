---
title: 'Migrazione: Normalizzazione del percorso'
ms.date: 03/30/2017
ms.assetid: 158d47b1-ba6d-4fa6-8963-a012666bdc31
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: aa31641cc325f15b9afe677038deb33c57e77fd1
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/02/2018
ms.locfileid: "43388352"
---
# <a name="mitigation-path-normalization"></a>Migrazione: Normalizzazione del percorso
A partire dalle applicazioni destinate a [!INCLUDE[net_v462](../../../includes/net-v462-md.md)], la normalizzazione del percorso in .NET Framework è stata modificata.  
  
## <a name="what-is-path-normalization"></a>Che cos'è la normalizzazione di un percorso?  
 La normalizzazione di un percorso include la modifica della stringa che identifica un file o il percorso in modo che sia conforme a un percorso valido sul sistema operativo di destinazione. In genere, la normalizzazione implica:  
  
-   La conversione in forma canonica dei separatori di directory e dei componenti.  
  
-   L'applicazione della directory corrente in un percorso relativo.  
  
-   La valutazione della directory relativa (`.`) o della directory padre (`..`) in un percorso.  
  
-   La rimozione di caratteri specificati.  
  
## <a name="the-changes"></a>Le modifiche  
 A partire dalle applicazioni destinate a [!INCLUDE[net_v462](../../../includes/net-v462-md.md)], la normalizzazione è stata modificata così come segue:  
  
-   Il runtime viene rinviato alla funzione [GetFullPathName](/windows/desktop/api/fileapi/nf-fileapi-getfullpathnamea) del sistema operativo per normalizzare i percorsi.  
  
-   La normalizzazione non consiste più nel rimuovere la fine dei segmenti di directory (ad esempio uno spazio alla fine di un nome di directory).  
  
-   Supporto per la sintassi del percorso dispositivo in attendibilità totale, tra cui `\\.\` e, per le API del file I/O in mscorlib. dll, `\\?\`.  
  
-   Il runtime non convalida i percorsi di sintassi del dispositivo.  
  
-   È supportato l'uso della sintassi del dispositivo per accedere ai flussi di dati alternativi.  
  
## <a name="impact"></a>Impatto  
 Per le applicazioni destinate a [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] o versioni successive, queste modifiche sono applicate per impostazione predefinita. Tali modifiche migliorano le prestazioni, consentendo al contempo ai metodi di accedere ai percorsi in precedenza inaccessibili.  
  
 Le applicazioni destinate a [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] e versioni precedenti ma in esecuzione in [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] o versioni successive non sono interessate da questa modifica.  
  
## <a name="mitigation"></a>Mitigazione  
 Le app destinate a [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] o versioni successive possono rifiutare esplicitamente questa modifica e usare la normalizzazione legacy aggiungendo il codice seguente alla sezione [\<runtime>](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) del file di configurazione dell'applicazione:  
  
```xml  
<runtime>  
    <AppContextSwitchOverrides value="Switch.System.IO.UseLegacyPathHandling=true" />    
</runtime>  
```  
  
 Le app destinate a [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] o versioni precedenti ma in esecuzione su [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] o versioni successive possono abilitare le modifiche alla normalizzazione del percorso aggiungendo la riga seguente alla sezione [\<runtime>](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) del file di configurazione dell'applicazione:  
  
```xml  
<runtime>  
    <AppContextSwitchOverrides value="Switch.System.IO.UseLegacyPathHandling=false" />    
</runtime>  
```  
  
## <a name="see-also"></a>Vedere anche  
 [Modifiche di reindirizzamento](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-6-2.md)
