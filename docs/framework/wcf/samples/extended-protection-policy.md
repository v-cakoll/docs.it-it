---
title: Criteri di protezione estesa
ms.date: 03/30/2017
ms.assetid: e2616a10-317e-4c34-8023-0c015a80a82f
ms.openlocfilehash: 59a377a94978741f3f116bab819dff77d8b0fee4
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2018
ms.locfileid: "43532345"
---
# <a name="extended-protection-policy"></a>Criteri di protezione estesa
La protezione estesa rappresenta un'iniziativa di sicurezza per la protezione da attacchi di tipo man-in-the-middle (MITM). Un attacco MITM è un rischio per la sicurezza nel quale l'autore dell'attacco rileva le credenziali di un client e le inoltra a un server.  
  
## <a name="demonstrates"></a>Dimostrazione  
 Protezione estesa  
  
## <a name="discussion"></a>Discussione  
 Quando le applicazioni eseguono l'autenticazione con i metodi Kerberos, Digest o NTLM usando il protocollo HTTPS, viene innanzitutto stabilito un canale TLS (Transport Level Security) e l'autenticazione viene eseguita usando un canale protetto. Non esiste tuttavia alcuna associazione tra la chiave di sessione generata da SSL e quella generata durante l'autenticazione e pertanto l'autore dell'attacco di tipo MITM può inserirsi tra il client e il server e iniziare a inoltrare le richieste dal client, anche quando il canale di trasporto è protetto, poiché il server non ha modo di sapere se il canale protetto è stato stabilito dal client o dall'autore dell'attacco di tipo MITM. La soluzione in questo scenario consiste nell'associare il canale TLS esterno al canale di autenticazione interno, in modo tale che il server possa determinare se si tratta di un attacco di tipo MITM.  
  
> [!NOTE]
>  Questo esempio può essere usato solo se ospitato in IIS. Non può essere usato su Cassini - Visual Studio Development Server in quanto Cassini non supporta HTTPS.  
  
> [!NOTE]
>  Questa funzionalità è attualmente disponibile solo in Windows 7. La procedura seguente è specifica di Windows 7.  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>Per impostare, compilare ed eseguire l'esempio  
  
1.  Installare Internet Information Services dalla **Pannello di controllo**, **Aggiungi/Rimuovi programmi**, **funzionalità Windows**.  
  
2.  Installare **Windows autenticazione** nelle **le funzionalità di Windows**, **Internet Information Services**, **servizi World Wide Web**,  **Sicurezza**, e **l'autenticazione di Windows**.  
  
3.  Installare **Windows Communication Foundation HTTP Activation** nelle **funzionalità Windows**, **Microsoft .NET Framework 3.5.1**, e **comunicazione di Windows Foundation HTTP Activation**.  
  
4.  In questo esempio il client deve stabilire un canale protetto con il server, di conseguenza è necessario che sia presente un certificato del server che può essere installato da Gestione Internet Information Services.  
  
    1.  Aprire Gestione IIS. Aprire **certificati del Server**, che viene visualizzato il **visualizzazione funzionalità** scheda quando si seleziona il nodo radice (nome del computer).  
  
    2.  Ai fini dimostrativi di questo esempio, creare un certificato autofirmato. Se non si desidera che venga visualizzato un messaggio relativo alla sicurezza del certificato, installare il certificato nell'archivio Autorità di certificazione radice attendibili.  
  
5.  Aprire il **azioni** riquadro per il sito Web predefinito. Fare clic su **modifica sito**, **associazioni**. Aggiungere HTTPS come tipo, se non già presente, con numero di porta 443. Assegnare il certificato SSL creato nel passaggio precedente.  
  
6.  Compilare il servizio. In questo modo viene creata automaticamente una directory virtuale in IIS e vengono copiati i file con estensione dll e svc e il file di configurazione per il servizio da ospitare nel Web.  
  
7.  Aprire Gestione IIS. Fare doppio clic su directory virtuale (**ExtendedProtection**), che è stato creato nel passaggio precedente. Selezionare **Converti in applicazione**.  
  
8.  Aprire il **Authentication** modulo in Gestione IIS per questa directory virtuale e abilitare **l'autenticazione di Windows**.  
  
9. Aprire **impostazioni avanzate** sotto **l'autenticazione di Windows** per questa directory virtuale e impostarlo su **necessari**.  
  
10. È possibile testare il servizio eseguendo l'accesso all'URL HTTPS da una finestra del browser (fornire un nome di dominio completo). Se si desidera accedere a tale URL da un computer remoto, verificare che il firewall sia aperto per tutte le connessioni HTTP e HTTPS in entrata.  
  
11. Aprire il file di configurazione del client e specificare un nome di dominio completo per l'attributo dell'indirizzo del client o dell'endpoint sostituendo `<<full_machine_name>>`.  
  
12. Eseguire il client. Per comunicare con il servizio, il client stabilisce un canale protetto e usa la protezione estesa.  
  
> [!IMPORTANT]
>  È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Se questa directory non esiste, andare al [Windows Communication Foundation (WCF) e gli esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi. Questo esempio si trova nella directory seguente.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\Security\ExtendedProtection`
