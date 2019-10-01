---
title: Elemento <httpListener> (impostazioni di rete)
ms.date: 03/30/2017
ms.assetid: 62f121fd-3f2e-4033-bb39-48ae996bfbd9
ms.openlocfilehash: 3f75096681ab07dd6d4788fbded5ca5c4a024aef
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/01/2019
ms.locfileid: "71698191"
---
# <a name="httplistener-element-network-settings"></a>Elemento > \<httpListener (impostazioni di rete)
Personalizza i parametri utilizzati dalla classe <xref:System.Net.HttpListener>.  
  
[ **\<configuration>** ](../configuration-element.md)  
&nbsp; @ no__t-1[ **@no__t -4system. net >** ](system-net-element-network-settings.md)  
&nbsp; @ no__t-1 @ no__t-2 @ no__t-3[ **\<settings >** ](settings-element-network-settings.md)  
&nbsp; @ no__t-1 @ no__t-2 @ no__t-3 @ no__t-4 @ no__t-5 **\<httpListener >**  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<httpListener  
  unescapeRequestUrl="true|false"  
/>  
```  
  
## <a name="type"></a>Type  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|unescapeRequestUrl|Valore booleano che indica se un'istanza di <xref:System.Net.HttpListener> utilizza l'URI senza caratteri di escape non elaborato anziché l'URI convertito.|  
  
### <a name="child-elements"></a>Elementi figlio  
 No.  
  
### <a name="parent-elements"></a>Elementi padre  
  
|**Elemento**|**Descrizione**|  
|-----------------|---------------------|  
|[Impostazioni](settings-element-network-settings.md)|Configura le opzioni di rete di base per lo spazio dei nomi <xref:System.Net>.|  
  
## <a name="remarks"></a>Note  
 L'attributo **unescapeRequestUrl** indica se <xref:System.Net.HttpListener> utilizza l'URI senza codice di escape non elaborato anziché l'URI convertito in cui vengono convertiti i valori con codifica percentuale e vengono eseguiti altri passaggi di normalizzazione.  
  
 Quando un'istanza <xref:System.Net.HttpListener> riceve una richiesta tramite il servizio `http.sys`, crea un'istanza della stringa URI fornita da `http.sys` e la espone come proprietà <xref:System.Net.HttpListenerRequest.Url%2A?displayProperty=nameWithType>.  
  
 Il servizio `http.sys` espone due stringhe URI di richiesta:  
  
- URI non elaborato  
  
- URI convertito  
  
 L'URI non elaborato è il <xref:System.Uri?displayProperty=nameWithType> specificato nella riga della richiesta di una richiesta HTTP:  
  
 `GET /path/`  
  
 `Host: www.contoso.com`  
  
 L'URI non elaborato fornito da `http.sys` per la richiesta indicata in precedenza è "/Path/". Rappresenta la stringa che segue il verbo HTTP così come è stato inviato in rete.  
  
 Il servizio `http.sys` crea un URI convertito dalle informazioni fornite nella richiesta utilizzando l'URI fornito nella riga di richiesta HTTP e l'intestazione host per determinare il server di origine a cui deve essere trasmessa la richiesta. Questa operazione viene eseguita confrontando le informazioni della richiesta con un set di prefissi URI registrati. La documentazione relativa all'SDK del server HTTP fa riferimento a questo URI convertito come struttura HTTP_COOKED_URL.  
  
 Per poter confrontare la richiesta con i prefissi URI registrati, è necessario eseguire alcune operazioni di normalizzazione per la richiesta. Per l'esempio sopra l'URI convertito sarà il seguente:  
  
 `http://www.contoso.com/path/`  
  
 Il servizio `http.sys` combina il valore della proprietà <xref:System.Uri.Host%2A?displayProperty=nameWithType> e la stringa nella riga della richiesta per creare un URI convertito. Inoltre, `http.sys` e la classe <xref:System.Uri?displayProperty=nameWithType> esegue le operazioni seguenti:  
  
- Annulla l'escape di tutti i valori codificati in percentuale.  
  
- Converte i caratteri non ASCII con codifica percentuale in una rappresentazione in caratteri UTF-16. Si noti che i caratteri UTF-8 e ANSI/DBCS sono supportati e i caratteri Unicode (codifica Unicode con il formato% uXXXX).  
  
- Esegue altri passaggi di normalizzazione, come la compressione del percorso.  
  
 Poiché la richiesta non contiene informazioni sulla codifica utilizzata per i valori con codifica percentuale, potrebbe non essere possibile determinare la codifica corretta semplicemente analizzando i valori con codifica percentuale.  
  
 Pertanto `http.sys` fornisce due chiavi del registro di sistema per modificare il processo:  
  
|Chiave del Registro di sistema|Default Value|Descrizione|  
|------------------|-------------------|-----------------|  
|EnableNonUTF8|1|Se è zero, `http.sys` accetta solo URL con codifica UTF-8.<br /><br /> Se diverso da zero, `http.sys` accetta anche URL con codifica ANSI o DBCS nelle richieste.|  
|FavorUTF8|1|Se diverso da zero, `http.sys` tenta sempre di decodificare un URL come UTF-8. Se la conversione ha esito negativo e EnableNonUTF8 è diverso da zero, http. sys tenta di decodificarlo come ANSI o DBCS.<br /><br /> Se zero (e EnableNonUTF8 è diverso da zero), `http.sys` tenta di decodificarlo come ANSI o DBCS; Se l'operazione ha esito negativo, viene tentata una conversione UTF-8.|  
  
 Quando <xref:System.Net.HttpListener> riceve una richiesta, usa l'URI convertito da `http.sys` come input per la proprietà <xref:System.Net.HttpListenerRequest.Url%2A>.  
  
 È necessario supportare i caratteri oltre ai caratteri e ai numeri negli URI. Un esempio è l'URI seguente, che viene usato per recuperare le informazioni sul cliente per il numero cliente "1/3812":  
  
 `http://www.contoso.com/Customer('1%2F3812')/`  
  
 Prendere nota della barra codificata in percentuale nell'URI (% 2F). Questa operazione è necessaria, poiché in questo caso il carattere barra rappresenta i dati e non un delimitatore di percorso.  
  
 Passando la stringa al costruttore URI si otterrà l'URI seguente:  
  
 `http://www.contoso.com/Customer('1/3812')/`  
  
 Suddividendo il percorso nei segmenti si verificheranno gli elementi seguenti:  
  
 `Customer('1`  
  
 `3812')`  
  
 Non si tratta dello scopo del mittente della richiesta.  
  
 Se l'attributo **unescapeRequestUrl** è impostato su **false**, quando il <xref:System.Net.HttpListener> riceve una richiesta, usa l'URI non elaborato anziché l'URI convertito da `http.sys` come input per la proprietà <xref:System.Net.HttpListenerRequest.Url%2A>.  
  
 Il valore predefinito per l'attributo **unescapeRequestUrl** è **true**.  
  
 La proprietà <xref:System.Net.Configuration.HttpListenerElement.UnescapeRequestUrl%2A> può essere usata per ottenere il valore corrente dell'attributo **unescapeRequestUrl** dai file di configurazione applicabili.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come configurare la classe <xref:System.Net.HttpListener> quando viene ricevuta una richiesta di utilizzo dell'URI non elaborato anziché l'URI convertito da `http.sys` come input per la proprietà <xref:System.Net.HttpListenerRequest.Url%2A>.  
  
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
- [Schema delle impostazioni di rete](index.md)
