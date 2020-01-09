---
title: Provider ETW di CLR
ms.date: 03/30/2017
helpviewer_keywords:
- ETW, CLR providers
- CLR ETW providers
ms.assetid: 0beafad4-b2c8-47f4-b342-83411d57a51f
ms.openlocfilehash: dbdd4ad862ae300c330dc56a82fcd65b866855b6
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75716174"
---
# <a name="clr-etw-providers"></a>Provider ETW di CLR
Common Language Runtime (CLR) dispone di due provider, ovvero il provider di runtime e quello di rundown.  
  
 Il provider di runtime genera eventi in base alle parole chiave (categorie di eventi) abilitate. È ad esempio possibile raccogliere gli eventi del caricatore abilitando la parola chiave `LoaderKeyword`.  
  
 Gli eventi Event Tracing for Windows (ETW) vengono registrati in un file con estensione ETL, che può essere successivamente elaborato in un file con valori delimitati da virgole (CSV) in base alle esigenze. Per informazioni su come convertire il file con estensione etl in un file con estensione csv, vedere [Controllo della registrazione di .NET Framework](controlling-logging.md).  
  
## <a name="the-runtime-provider"></a>Provider di runtime  
 Il provider di runtime è il principale provider ETW di CLR.  
  
 Il GUID del provider di runtime di CLR è e13c0d23-ccbc-4e12-931b-d9cc2eee27e4.  
  
 Per alcuni esempi di registrazione e visualizzazione di eventi ETW di CLR tramite strumenti comunemente disponibili, vedere [Controllo della registrazione di .NET Framework](controlling-logging.md).  
  
 Oltre a usare parole chiave, come `LoaderKeyword`, può essere necessario abilitare parole chiave per la registrazione di eventi che possono essere generati troppo di frequente. Questi eventi sono abilitati dalle parole chiave `StartEnumerationKeyword` e `EndEnumerationKeyword`, riepilogate in [Parole chiave e livelli ETW di CLR](clr-etw-keywords-and-levels.md).  
  
## <a name="the-rundown-provider"></a>Provider di rundown  
 Il provider di rundown deve essere attivato per determinati usi finalizzati a scopi specifici. Per la maggior parte degli utenti, tuttavia, dovrebbe essere sufficiente il provider di runtime.  
  
 Il GUID del provider di rundown di CLR è A669021C-C450-4609-A035-5AF59AF4DF18.  
  
 La registrazione ETW viene in genere abilitata prima dell'avvio di un processo e disattivata al termine dello stesso. Se tuttavia la registrazione ETW viene attivata durante l'esecuzione del processo, sono necessarie informazioni aggiuntive sul processo. Per la risoluzione dei simboli, ad esempio, è necessario registrare gli eventi di metodo per i metodi già caricati prima dell'attivazione della registrazione.  
  
 Gli eventi `DCStart` e `DCEnd` acquisiscono lo stato del processo al momento dell'avvio e dell'arresto della raccolta dei dati. (Lo stato si riferisce alle informazioni a livello generale, inclusi i metodi che sono già stati compilati JIT (just-in-Time) e gli assembly caricati. Questi due eventi possono fornire informazioni sugli eventi che si sono già verificati nel processo. ad esempio, quali metodi sono stati compilati tramite JIT e così via.  
  
 Solo gli eventi il cui nome contiene `DC`, `DCStart`, `DCEnd` o `DCInit` vengono generati nel provider di rundown ed esclusivamente in questo provider.  
  
 Oltre ai filtri delle parole chiave di evento, il provider di rundown supporta anche le parole chiave `StartRundownKeyword` e `EndRundownKeyword` per fornire un filtraggio mirato.  
  
### <a name="start-rundown"></a>Rundown iniziale  
 Quando si abilita la registrazione nel provider di rundown tramite la parola chiave `StartRundownKeyword`, viene attivato un rundown iniziale. Ciò determina la generazione dell'evento `DCStart` e l'acquisizione dello stato del sistema. Prima dell'avvio dell'enumerazione, viene generato l'evento `DCStartInit`. Al termine dell'enumerazione, viene generato l'evento `DCStartComplete` per notificare al controller la regolare conclusione della raccolta dei dati.  
  
### <a name="end-rundown"></a>Rundown finale  
 Quando si abilita la registrazione nel provider di rundown tramite la parola chiave `EndRundownKeyword`, viene attivato un rundown finale. Ciò determina l'arresto della profilatura in un processo ancora in esecuzione. Gli eventi `DCEnd` acquisiscono lo stato del sistema nel momento in cui viene arrestata la profilatura.  
  
 Prima dell'avvio dell'enumerazione, viene generato l'evento `DCEndInit`. Al termine dell'enumerazione, viene generato l'evento `DCEndComplete` per notificare al consumer la regolare conclusione della raccolta dei dati. Il rundown iniziale e quello finale vengono usati principalmente per la risoluzione di simboli gestiti. Il rundown iniziale può fornire informazioni sull'intervallo di indirizzi per i metodi già compilati tramite JIT prima dell'avvio della sessione di profilatura. Il rundown finale può fornire informazioni sull'intervallo di indirizzi per tutti i metodi che sono stati compilati tramite JIT quando la profilatura sta per essere disattivata.  
  
 Il rundown finale non viene eseguito automaticamente quando una sessione di profilatura viene arrestata. Al contrario, uno strumento che sta provando a eseguire la risoluzione di simboli gestiti deve richiamare in modo esplicito una sessione del provider di rundown di CLR, con la parola chiave `EndRundownKeyword` abilitata, appena prima dell'arresto della profilatura.  
  
 Anche se il rundown iniziale o il rundown finale può fornire informazioni sull'intervallo di indirizzi dei metodi per la risoluzione di simboli gestiti, è consigliabile usare la parola chiave `EndRundownKeyword` (che fornisce eventi `DCEnd`) anziché la parola chiave `StartRundownKeyword` (che fornisce eventi `DCStart`). Se si usa `StartRundownKeyword`, il rundown si verifica durante la sessione di profilatura e questo può pregiudicare lo scenario profilato.  
  
## <a name="etw-data-collection-using-runtime-and-rundown-providers"></a>Raccolta dei dati ETW tramite provider di runtime e rundown  
 L'esempio seguente illustra come usare il provider di rundown di CLR in modo che la risoluzione di simboli dei processi gestiti abbia un impatto minimo, indipendentemente dal fatto che i processi abbiano inizio o fine all'interno o all'esterno della finestra profilata.  
  
1. Attivare la registrazione ETW tramite il provider di runtime di CLR:  
  
    ```console
    xperf -start clr -on e13c0d23-ccbc-4e12-931b-d9cc2eee27e4:0x1CCBD:0x5 -f clr1.etl      
    ```  
  
     Il log verrà salvato nel file clr1.etl.  
  
2. Per arrestare la profilatura mentre il processo è ancora in esecuzione, avviare il provider di rundown per acquisire gli eventi `DCEnd`:  
  
    ```console
    xperf -start clrRundown -on A669021C-C450-4609-A035-5AF59AF4DF18:0xB8:0x5 -f clr2.etl      
    ```  
  
     In questo modo, la raccolta di eventi `DCEnd` potrà avviare una sessione di rundown. La raccolta di tutti gli eventi può richiedere un tempo di attesa compreso fra 30 e 60 secondi. Il log verrà salvato nel file clr1.et2.  
  
3. Disattivare tutta la profilatura ETW:  
  
    ```console
    xperf -stop clrRundown   
    xperf -stop clr  
    ```  
  
4. Unire i profili per creare un unico file di log:  
  
    ```console
    xperf -merge clr1.etl clr2.etl merged.etl  
    ```  
  
     Il file merged.etl conterrà gli eventi delle sessioni dei provider di runtime e rundown.  
  
 Uno strumento può eseguire i passaggi 2 e 3 (avvio di una sessione di rundown e conclusione della profilatura) anziché disattivare immediatamente la profilatura nel momento in cui un utente ne richiede l'arresto. Uno strumento può anche eseguire il passaggio 4.  
  
## <a name="see-also"></a>Vedere anche

- [Eventi ETW in Common Language Runtime](etw-events-in-the-common-language-runtime.md)
