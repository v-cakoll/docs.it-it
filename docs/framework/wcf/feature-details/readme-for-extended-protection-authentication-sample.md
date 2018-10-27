---
title: File Leggimi sull'esempio relativo alla protezione estesa per l'autenticazione
ms.date: 03/30/2017
ms.assetid: 80bf2e97-398d-4db5-9040-d96478a2ccab
ms.openlocfilehash: 19fe961e346874346485442bd0ba90badab5f79f
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2018
ms.locfileid: "50192473"
---
# <a name="readme-for-extended-protection-authentication-sample"></a>File Leggimi sull'esempio relativo alla protezione estesa per l'autenticazione
La protezione estesa è un'iniziativa di sicurezza per impedire attacchi man-in-the-middle (MITM) in cui un utente malintenzionato (il "man-in-the-middle"), intercetta le credenziali del client e li utilizza per accedere alle risorse protette nel server di destinazione del client.  
  
 Per altre informazioni, vedere [Extended Protection for Authentication Overview](../../../../docs/framework/wcf/feature-details/extended-protection-for-authentication-overview.md).  
  
> [!NOTE]
>  Questo esempio funziona solo quando è ospitato in IIS e non funziona in Visual Studio Development Server perché non supporta HTTPS.  
  
## <a name="to-set-up-build-and-run-the-sample"></a>Per impostare, compilare ed eseguire l'esempio  
  
1.  Installare IIS nel computer utilizzando Installazione applicazioni -> Funzionalità Windows.  
  
2.  Attivare l'autenticazione di Windows nelle funzionalità di Windows, ovvero Internet Information Services -> Servizi World Wide Web -> Sicurezza -> Autenticazione Windows.  
  
3.  Abilitare l'attivazione HTTP nelle funzionalità di Windows, ovvero Microsoft .NET Framework 3.5.1 -> Attivazione HTTP di Windows Communication Foundation.  
  
4.  In questo esempio il client deve stabilire un canale protetto con il server ed è di conseguenza necessario che sia presente un certificato del server che può essere installato da Gestione Internet Information Services.  
  
    1.  Aprire Gestione IIS -> Certificati server (dalla scheda delle funzionalità).  
  
    2.  Ai fini dimostrativi di questo esempio, è possibile creare un certificato autofirmato. Se non si desidera che venga visualizzato un messaggio relativo alla sicurezza del certificato, è possibile installare un certificato presente nell'archivio Autorità di certificazione radice attendibili.  
  
5.  Spostarsi sul riquadro azioni per il sito Web predefinito. Fare clic su Modifica sito -> Binding. Aggiungere HTTPS come tipo, se non è già presente, con il numero di porta 443 e assegnare il certificato SSL creato nel passaggio precedente.  
  
6.  Compilare il servizio. In questo modo viene creata automaticamente una directory virtuale in IIS (dall'azione di post-compilazione specificata nelle proprietà di progetto) e vengono copiati i file con estensione dll e svc e il file di configurazione per un servizio da ospitare nel Web.  
  
7.  Aprire Gestione IIS. Fare clic con il pulsante destro del mouse sulla directory virtuale (ExtendedProtection) creata nel passaggio precedente, quindi scegliere Converti in applicazione.  
  
8.  Aprire il modulo di autenticazione in Gestione IIS relativo alla directory virtuale e abilitare l'autenticazione di Windows.  
  
9. Aprire le impostazioni avanzate per l'autenticazione di Windows relativa alla directory virtuale e specificare il valore in modo che sia richiesta poiché nell'esempio il valore ExtendedProtection corrispondente è impostata su Sempre.  
  
10. Per testare il servizio, accedere all'URL da una finestra del browser. Se si desidera accedere a tale URL da più computer, verificare che il firewall sia aperto per tutte le connessioni HTTP e HTTPS in ingresso.  
  
11. Aprire il file di configurazione client e fornire un nome di computer completo per il \<client >- \<endpoint >-attributo dell'indirizzo, sostituendo << full_machine_name >>.  
  
12. Eseguire il client. Per comunicare con il servizio, il client stabilisce un canale protetto e utilizza la protezione estesa tra gli elementi.
