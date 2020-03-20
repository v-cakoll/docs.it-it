---
title: Modifiche apportate all'autenticazione NTLM per HttpWebRequest nella versione 3.5 SP1
ms.date: 03/30/2017
ms.assetid: 8bf0b428-5a21-4299-8d6e-bf8251fd978a
ms.openlocfilehash: 388e6dc648e1fd68e24a852cb08de107f09f9c9f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "64754882"
---
# <a name="changes-to-ntlm-authentication-for-httpwebrequest-in-version-35-sp1"></a>Modifiche apportate all'autenticazione NTLM per HttpWebRequest nella versione 3.5 SP1

In .NET Framework 3.5 SP1 e versioni successive sono state apportate modifiche per la sicurezza che influiscono sul modo in cui l'autenticazione integrata di Windows viene gestita da <xref:System.Net.HttpWebRequest>, <xref:System.Net.HttpListener>, <xref:System.Net.Security.NegotiateStream> e dalle classi correlate nello spazio dei nomi System.Net. Queste modifiche possono avere effetto sulle applicazioni che usano queste classi per eseguire richieste Web e ricevere risposte in cui viene usata l'autenticazione integrata di Windows basata su NTLM. Possono inoltre influire sulle applicazioni client e sui server Web configurati per l'utilizzo dell'autenticazione integrata di Windows.

## <a name="overview"></a>Panoramica

La progettazione dell'autenticazione integrata di Windows fa sì che alcune risposte con verifica delle credenziali siano universali, ovvero possano essere riusate o inoltrate. Se questa particolare funzionalità di progettazione non è necessaria, i protocolli di autenticazione dovrebbero contenere informazioni specifiche sulla destinazione e sul canale. I servizi possono quindi fornire protezione estesa per garantire che le risposte con verifica delle credenziali contengano informazioni specifiche sui servizi, ad esempio il nome di un'entità servizio (SPN). Con queste informazioni nello scambio di credenziali, i servizi possono offrire migliore protezione contro l'utilizzo dannoso di risposte con verifica delle credenziali che potrebbero essere state ottenute in modo improprio.

Più componenti negli spazi dei nomi <xref:System.Net> e <xref:System.Net.Security> eseguono l'autenticazione integrata di Windows per conto di un'applicazione chiamante. Questa sezione descrive le modifiche apportate ai componenti System.Net per aggiungere la protezione estesa quando usano l'autenticazione integrata di Windows.

## <a name="changes"></a>Modifiche

Il processo di autenticazione basato su NTLM usato con l'autenticazione integrata di Windows include spesso una richiesta di verifica inviata dal computer di destinazione e quindi ritrasmessa al computer client. Quando un computer riceve una richiesta di verifica generata dal computer stesso, l'autenticazione ha esito negativo a meno che non si tratti di una connessione di loopback, ad esempio con indirizzo IPv4 127.0.0.1.

Quando si accede a un servizio in esecuzione su un server Web interno, viene in genere usato un URL simile a `http://contoso/service` o `https://contoso/service`. Il nome "contoso" spesso non corrisponde al nome del computer in cui viene distribuito il servizio. Per risolvere i nomi in indirizzi, <xref:System.Net> e gli spazi dei nomi correlati supportano l'utilizzo di Active Directory, DNS, NetBIOS, del file hosts del computer locale (in genere WINDOWS\system32\drivers\etc\hosts) o del file lmhosts del computer locale (in genere WINDOWS\system32\drivers\etc\lmhosts). Il nome "contoso" viene risolto in modo che le richieste a "contoso" vengono inviate al computer server appropriato.

Nel caso di distribuzioni di grandi dimensioni, è anche prassi comune assegnare alla distribuzione un singolo nome di server virtuale, senza che i nomi di computer sottostanti vengono mai usati dalle applicazioni client e dagli utenti finali. È ad esempio possibile chiamare il server `www.contoso.com`, ma in una rete interna usare semplicemente "contoso". Questo nome è definito come intestazione Host nella richiesta Web del client. Come specificato dal protocollo HTTP, il campo dell'intestazione della richiesta Host specifica l'host Internet e il numero di porta della risorsa richiesta. Queste informazioni vengono ottenute dall'URI di origine specificato dall'utente o dalla risorsa di riferimento, che in genere è un URL HTTP. In .NET Framework versione 4 queste informazioni possono essere impostate anche dal client usando la nuova proprietà <xref:System.Net.HttpWebRequest.Host%2A>.

La classe <xref:System.Net.AuthenticationManager> controlla i componenti di autenticazione gestita ("moduli") che vengono usati dalle classi derivate di <xref:System.Net.WebRequest> e dalla classe <xref:System.Net.WebClient>. In <xref:System.Net.AuthenticationManager> è disponibile una proprietà che espone un oggetto <xref:System.Net.AuthenticationManager.CustomTargetNameDictionary%2A?displayProperty=nameWithType>, indicizzato in base alla stringa dell'URI, per consentire alle applicazioni di fornire una stringa SPN personalizzata da usare durante l'autenticazione.

Nella versione 3.5 SP1, quando la proprietà <xref:System.Net.AuthenticationManager.CustomTargetNameDictionary%2A> non è impostata, come stringa SPN nello scambio di autenticazione NTLM (NT LAN Manager) viene specificato per impostazione predefinita il nome host usato nell'URL della richiesta. Il nome host usato nell'URL della richiesta può essere diverso dall'intestazione Host specificata in <xref:System.Net.HttpRequestHeader?displayProperty=nameWithType> nella richiesta del client. Il nome host usato nell'URL della richiesta può essere diverso dal nome host effettivo del server, dal nome computer del server, dall'indirizzo IP del computer o dall'indirizzo di loopback. In questi casi la richiesta di autenticazione in Windows ha esito negativo. Per risolvere il problema, è necessario notificare a Windows che il nome host usato nell'URL della richiesta del client, ad esempio "contoso", è in realtà un nome alternativo del computer locale.

Sono possibili varie soluzioni per ovviare a questa modifica in un'applicazione server. L'approccio consigliato consiste nell'eseguire il mapping del nome host usato nell'URL della richiesta alla chiave `BackConnectionHostNames` nel Registro di sistema sul server. La chiave `BackConnectionHostNames` viene normalmente usata per eseguire il mapping di un nome host a un indirizzo di loopback. Di seguito sono elencati i passaggi da seguire.

Per specificare i nomi host di cui è stato eseguito il mapping con l'indirizzo di loopback e che possono connettersi a siti Web in un computer locale, seguire questa procedura:

1. Fare clic su Start, scegliere Esegui, digitare regedit e quindi fare clic su OK.

2. Nell'editor del Registro di sistema cercare la chiave del Registro di sistema seguente e selezionarla:

    `HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\Lsa\MSV1_0`

3. Fare clic con il pulsante destro del mouse su MSV1_0, scegliere Nuovo e quindi fare clic su Valore multistringa.

4. Digitare `BackConnectionHostNames` e quindi premere INVIO.

5. Fare clic con il pulsante destro del mouse su `BackConnectionHostNames` e quindi scegliere Modifica.

6. Nella casella Dati valore digitare uno o più nomi host (come specificato nell'URL della richiesta) per i siti presenti nel computer locale e quindi fare clic su OK.

7. Chiudere l'editor del Registro di sistema e quindi riavviare il servizio IISAdmin ed eseguire IISReset.

Una soluzione alternativa meno sicura consiste nel disabilitare il controllo di loopback, come descritto in <https://support.microsoft.com/kb/896861>. Questa operazione ha l'effetto di disabilitare la protezione contro attacchi di tipo reflection. È pertanto preferibile limitare l'impostazione di nomi alternativi a quelli che si presume vengano effettivamente usati dal computer.

## <a name="see-also"></a>Vedere anche

- <xref:System.Net.AuthenticationManager.CustomTargetNameDictionary%2A?displayProperty=nameWithType>
- <xref:System.Net.HttpRequestHeader?displayProperty=nameWithType>
- <xref:System.Net.HttpWebRequest.Host%2A?displayProperty=nameWithType>
