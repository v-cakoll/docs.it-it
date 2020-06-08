---
title: Rilevamento automatico proxy
description: Informazioni sul rilevamento automatico del proxy, in cui il sistema identifica un server proxy Web e lo usa per inviare richieste per conto del client.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- automatic proxy detections
- Web Proxy Auto-Discovery
- Web proxy
- detecting proxies automatically
- WebProxy class, automatic proxy detections
- proxies, automatically detecting
- network
- WPAD (Web Proxy Auto-Discovery)
ms.assetid: fcd9c3bd-93de-4c92-8ff3-837327ad18de
ms.openlocfilehash: dbd5d7fa671ae5ec3b7dc00205f0c9d8381bb3ce
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84502697"
---
# <a name="automatic-proxy-detection"></a>Rilevamento automatico proxy
Il rilevamento automatico del proxy è un processo con cui un server proxy Web viene identificato dal sistema e usato per inviare richieste per conto del client. Questa funzionalità è nota anche come Rilevamento automatico proxy Web (WPAD). Quando il rilevamento automatico del proxy è abilitato, il sistema tenta di trovare uno script di configurazione del proxy responsabile della restituzione del set di proxy che possono essere usati per la richiesta. Se viene trovato, lo script di configurazione del proxy viene scaricato, compilato ed eseguito nel computer locale quando per una richiesta che usa un'istanza <xref:System.Net.WebProxy> vengono ottenute le informazioni del proxy, la risposta o il flusso di richieste.  
  
 Il rilevamento automatico del proxy viene eseguito dalla classe <xref:System.Net.WebProxy> e può usare impostazioni a livello di richiesta, impostazioni del file di configurazione e impostazioni specificate tramite la finestra di dialogo **Rete locale (LAN)** di Internet Explorer.  
  
> [!NOTE]
> È possibile visualizzare la finestra di dialogo di Internet Explorer **Impostazioni rete locale (LAN)** selezionando **Strumenti** dal menu principale di Internet Explorer e quindi scegliendo **Opzioni Internet**. Selezionare quindi la scheda **Connessioni** e scegliere **Impostazioni LAN**.  
  
 Se il rilevamento automatico del proxy è abilitato, la classe <xref:System.Net.WebProxy> tenta di individuare lo script di configurazione del proxy come indicato di seguito:  
  
1. La funzione di WinINet `InternetQueryOption` consente di individuare l'ultimo script di configurazione del proxy rilevato da Internet Explorer.  
  
2. Se lo script non viene individuato, la classe <xref:System.Net.WebProxy> usa il Dynamic Host Configuration Protocol (DHCP) per trovarlo. Il server DHCP può rispondere specificando il percorso (nome host) o l'URL completo dello script.  
  
3. Se DHCP non identifica l'host WPAD, viene eseguita una query sul server DNS per trovare un host con WPAD come nome o alias.  
  
4. Se l'host non viene identificato ma nelle impostazioni della LAN di Internet Explorer o in un file di configurazione è specificato il percorso di uno script di configurazione del proxy, viene usato questo percorso.  
  
> [!NOTE]
> Le applicazioni in esecuzione come servizio NT o nell'ambito di ASP.NET usano le impostazioni del server proxy configurate dall'utente chiamante in Internet Explorer (se disponibili). È possibile che queste impostazioni non siano disponibili per tutte le applicazioni di servizio.  
  
 I proxy vengono configurati a livello di singolo connettoide. Un connettoide è un elemento della finestra di dialogo di connessione di rete e può essere un dispositivo di rete fisico (modem o scheda Ethernet) o un'interfaccia virtuale (ad esempio, una connessione VPN in esecuzione su un dispositivo di rete). Se un connettoide cambia (ad esempio, una connessione wireless modifica un punto di accesso o viene abilitata una rete VPN), l'algoritmo di rilevamento del proxy viene eseguito nuovamente.  
  
 Per impostazione predefinita, per il rilevamento del proxy vengono usate le impostazioni del proxy definite in Internet Explorer. Se l'applicazione è in esecuzione con un account non interattivo (senza un modo pratico per configurare le impostazioni del proxy IE) o se si vuole usare impostazioni proxy diverse dalle impostazioni di IE, è possibile configurare il proxy creando un file di configurazione con gli elementi [ \<defaultProxy> elemento (impostazioni di rete)](../configure-apps/file-schema/network/defaultproxy-element-network-settings.md) ed [ \<proxy> elemento (impostazioni di rete)](../configure-apps/file-schema/network/proxy-element-network-settings.md) definiti.  
  
 Per le richieste create, è possibile disabilitare il rilevamento automatico del proxy a livello di richiesta specificando un valore <xref:System.Net.WebRequest.Proxy%2A> null con la richiesta, come illustrato nell'esempio di codice seguente.  
  
```csharp  
public static void DisableForMyRequest (Uri resource)  
{  
    WebRequest request = WebRequest.Create (resource);  
    request.Proxy = null;  
    WebResponse response = request.GetResponse ();  
}  
```  
  
```vb  
Public Shared Sub DisableForMyRequest(ByVal resource As Uri)  
    Dim request As WebRequest = WebRequest.Create(resource)  
    request.Proxy = Nothing  
    Dim response As WebResponse = request.GetResponse()  
    End Sub
```  
  
 Le richieste in cui non è specificato un proxy usano il proxy predefinito del dominio dell'applicazione, disponibile nella proprietà <xref:System.Net.WebRequest.DefaultWebProxy%2A>.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Net.WebProxy>
- <xref:System.Net.WebRequest>
- [\<system.Net>Elemento (impostazioni di rete)](../configure-apps/file-schema/network/system-net-element-network-settings.md)
