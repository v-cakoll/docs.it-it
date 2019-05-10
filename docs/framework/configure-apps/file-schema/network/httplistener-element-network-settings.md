---
title: Elemento <httpListener> (impostazioni di rete)
ms.date: 03/30/2017
ms.assetid: 62f121fd-3f2e-4033-bb39-48ae996bfbd9
ms.openlocfilehash: 8257b0311e18a21fbc04185f8297ee8e5f38b86b
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64592730"
---
# <a name="httplistener-element-network-settings"></a>\<httpListener > (impostazioni di rete)
Consente di personalizzare i parametri usati dal <xref:System.Net.HttpListener> classe.  
  
 \<configuration>  
\<system.net>  
\<Impostazioni >  
\<httpListener>  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<httpListener  
  unescapeRequestUrl="true|false"  
/>  
```  
  
## <a name="type"></a>Tipo  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|unescapeRequestUrl|Valore booleano che indica se un <xref:System.Net.HttpListener> istanza utilizza l'URI senza codice di escape non elaborato anziché l'URI convertito.|  
  
### <a name="child-elements"></a>Elementi figlio  
 Nessuno.  
  
### <a name="parent-elements"></a>Elementi padre  
  
|**Elemento**|**Descrizione**|  
|-----------------|---------------------|  
|[settings](../../../../../docs/framework/configure-apps/file-schema/network/settings-element-network-settings.md)|Configura le opzioni di rete di base per lo spazio dei nomi <xref:System.Net>.|  
  
## <a name="remarks"></a>Note  
 Il **unescapeRequestUrl** attributo indica se <xref:System.Net.HttpListener> Usa l'URI senza codice di escape non elaborato anziché l'URI convertito in cui vengono convertiti i valori codificati in percentuale e vengono eseguiti altri passaggi di normalizzazione.  
  
 Quando un <xref:System.Net.HttpListener> istanza riceve una richiesta tramite il `http.sys` servizio, crea un'istanza della stringa URI fornita dal `http.sys`e lo espone come il <xref:System.Net.HttpListenerRequest.Url%2A?displayProperty=nameWithType> proprietà.  
  
 Il `http.sys` servizio espone due stringhe URI richiesta:  
  
- URI non elaborato  
  
- URI convertito  
  
 L'URI non elaborato è il <xref:System.Uri?displayProperty=nameWithType> fornito nella riga della richiesta di una richiesta HTTP:  
  
 `GET /path/`  
  
 `Host: www.contoso.com`  
  
 L'URI non elaborato fornito dal `http.sys` per è indicato in precedenza, la richiesta di "percorso /". Rappresenta la stringa che segue il verbo HTTP, come è stato inviato in rete.  
  
 Il `http.sys` servizio crea un URI convertito dalle informazioni ottenute tramite l'URI fornito nella riga della richiesta HTTP nella richiesta e intestazione Host per determinare il server di origine della richiesta deve essere inoltrato a. Questa operazione viene eseguita confrontando le informazioni della richiesta con un set di prefissi URI registrati. La documentazione di HTTP Server SDK fa riferimento a questo URI convertito della struttura di HTTP_COOKED_URL.  
  
 Per poter essere in grado di confrontare la richiesta con i prefissi URI registrati, la normalizzazione della richiesta deve essere eseguita. Nell'esempio precedente l'URI convertito sarà come segue:  
  
 `http://www.contoso.com/path/`  
  
 Il `http.sys` service combina il <xref:System.Uri.Host%2A?displayProperty=nameWithType> valore della proprietà e la stringa nella riga della richiesta per creare un URI convertito. È inoltre `http.sys` e il <xref:System.Uri?displayProperty=nameWithType> classe esegue anche le operazioni seguenti:  
  
- Escape di annullare la percentuale di tutti i valori codificati.  
  
- Caratteri non ASCII converte codificato in percentuale in una rappresentazione di caratteri UTF-16. Si noti che i caratteri DBCS/ANSI e UTF-8 sono supportati anche i caratteri Unicode (codifica Unicode utilizzando il formato uXXXX %).  
  
- Esegue gli altri passaggi di normalizzazione, ad esempio la compressione del percorso.  
  
 Poiché la richiesta non contiene alcuna informazione sulla codifica usata per i valori codificati in percentuale, potrebbe non essere possibile determinare la codifica corretta appena analizzando i valori codificati in percentuale.  
  
 Di conseguenza `http.sys` vengono fornite due chiavi del Registro di sistema per la modifica del processo:  
  
|Chiave del Registro di sistema|Valore predefinito|Descrizione|  
|------------------|-------------------|-----------------|  
|EnableNonUTF8|1|Se è zero, `http.sys` accetta solo gli URL con codifica UTF-8.<br /><br /> Se diverso da zero, `http.sys` accetta anche un URL con codifica ANSI o con codifica DBCS nelle richieste.|  
|FavorUTF8|1|Se diverso da zero, `http.sys` sempre prova a decodificare un URL come UTF-8 per primo; se tale conversione non riesce ed EnableNonUTF8 è diverso da zero, HTTP. sys quindi prova a decodificare come ANSI o DBCS.<br /><br /> Se è zero (ed EnableNonUTF8 è diverso da zero), `http.sys` prova a decodificare come ANSI o DBCS; se non riesce, ritenta una conversione UTF-8.|  
  
 Quando <xref:System.Net.HttpListener> riceve una richiesta, Usa l'URI convertito da `http.sys` come input per il <xref:System.Net.HttpListenerRequest.Url%2A> proprietà.  
  
 È necessario per il supporto di caratteri oltre ai caratteri e numeri negli URI. Un esempio è l'URI seguente, che consente di recuperare informazioni sui clienti per cliente numero "1/3812":  
  
 `http://www.contoso.com/Customer('1%2F3812')/`  
  
 Si noti la barra nell'Uri (% 2F) codificati in percentuale. Ciò è necessario, poiché in questo caso il carattere di barra rappresenta i dati e non un delimitatore di percorso.  
  
 Passare la stringa al costruttore Uri causerà l'URI seguente:  
  
 `http://www.contoso.com/Customer('1/3812')/`  
  
 Suddividendo il percorso in segmenti comporta i seguenti elementi:  
  
 `Customer('1`  
  
 `3812')`  
  
 Non è questo lo scopo del mittente della richiesta.  
  
 Se il **unescapeRequestUrl** attributo è impostato su **false**, quindi quando il <xref:System.Net.HttpListener> riceve una richiesta, Usa l'URI non elaborato anziché l'URI convertito da `http.sys` come input per il <xref:System.Net.HttpListenerRequest.Url%2A> proprietà.  
  
 Il valore predefinito per il **unescapeRequestUrl** attributo **true**.  
  
 Il <xref:System.Net.Configuration.HttpListenerElement.UnescapeRequestUrl%2A> proprietà può essere utilizzata per ottenere il valore corrente del **unescapeRequestUrl** attributo dal file di configurazione applicabili.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come configurare il <xref:System.Net.HttpListener> classe quando riceve una richiesta per usare l'URI non elaborato anziché l'URI convertito da `http.sys` come input per il <xref:System.Net.HttpListenerRequest.Url%2A> proprietà.  
  
```xml  
<configuration>  
  <system.net>  
    <settings>  
      <httpListener  
        unescapeRequestUrl="false"  
      />  
    </settings>  
  </system.net>  
</configuration>  
```  
  
## <a name="element-information"></a>Informazioni sull'elemento  
  
|||
|-|-|  
|Spazio dei nomi|System.Net|  
|Nome di schema||  
|File di convalida||  
|Può essere vuoto||  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Net.Configuration.HttpListenerElement>
- <xref:System.Net.HttpListener>
- <xref:System.Net.HttpListenerRequest.Url%2A>
- [Schema delle impostazioni di rete](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
