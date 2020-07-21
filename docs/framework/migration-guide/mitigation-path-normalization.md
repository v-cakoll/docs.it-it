---
title: 'Migrazione: Normalizzazione del percorso'
description: Informazioni sul modo in cui la normalizzazione dei percorsi in .NET Framework è cambiata a partire dalle app destinate a .NET Framework 4.6.2.
ms.date: 03/30/2017
ms.assetid: 158d47b1-ba6d-4fa6-8963-a012666bdc31
ms.openlocfilehash: 89dcc46d9f266ffd3635dc0cc02b634720356eda
ms.sourcegitcommit: cf5a800a33de64d0aad6d115ffcc935f32375164
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/20/2020
ms.locfileid: "86475216"
---
# <a name="mitigation-path-normalization"></a>Migrazione: Normalizzazione del percorso
A partire dalle app destinate a .NET Framework 4.6.2, la normalizzazione del percorso nel .NET Framework è cambiata.  
  
## <a name="what-is-path-normalization"></a>Che cos'è la normalizzazione di un percorso?  
 La normalizzazione di un percorso include la modifica della stringa che identifica un file o il percorso in modo che sia conforme a un percorso valido sul sistema operativo di destinazione. In genere, la normalizzazione implica:  
  
- La conversione in forma canonica dei separatori di directory e dei componenti.  
  
- L'applicazione della directory corrente in un percorso relativo.  
  
- La valutazione della directory relativa (`.`) o della directory padre (`..`) in un percorso.  
  
- La rimozione di caratteri specificati.  
  
## <a name="the-changes"></a>Le modifiche  
 A partire dalle applicazioni destinate a .NET Framework 4.6.2, la normalizzazione del percorso è stata modificata come segue:  
  
- Il runtime viene rinviato alla funzione [GetFullPathName](/windows/desktop/api/fileapi/nf-fileapi-getfullpathnamea) del sistema operativo per normalizzare i percorsi.  
  
- La normalizzazione non consiste più nel rimuovere la fine dei segmenti di directory (ad esempio uno spazio alla fine di un nome di directory).  
  
- Supporto per la sintassi del percorso dispositivo in attendibilità totale, tra cui `\\.\` e, per le API del file I/O in mscorlib. dll, `\\?\`.  
  
- Il runtime non convalida i percorsi di sintassi del dispositivo.  
  
- È supportato l'uso della sintassi del dispositivo per accedere ai flussi di dati alternativi.  
  
## <a name="impact"></a>Impatto  

Per le applicazioni destinate a .NET Framework 4.6.2 o versioni successive, queste modifiche sono applicate per impostazione predefinita. Tali modifiche migliorano le prestazioni, consentendo al contempo ai metodi di accedere ai percorsi in precedenza inaccessibili.  
  
Le applicazioni destinate a .NET Framework 4.6.1 e versioni precedenti ma in esecuzione in .NET Framework 4.6.2 o versioni successive non sono interessate da questa modifica.  
  
## <a name="mitigation"></a>Strategia di riduzione del rischio  
 Le app destinate a .NET Framework 4.6.2 o versioni successive possono rifiutare esplicitamente questa modifica e usare la normalizzazione legacy aggiungendo quanto segue alla [\<runtime>](../configure-apps/file-schema/runtime/runtime-element.md) sezione del file di configurazione dell'applicazione:  
  
```xml  
<runtime>  
    <AppContextSwitchOverrides value="Switch.System.IO.UseLegacyPathHandling=true" />
</runtime>  
```  
  
Le app destinate a .NET Framework 4.6.1 o versioni precedenti ma in esecuzione nel .NET Framework 4.6.2 o versioni successive possono abilitare le modifiche alla normalizzazione del percorso aggiungendo la riga seguente alla [\<runtime>](../configure-apps/file-schema/runtime/runtime-element.md) sezione del file di configurazione dell'applicazione:  
  
```xml  
<runtime>  
    <AppContextSwitchOverrides value="Switch.System.IO.UseLegacyPathHandling=false" />
</runtime>  
```  
  
## <a name="see-also"></a>Vedere anche

- [Compatibilità tra le versioni](application-compatibility.md)
